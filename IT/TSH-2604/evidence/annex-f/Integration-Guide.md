# ANNEX F: INTEGRATION GUIDE

**Tender Reference:** MMFSB/TD 01/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**System:** LogisticsPro Enterprise Suite v4.2  
**Date:** 31 January 2026

---

## TABLE OF CONTENTS

1. [Integration Architecture Overview](#1-integration-architecture-overview)
2. [API Specifications](#2-api-specifications)
3. [EDI Integration Standards](#3-edi-integration-standards)
4. [Third-Party System Integrations](#4-third-party-system-integrations)
5. [Internal System Integration](#5-internal-system-integration)
6. [Security & Authentication](#6-security--authentication)
7. [Integration Development Kit (IDK)](#7-integration-development-kit-idk)
8. [Error Handling & Monitoring](#8-error-handling--monitoring)

---

## 1. INTEGRATION ARCHITECTURE OVERVIEW

### 1.1 Enterprise Integration Architecture

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                         EXTERNAL SYSTEMS LAYER                                   │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────────────┐ │
│  │   IRBM   │  │  MyGBS   │  │  Port    │  │   KTMB   │  │  Shipping Lines  │ │
│  │ MyInvois │  │ (Customs)│  │   PCS    │  │  (Rail)  │  │  (15+ carriers)  │ │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────────┬─────────┘ │
│       │             │             │             │                  │           │
│       │  REST API   │ SOAP/REST   │   EDI/API   │     EDI          │   EDI/API │
│       │             │             │             │                  │           │
└───────┼─────────────┼─────────────┼─────────────┼──────────────────┼───────────┘
        │             │             │             │                  │
        └─────────────┴─────────────┴─────────────┴──────────────────┘
                                    │
                          ┌─────────▼─────────┐
                          │   API GATEWAY     │
                          │    (Kong)         │
                          │  • Rate Limiting  │
                          │  • Auth/JWT       │
                          │  • Logging        │
                          │  • Load Balancing │
                          └─────────┬─────────┘
                                    │
┌───────────────────────────────────┼─────────────────────────────────────────────┐
│                      LOGISTICSPRO INTEGRATION LAYER                             │
├───────────────────────────────────┼─────────────────────────────────────────────┤
│                                   │                                             │
│  ┌────────────────────────────────┼─────────────────────────────────────────┐  │
│  │         MESSAGE BUS            │         (RabbitMQ)                      │  │
│  │  ┌─────────────────────────────┼─────────────────────────────────────┐   │  │
│  │  │ • Async Processing          │ • Event-driven Architecture         │   │  │
│  │  │ • Guaranteed Delivery       │ • Dead Letter Queue                 │   │  │
│  │  │ • Message Persistence       │ • Priority Queuing                  │   │  │
│  │  └─────────────────────────────┴─────────────────────────────────────┘   │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│                                   │                                             │
│  ┌────────────────────────────────┼─────────────────────────────────────────┐  │
│  │     INTEGRATION ADAPTERS       │                                         │  │
│  │  ┌────────┐ ┌────────┐ ┌───────▼────┐ ┌────────┐ ┌────────┐            │  │
│  │  │ REST   │ │ SOAP   │ │   EDI      │ │  SFTP  │ │Webhook │            │  │
│  │  │Adapter │ │Adapter │ │  Adapter   │ │Adapter │ │Adapter │            │  │
│  │  │(150+)  │ │(50+)   │ │  (ANSI/    │ │(Auto)  │ │(Real-  │            │  │
│  │  │        │ │        │ │   UN/EDIF) │ │        │ │  time) │            │  │
│  │  └────────┘ └────────┘ └────────────┘ └────────┘ └────────┘            │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│                                   │                                             │
└───────────────────────────────────┼─────────────────────────────────────────────┘
                                    │
┌───────────────────────────────────┼─────────────────────────────────────────────┐
│                      INTERNAL SYSTEMS LAYER                                     │
├───────────────────────────────────┼─────────────────────────────────────────────┤
│                                   │                                             │
│  ┌──────────┐  ┌──────────┐  ┌───▼────┐  ┌──────────┐  ┌──────────┐           │
│  │   HMS    │  │   FFS    │  │  WMS   │  │   TMS    │  │   FMS    │           │
│  │Microsvcs │  │Microsvcs │  │Microsvc│  │Microsvcs │  │Microsvcs │           │
│  │  (12)    │  │  (10)    │  │  (14)  │  │  (11)    │  │  (16)    │           │
│  └────┬─────┘  └────┬─────┘  └───┬────┘  └────┬─────┘  └────┬─────┘           │
│       │             │            │            │             │                  │
│       └─────────────┴────────────┴────────────┴─────────────┘                  │
│                          │                                                     │
│                    ┌─────▼─────┐                                               │
│                    │  SHARED   │                                               │
│                    │  DATABASE │                                               │
│                    │  LAYER    │                                               │
│                    └───────────┘                                               │
│                                                                                │
└────────────────────────────────────────────────────────────────────────────────┘
```

---

### 1.2 Integration Capabilities Summary

| Capability | Specification | Status |
|------------|---------------|--------|
| **API Protocols** | REST, GraphQL, SOAP, gRPC | ✅ Supported |
| **EDI Standards** | ANSI X12, UN/EDIFACT, XML, JSON | ✅ Supported |
| **File Transfers** | SFTP, FTPS, AS2, HTTPS | ✅ Supported |
| **Real-time Events** | Webhooks, WebSocket, Server-Sent Events | ✅ Supported |
| **Message Queue** | RabbitMQ, Apache Kafka | ✅ Supported |
| **API Gateway** | Kong Enterprise | ✅ Deployed |
| **Pre-built Connectors** | 150+ | ✅ Available |

---

## 2. API SPECIFICATIONS

### 2.1 OpenAPI 3.0 Specification

All LogisticsPro APIs are documented using OpenAPI 3.0 standard.

**API Documentation URL:** `https://api.logisticspro.com/docs`

**Base URL:** `https://api.logisticspro.com/v1`

#### Authentication

All API requests require authentication using OAuth 2.0 with JWT tokens.

```http
GET /shipments/SH-001
Authorization: Bearer {access_token}
X-API-Key: {api_key}
Content-Type: application/json
```

---

### 2.2 Core API Endpoints

#### Shipment Management API

```yaml
openapi: 3.0.0
info:
  title: LogisticsPro Shipment API
  version: 1.0.0
  description: API for managing shipments across HMS, FFS, WMS, TMS

servers:
  - url: https://api.logisticspro.com/v1
    description: Production
  - url: https://api-staging.logisticspro.com/v1
    description: Staging

paths:
  /shipments:
    get:
      summary: List shipments
      parameters:
        - name: status
          in: query
          schema:
            type: string
            enum: [pending, in_transit, completed, cancelled]
        - name: from_date
          in: query
          schema:
            type: string
            format: date
        - name: to_date
          in: query
          schema:
            type: string
            format: date
        - name: customer_id
          in: query
          schema:
            type: string
        - name: limit
          in: query
          schema:
            type: integer
            default: 25
            maximum: 100
        - name: offset
          in: query
          schema:
            type: integer
            default: 0
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              schema:
                type: object
                properties:
                  data:
                    type: array
                    items:
                      $ref: '#/components/schemas/Shipment'
                  pagination:
                    type: object
                    properties:
                      total:
                        type: integer
                      limit:
                        type: integer
                      offset:
                        type: integer
                      has_more:
                        type: boolean
    
    post:
      summary: Create new shipment
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ShipmentCreate'
      responses:
        '201':
          description: Shipment created
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Shipment'
        '400':
          description: Validation error
        '401':
          description: Unauthorized

  /shipments/{shipment_id}:
    get:
      summary: Get shipment details
      parameters:
        - name: shipment_id
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: Shipment details
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Shipment'
        '404':
          description: Shipment not found
    
    put:
      summary: Update shipment
      parameters:
        - name: shipment_id
          in: path
          required: true
          schema:
            type: string
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ShipmentUpdate'
      responses:
        '200':
          description: Shipment updated
        '404':
          description: Shipment not found

components:
  schemas:
    Shipment:
      type: object
      properties:
        shipment_id:
          type: string
          example: "SH-MMFSB-2026-001892"
        status:
          type: string
          enum: [pending, in_transit, completed, cancelled]
        customer:
          type: object
          properties:
            id:
              type: string
            name:
              type: string
            contact:
              type: string
        route:
          type: object
          properties:
            origin:
              type: string
            destination:
              type: string
            distance_km:
              type: number
        container:
          type: object
          properties:
            number:
              type: string
            size:
              type: string
              enum: [20ft, 40ft, 40ft HC, 45ft]
            type:
              type: string
            weight_kg:
              type: number
        assigned_vehicle:
          type: object
          properties:
            pm_unit:
              type: string
            driver:
              type: string
            current_location:
              type: object
              properties:
                lat:
                  type: number
                lng:
                  type: number
        timeline:
          type: array
          items:
            type: object
            properties:
              status:
                type: string
              timestamp:
                type: string
                format: date-time
        eta:
          type: string
          format: date-time
        created_at:
          type: string
          format: date-time
        updated_at:
          type: string
          format: date-time
```

---

### 2.3 Vehicle Tracking API

```yaml
paths:
  /tracking/vehicles:
    get:
      summary: Get real-time vehicle locations
      parameters:
        - name: vehicle_ids
          in: query
          schema:
            type: array
            items:
              type: string
        - name: status
          in: query
          schema:
            type: string
            enum: [active, idle, offline]
      responses:
        '200':
          description: Vehicle locations
          content:
            application/json:
              schema:
                type: object
                properties:
                  vehicles:
                    type: array
                    items:
                      type: object
                      properties:
                        vehicle_id:
                          type: string
                        pm_unit:
                          type: string
                        driver:
                          type: string
                        location:
                          type: object
                          properties:
                            lat:
                              type: number
                            lng:
                              type: number
                            speed_kmh:
                              type: number
                            heading:
                              type: number
                        status:
                          type: string
                        last_updated:
                          type: string
                          format: date-time

  /tracking/vehicles/{vehicle_id}/history:
    get:
      summary: Get vehicle movement history
      parameters:
        - name: vehicle_id
          in: path
          required: true
          schema:
            type: string
        - name: from
          in: query
          required: true
          schema:
            type: string
            format: date-time
        - name: to
          in: query
          required: true
          schema:
            type: string
            format: date-time
      responses:
        '200':
          description: Movement history
          content:
            application/json:
              schema:
                type: object
                properties:
                  vehicle_id:
                    type: string
                  path:
                    type: array
                    items:
                      type: object
                      properties:
                        lat:
                          type: number
                        lng:
                          type: number
                        timestamp:
                          type: string
                        speed_kmh:
                          type: number
```

---

### 2.4 Billing & Invoicing API

```yaml
paths:
  /invoices:
    post:
      summary: Generate invoice
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              properties:
                customer_id:
                  type: string
                invoice_date:
                  type: string
                  format: date
                due_date:
                  type: string
                  format: date
                line_items:
                  type: array
                  items:
                    type: object
                    properties:
                      description:
                        type: string
                      quantity:
                        type: number
                      unit_price:
                        type: number
                      tax_rate:
                        type: number
                generate_einvoice:
                  type: boolean
                  default: true
      responses:
        '201':
          description: Invoice created
          content:
            application/json:
              schema:
                type: object
                properties:
                  invoice_id:
                    type: string
                  invoice_number:
                    type: string
                  einvoice_uuid:
                    type: string
                  status:
                    type: string
                  total_amount:
                    type: number
                  pdf_url:
                    type: string

  /invoices/{invoice_id}/einvoice:
    post:
      summary: Submit to MyInvois
      parameters:
        - name: invoice_id
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: e-Invoice submitted
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    type: string
                    example: "submitted"
                  irbm_reference:
                    type: string
                  validation_time:
                    type: string
                    format: date-time
                  qr_code:
                    type: string
```

---

### 2.5 Webhook Events

```yaml
webhooks:
  shipment.status_changed:
    post:
      summary: Shipment status changed
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                event:
                  type: string
                  example: "shipment.status_changed"
                timestamp:
                  type: string
                  format: date-time
                webhook_id:
                  type: string
                data:
                  type: object
                  properties:
                    shipment_id:
                      type: string
                    previous_status:
                      type: string
                    new_status:
                      type: string
                    location:
                      type: object
                    triggered_by:
                      type: string
      responses:
        '200':
          description: Webhook received

  shipment.delay_detected:
    post:
      summary: Shipment delay detected by AI
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                event:
                  type: string
                  example: "shipment.delay_detected"
                timestamp:
                  type: string
                data:
                  type: object
                  properties:
                    shipment_id:
                      type: string
                    predicted_delay_hours:
                      type: number
                    confidence:
                      type: number
                    reason:
                      type: string
```

---

## 3. EDI INTEGRATION STANDARDS

### 3.1 Supported EDI Standards

| Standard | Version | Message Types | Status |
|----------|---------|---------------|--------|
| **UN/EDIFACT** | D96A, D01B | COPARN, COPRAR, CODECO, COARRI, IFTMIN, IFTMBC, CUSCAR | ✅ Full Support |
| **ANSI X12** | 4010, 5010 | 204, 210, 214, 810, 850, 856, 997 | ✅ Full Support |
| **XML** | Custom | Various port/shipping line formats | ✅ Full Support |
| **JSON** | REST API | Modern API integrations | ✅ Full Support |

---

### 3.2 EDIFACT Message Examples

#### COPARN (Container Arrival Notice)

```
UNA:+.? '
UNB+UNOA:3+MAERSK+MMF+260131:1432+892345'
UNH+1+COPARN:D:96A:UN'
BGM+105+7892345+9'
RFF+BN:BOOK123456'
TDT+20+026E+1++MSC:172:20+++MSC OSCAR:MA'
LOC+5+MYPKG:139:6'
LOC+7+SGSIN:139:6'
DTM+132:20260131:102'
DTM+133:20260205:102'
MEA+WT++KGM:24500'
MEA+VOL++MTQ:65.5'
EQD+CN+MSKU7892345:102:5++2:45R1'
SEL+SL789234+SH'
FTX+AAI+++ELECTRONIC COMPONENTS'
FTX+AAA+++NOR'
NAD+CA+MAERSK:160:87'
NAD+CN+ABC LOGISTICS:160:87'
NAD+NI+ABC LOGISTICS:160:87'
GID+1+500:CT'
FTX+AAA+++COMPUTER PARTS'
UNT+20+1'
UNZ+1+892345'
```

**Field Mapping:**

| Segment | Element | Description | Maps To |
|---------|---------|-------------|---------|
| BGM | C105/1154 | Booking Reference | shipment.booking_ref |
| TDT | C222/8212 | Vessel Name | shipment.vessel |
| TDT | C228/8179 | Voyage Number | shipment.voyage |
| LOC+5 | C517/3225 | Port of Loading | shipment.pol |
| LOC+7 | C517/3225 | Port of Discharge | shipment.pod |
| DTM+132 | C507/2380 | ETA | shipment.eta |
| MEA+WT | C174/6314 | Weight | container.weight_kg |
| EQD | C237/8260 | Container Number | container.number |
| SEL | C215/9308 | Seal Number | container.seal |
| NAD+CN | C082/3039 | Consignee | customer.name |

---

#### CODECO (Container Departure/Arrival Confirmation)

```
UNA:+.? '
UNB+UNOA:3+PPSB+MMF+260131:1432+892346'
UNH+1+CODECO:D:96A:UN'
BGM+36+7892345+9'
NAD+MS+MMF:160:87'
EQD+CN+MSKU7892345:102:5++2:45R1'
RFF+BN:BOOK123456'
TDT+30++3++TR:172:20+++PM047:MM'
LOC+147+MYPKG:139:6'
DTM+7:202601311432:203'
MEA+WT++KGM:32450'
SEL+SL789234+CA'
FTX+AAI+++GATE IN COMPLETED'
TDT+30'
LOC+9+MYPKG:139:6'
UNT+13+1'
UNZ+1+892346'
```

---

### 3.3 ANSI X12 Message Examples

#### 214 (Shipment Status Message)

```
ISA*00*          *00*          *ZZ*MAERSK         *ZZ*MMF            *260131*1432*U*00401*000000001*0*P*>
GS*QM*MAERSK*MMF*20260131*1432*1*X*004010
ST*214*0001
B10*7892345*BOOK123456*SCAC
N1*SF*TechCorp Sdn Bhd
N1*CN*ABC Logistics
LX*1
AT7*X3*NS***20260131*1432*LT
MS1*MYPKG*SGSIN*MI
MS2*MSC*026E
AT8*G*L*24500*65.5
SE*10*0001
GE*1*1
IEA*1*000000001
```

---

### 3.4 EDI Configuration

#### Trading Partner Setup

```json
{
  "trading_partner": {
    "id": "TP-MAERSK-001",
    "name": "Maersk Line",
    "type": "shipping_line",
    "edi_config": {
      "standard": "EDIFACT",
      "version": "D96A",
      "messages": ["COPARN", "COPRAR", "CODECO", "COARRI"],
      "communication": {
        "protocol": "SFTP",
        "host": "sftp.maersk.com",
        "port": 22,
        "authentication": "key_based",
        "inbound_directory": "/to_mmf",
        "outbound_directory": "/from_mmf"
      },
      "mapping_profile": "MAERSK_STANDARD",
      "validation_rules": {
        "strict_mode": true,
        "allow_unknown_segments": false,
        "require_all_mandatory": true
      }
    }
  }
}
```

---

## 4. THIRD-PARTY SYSTEM INTEGRATIONS

### 4.1 IRBM MyInvois Integration

**Purpose:** e-Invoice submission and validation

**Protocol:** REST API (JSON)

**Authentication:** OAuth 2.0 Client Credentials

**Base URL:** `https://api.myinvois.hasil.gov.my/v1.0`

#### API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/v1.0/login` | POST | Get access token |
| `/api/v1.0/documents/submission` | POST | Submit e-Invoice |
| `/api/v1.0/documents/{id}` | GET | Get document status |
| `/api/v1.0/documents/search` | GET | Search documents |

#### Submit e-Invoice

```http
POST https://api.myinvois.hasil.gov.my/api/v1.0/documents/submission
Authorization: Bearer {access_token}
Content-Type: application/json

{
  "documents": [
    {
      "format": "JSON",
      "document": "{base64_encoded_invoice_json}",
      "documentHash": "sha256_hash",
      "codeNumber": "INV-001892"
    }
  ]
}
```

#### Response

```json
{
  "submissionUID": "SUB-789234-20260131",
  "acceptedDocuments": [
    {
      "uuid": "IVL-789234-20260131-001892",
      "internalId": "INV-001892",
      "longId": "https://myinvois.hasil.gov.my/verify/IVL-789234...",
      "dateTimeValidated": "2026-01-31T14:32:18+08:00"
    }
  ],
  "rejectedDocuments": []
}
```

---

### 4.2 MyGBS (Customs) Integration

**Purpose:** Customs declaration submission and status tracking

**Protocol:** SOAP Web Services

**WSDL:** `https://mygbs.customs.gov.my/services/CustomsDeclaration?wsdl`

#### Operations

| Operation | Description |
|-----------|-------------|
| `submitDeclaration` | Submit K1/K2/K3 declaration |
| `queryDeclarationStatus` | Check declaration status |
| `getTaxCalculation` | Get duty/tax calculation |
| `updateDeclaration` | Amend declaration |

#### Submit Declaration (K1)

```xml
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Header>
    <wsse:Security>
      <wsse:UsernameToken>
        <wsse:Username>MMF_USER</wsse:Username>
        <wsse:Password>*****</wsse:Password>
      </wsse:UsernameToken>
    </wsse:Security>
  </soap:Header>
  <soap:Body>
    <submitDeclaration xmlns="http://customs.gov.my/mygbs">
      <declaration>
        <declarationType>K1</declarationType>
        <referenceNumber>IMP-2026-001892</referenceNumber>
        <importer>
          <tin>C1234567890</tin>
          <name>Multimodal Freight Sdn Bhd</name>
        </importer>
        <supplier>
          <name>TechCorp Sdn Bhd</name>
          <country>MY</country>
        </supplier>
        <items>
          <item>
            <lineNumber>1</lineNumber>
            <hsCode>8471.30.1000</hsCode>
            <description>Computer Motherboards</description>
            <quantity>500</quantity>
            <uom>PCS</uom>
            <value>125000.00</value>
            <currency>MYR</currency>
          </item>
        </items>
        <containers>
          <container>
            <number>MSKU7892345</number>
            <size>40HC</size>
            <seal>SL789234</seal>
          </container>
        </containers>
      </declaration>
    </submitDeclaration>
  </soap:Body>
</soap:Envelope>
```

---

### 4.3 Port Klang PCS Integration

**Purpose:** Port Community System for container tracking

**Protocol:** REST API + SFTP

**Base URL:** `https://api.pcspk.com/v2`

#### Key Endpoints

| Endpoint | Description |
|----------|-------------|
| `/vessels/{imo}/schedule` | Vessel schedule |
| `/containers/{number}/status` | Container status |
| `/bookings/{ref}/details` | Booking details |
| `/gate/appointments` | Gate appointment booking |

---

### 4.4 Banking Integration (FPX)

**Purpose:** Online payment processing

**Protocol:** REST API

**Supported Banks:** Maybank, CIMB, Public Bank, RHB, Hong Leong, and 20+ others

#### Payment Flow

```
1. Customer selects FPX payment
2. System calls /api/payments/initiate
3. Redirect customer to bank portal
4. Bank returns callback with status
5. System verifies payment with bank
6. Auto-reconcile against invoice
```

---

### 4.5 GPS/Telematics Integration

**Purpose:** Real-time vehicle tracking

**Supported Providers:** Geotab, Wialon, Trackimo, ATrack

#### Geotab API

```http
GET https://api.geotab.com/v1/Get
{
  "typeName": "Device",
  "credentials": {
    "database": "mmf_fleet",
    "userName": "api_user",
    "sessionId": "session_token"
  }
}
```

#### Webhook Integration

```json
{
  "event": "device_moved",
  "device": {
    "id": "b123456",
    "name": "PM-047"
  },
  "position": {
    "latitude": 3.0421,
    "longitude": 101.3678,
    "speed": 68,
    "heading": 135
  },
  "timestamp": "2026-01-31T14:32:18Z"
}
```

---

## 5. INTERNAL SYSTEM INTEGRATION

### 5.1 Inter-Module Communication

#### Event-Driven Architecture

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                         INTERNAL EVENT BUS                                       │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│  PUBLISHER ───────────────► EVENT ───────────────► SUBSCRIBERS                   │
│                                                                                  │
│  HMS ──job.completed──────► JobEvent ────────────► FMS (billing)                │
│                              │                   ► WMS (alloc)                   │
│                              │                   ► Notification svc              │
│                              │                                                  │
│  FFS ──shipment.arrived────► ShipmentEvent ─────► HMS (haulage)                 │
│                              │                   ► WMS (receiving)               │
│                              │                   ► TMS (yard)                    │
│                              │                                                  │
│  WMS ──order.shipped───────► OrderEvent ─────────► FFS (status)                 │
│                              │                   ► FMS (revenue rec)             │
│                              │                                                  │
│  TMS ──container.gatein────► ContainerEvent ─────► WMS (expect)                 │
│                              │                   ► FMS (storage bill)            │
│                              │                                                  │
│  FMS ──payment.received────► PaymentEvent ───────► HMS (credit release)         │
│                              │                   ► All (status update)           │
│                                                                                  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

---

### 5.2 Data Synchronization

#### Real-time Synchronization

| Source | Target | Data | Frequency |
|--------|--------|------|-----------|
| HMS | FMS | Job completion, billing data | Real-time (Event) |
| FFS | HMS | Shipment haulage requests | Real-time (Event) |
| WMS | FFS | Inventory availability | Real-time (Event) |
| TMS | HMS | Container release status | Real-time (Event) |
| All | FMS | Financial transactions | Real-time (Event) |

#### Batch Synchronization

| Source | Target | Data | Frequency |
|--------|--------|------|-----------|
| HMS | Data Warehouse | GPS tracking history | Hourly |
| FFS | Data Warehouse | Shipment statistics | Hourly |
| FMS | IRBM | e-Invoice submission | Real-time |
| All | Backup | Full data backup | Daily |

---

### 5.3 Shared Services

#### Common Authentication Service

```
┌─────────────────────────────────────────────────────────────────────┐
│                    AUTH SERVICE (OAuth 2.0)                          │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  ┌──────────────┐        ┌──────────────┐        ┌──────────────┐   │
│  │    HMS       │◄──────►│              │◄──────►│  Microsoft   │   │
│  │    FFS       │        │   IDENTITY   │        │   Entra ID   │   │
│  │    WMS       │◄──────►│   PROVIDER   │◄──────►│  (SSO)       │   │
│  │    TMS       │        │              │        │              │   │
│  │    FMS       │◄──────►│  • JWT Tokens│        │  • SAML 2.0  │   │
│  │              │        │  • RBAC      │        │  • MFA       │   │
│  │  Mobile Apps │◄──────►│  • Sessions  │        │              │   │
│  └──────────────┘        └──────────────┘        └──────────────┘   │
│                                                                      │
└─────────────────────────────────────────────────────────────────────┘
```

#### Shared Database Access

```yaml
Database Architecture:
  PostgreSQL Cluster:
    - Primary: Read/Write operations
    - Standby 1: Read replica for reporting
    - Standby 2: Read replica for analytics
  
  Schema Separation:
    - hms_schema: HMS tables
    - ffs_schema: FFS tables
    - wms_schema: WMS tables
    - tms_schema: TMS tables
    - fms_schema: FMS tables
    - shared_schema: Common tables (users, configs, audit_logs)
  
  Cross-Schema Access:
    - Foreign Data Wrappers for cross-module queries
    - Materialized Views for aggregated data
    - Row-Level Security for data isolation
```

---

## 6. SECURITY & AUTHENTICATION

### 6.1 API Security

#### Authentication Flow (OAuth 2.0 + PKCE)

```
┌─────────┐                                    ┌─────────────┐
│ Client  │                                    │ Auth Server │
└────┬────┘                                    └──────┬──────┘
     │                                               │
     │ 1. Authorization Request + PKCE               │
     │ ─────────────────────────────────────────────►│
     │                                               │
     │ 2. Authorization Code                         │
     │ ◄─────────────────────────────────────────────│
     │                                               │
     │ 3. Token Request (code + verifier)            │
     │ ─────────────────────────────────────────────►│
     │                                               │
     │ 4. Access Token + Refresh Token               │
     │ ◄─────────────────────────────────────────────│
     │                                               │
     │ 5. API Request (Bearer token)                 │
     │ ─────────────────────────────────────────────►│
     │                                               │
```

#### JWT Token Structure

```json
{
  "header": {
    "alg": "RS256",
    "typ": "JWT",
    "kid": "key-id-2026"
  },
  "payload": {
    "iss": "https://auth.logisticspro.com",
    "sub": "user_789234",
    "aud": "logisticspro-api",
    "exp": 1738331538,
    "iat": 1738327938,
    "scope": "hms:read hms:write ffs:read fms:read",
    "permissions": [
      "job:create",
      "job:update",
      "shipment:view",
      "invoice:view"
    ],
    "branch": "PK",
    "department": "Operations"
  }
}
```

---

### 6.2 mTLS (Mutual TLS)

For high-security integrations (banking, government):

```
Client                          Server
  │                               │
  │ ───── Client Hello ─────────► │
  │                               │
  │ ◄──── Server Certificate ─── │
  │ ◄──── Certificate Request ── │
  │                               │
  │ ───── Client Certificate ──► │
  │ ───── Client Key Exchange ─► │
  │                               │
  │ ◄──── Encrypted Finished ─── │
  │ ───── Encrypted Finished ──► │
  │                               │
  │ ◄──── Secure Channel ──────► │
```

---

### 6.3 API Rate Limiting

| Tier | Requests/Minute | Burst | Use Case |
|------|-----------------|-------|----------|
| **Free** | 60 | 10 | Development, testing |
| **Standard** | 1,000 | 100 | Single customer integration |
| **Enterprise** | 10,000 | 1,000 | High-volume trading partner |
| **Internal** | Unlimited | N/A | Internal system calls |

---

## 7. INTEGRATION DEVELOPMENT KIT (IDK)

### 7.1 IDK Components

```
Integration Development Kit (IDK)
├── SDKs/
│   ├── Python SDK
│   ├── Node.js SDK
│   ├── Java SDK
│   └── .NET SDK
├── Tools/
│   ├── Connector Builder
│   ├── Mapping Designer
│   ├── Test Simulator
│   └── Monitoring Dashboard
├── Templates/
│   ├── REST Connector
│   ├── SOAP Connector
│   ├── EDI Connector
│   └── File Connector
└── Documentation/
    ├── Quick Start Guide
    ├── Best Practices
    └── API Cookbook
```

---

### 7.2 Connector Development

#### Python SDK Example

```python
from logisticspro import IntegrationClient

# Initialize client
client = IntegrationClient(
    api_key="your_api_key",
    api_secret="your_api_secret",
    environment="production"
)

# Create custom connector
@client.connector("custom_erp")
class CustomERPConnector:
    def authenticate(self, credentials):
        """Authenticate with external system"""
        return requests.post(
            f"{self.base_url}/auth",
            json=credentials
        ).json()["token"]
    
    def fetch_orders(self, since_date):
        """Fetch orders from external system"""
        return requests.get(
            f"{self.base_url}/orders",
            headers={"Authorization": f"Bearer {self.token}"},
            params={"since": since_date}
        ).json()
    
    def transform_order(self, external_order):
        """Transform to LogisticsPro format"""
        return {
            "customer_id": external_order["cust_code"],
            "origin": external_order["from_location"],
            "destination": external_order["to_location"],
            "cargo_details": {
                "description": external_order["item_desc"],
                "weight_kg": external_order["weight"]
            }
        }
    
    def sync(self):
        """Main synchronization method"""
        orders = self.fetch_orders(since_date="2026-01-01")
        for order in orders:
            transformed = self.transform_order(order)
            client.shipments.create(transformed)
```

---

### 7.3 Testing Tools

#### Integration Test Simulator

```json
{
  "test_suite": {
    "name": "Maersk EDI Integration Test",
    "scenarios": [
      {
        "name": "COPARN Processing",
        "input": {
          "type": "edi_file",
          "content": "UNA:+.? 'UNB+UNOA:3+MAERSK+MMF..."
        },
        "expected_output": {
          "shipment_created": true,
          "container_number": "MSKU7892345",
          "validation_passed": true
        },
        "assertions": [
          "response.status == 200",
          "data.container.number == 'MSKU7892345'",
          "data.status == 'pending'"
        ]
      }
    ]
  }
}
```

---

## 8. ERROR HANDLING & MONITORING

### 8.1 Error Codes

| Code | Description | Retryable | Action |
|------|-------------|-----------|--------|
| `INT-001` | Connection timeout | Yes | Retry with backoff |
| `INT-002` | Authentication failed | No | Check credentials |
| `INT-003` | Invalid message format | No | Fix mapping |
| `INT-004` | Duplicate transaction | No | Check idempotency |
| `INT-005` | Target system unavailable | Yes | Queue for retry |
| `INT-006` | Validation error | No | Review data |

---

### 8.2 Retry Strategy

```python
retry_config = {
    "max_retries": 5,
    "backoff_strategy": "exponential",
    "initial_delay": 1,  # seconds
    "max_delay": 300,    # 5 minutes
    "retryable_errors": ["INT-001", "INT-005"],
    "dead_letter_queue": "failed_integrations"
}
```

---

### 8.3 Integration Monitoring Dashboard

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                    INTEGRATION HEALTH MONITOR                                    │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│  OVERALL STATUS: 🟢 HEALTHY                                                      │
│                                                                                  │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐                  │
│  │ ACTIVE CONNS    │  │ SUCCESS RATE    │  │ AVG LATENCY     │                  │
│  │     45          │  │     99.7%       │  │     145ms       │                  │
│  │    (3 new)      │  │    ↑ 0.2%       │  │    ↓ 12ms       │                  │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘                  │
│                                                                                  │
│  TRADING PARTNER STATUS                                                          │
│  ┌──────────────┬──────────┬──────────────┬──────────────┬──────────────────┐  │
│  │ Partner      │ Status   │ Last Success │ Success Rate │ Queue Depth      │  │
│  ├──────────────┼──────────┼──────────────┼──────────────┼──────────────────┤  │
│  │ IRBM MyInvois│ 🟢       │ 14:32:18     │ 100%         │ 0                │  │
│  │ MyGBS        │ 🟢       │ 14:28:45     │ 99.8%        │ 0                │  │
│  │ Maersk       │ 🟢       │ 14:30:22     │ 99.5%        │ 2                │  │
│  │ Port Klang   │ 🟡       │ 14:15:00     │ 95.2%        │ 12               │  │
│  │ MSC          │ 🟢       │ 14:10:08     │ 99.9%        │ 0                │  │
│  └──────────────┴──────────┴──────────────┴──────────────┴──────────────────┘  │
│                                                                                  │
│  RECENT ERRORS                                                                   │
│  ┌──────────────┬──────────┬──────────────┬──────────────┬──────────────────┐  │
│  │ Time         │ Partner  │ Error Code   │ Message      │ Status           │  │
│  ├──────────────┼──────────┼──────────────┼──────────────┼──────────────────┤  │
│  │ 14:28:12     │ MSC      │ INT-001      │ Timeout      │ ✅ Retried OK    │  │
│  │ 14:15:33     │ PPSB     │ INT-005      │ 503 Error    │ ⏳ Retry 3/5     │  │
│  └──────────────┴──────────┴──────────────┴──────────────┴──────────────────┘  │
│                                                                                  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 01/2026 |
| API Version | v1.0 |
| OpenAPI Spec | 3.0.0 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*

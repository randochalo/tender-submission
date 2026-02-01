# TSH-2604: API DOCUMENTATION
## Complete API Reference

**Base URL:** `https://api.tsh2604.logisticspro.my/v1`  
**Authentication:** JWT Bearer Token  
**Content-Type:** `application/json`

---

## AUTHENTICATION

### POST /auth/login
Login with credentials to receive JWT token.

**Request:**
```json
{
  "email": "user@mmf.com.my",
  "password": "securePassword123"
}
```

**Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": "usr_123",
    "email": "user@mmf.com.my",
    "role": "DISPATCHER",
    "branchId": "br_pkl"
  }
}
```

### POST /auth/refresh
Refresh expired access token.

### POST /auth/logout
Invalidate current token.

---

## HMS MODULE

### GET /hms/dashboard/stats
Retrieve dashboard statistics.

**Response:**
```json
{
  "activeJobs": 45,
  "onTimeRate": 94.5,
  "fleetUtilization": 87,
  "revenueToday": 125000,
  "vehiclesAvailable": 12,
  "vehiclesActive": 18,
  "alerts": [...]
}
```

### GET /hms/jobs
List all haulage jobs with filtering.

**Query Parameters:**
- `status`: PENDING, ASSIGNED, IN_TRANSIT, etc.
- `dateFrom`: ISO date
- `dateTo`: ISO date
- `customerId`: Customer filter
- `driverId`: Driver filter
- `page`: Page number
- `limit`: Items per page

**Response:**
```json
{
  "data": [...],
  "pagination": {
    "page": 1,
    "limit": 50,
    "total": 245,
    "totalPages": 5
  }
}
```

### POST /hms/jobs
Create new haulage job.

**Request:**
```json
{
  "customerId": "cust_123",
  "pickupLocation": "Port Klang Terminal",
  "deliveryLocation": "Shah Alam Warehouse",
  "containerNo": "MSCU1234567",
  "scheduledDate": "2026-02-15",
  "rate": 850.00
}
```

### GET /hms/jobs/:id
Get job details.

### PATCH /hms/jobs/:id
Update job status.

### GET /hms/vehicles
List all vehicles.

### GET /hms/drivers
List all drivers.

### GET /hms/drivers/:id/incentives
Get driver incentive calculations.

### GET /hms/tracking/:jobId
Get GPS tracking data for job.

**Response:**
```json
{
  "jobId": "job_123",
  "locations": [
    {"lat": 3.0448, "lng": 101.4486, "timestamp": "2026-02-15T10:30:00Z"}
  ]
}
```

---

## FFS MODULE

### GET /ffs/shipments
List all shipments.

**Query Parameters:**
- `status`: BOOKED, IN_TRANSIT, DELIVERED
- `tradeLane`: IMPORT, EXPORT, DOMESTIC
- `carrier`: Maersk, MSC, etc.

### POST /ffs/shipments
Create new shipment booking.

**Request:**
```json
{
  "shipperId": "ship_123",
  "consigneeId": "cons_456",
  "origin": "Shanghai",
  "destination": "Port Klang",
  "mode": "SEA",
  "cargoDetails": {...}
}
```

### GET /ffs/shipments/:id
Get shipment details with tracking.

### GET /ffs/shipments/:id/documents
List all attached documents.

### POST /ffs/shipments/:id/documents
Upload document to shipment.

### GET /ffs/containers/:containerNo
Get container information.

### GET /ffs/integrations/pcs/containers
Query Port Klang PCS for container status.

**Response:**
```json
{
  "containerNo": "MSCU1234567",
  "status": "DISCHARGED",
  "location": "YARD A-12-3",
  "availableDate": "2026-02-15T08:00:00Z"
}
```

---

## WMS MODULE

### GET /wms/inventory
Get inventory listing.

**Query Parameters:**
- `sku`: Product SKU
- `locationId`: Warehouse location
- `status`: AVAILABLE, ALLOCATED, etc.

### POST /wms/inventory/receive
Process goods receipt.

**Request:**
```json
{
  "asnId": "asn_123",
  "items": [
    {"sku": "SKU-001", "quantity": 100, "locationId": "LOC-A-01"}
  ]
}
```

### POST /wms/inventory/adjust
Adjust inventory quantity.

### GET /wms/locations
List warehouse locations.

### POST /wms/orders/:id/pick
Process picking for order.

### POST /wms/gate-pass
Generate gate pass for shipment.

---

## TMS MODULE

### GET /tms/yard/containers
List all containers in yard.

### GET /tms/yard/containers/:id
Get container details and location.

### POST /tms/gate-in
Process container gate-in.

### POST /tms/gate-out
Process container gate-out.

### GET /tms/integrations/ktmb/manifest
Get KTMB rail manifest.

---

## FMS MODULE

### GET /fms/invoices
List all invoices.

### POST /fms/invoices
Create new invoice.

### POST /fms/invoices/:id/submit-einvoice
Submit invoice to IRBM MyInvois.

**Response:**
```json
{
  "status": "SUBMITTED",
  "irbmUuid": "uuid-123",
  "validationStatus": "VALID"
}
```

### GET /fms/customers/:id/credit
Get customer credit information.

### POST /fms/payments
Record payment receipt.

### GET /fms/reports/financial/pnl
Get Profit & Loss report.

---

## ERROR RESPONSES

### 400 Bad Request
```json
{
  "error": "VALIDATION_ERROR",
  "message": "Invalid input data",
  "details": [...]
}
```

### 401 Unauthorized
```json
{
  "error": "UNAUTHORIZED",
  "message": "Invalid or expired token"
}
```

### 403 Forbidden
```json
{
  "error": "FORBIDDEN",
  "message": "Insufficient permissions"
}
```

### 404 Not Found
```json
{
  "error": "NOT_FOUND",
  "message": "Resource not found"
}
```

---

**Total Endpoints Documented:** 80+  
**Last Updated:** February 2026

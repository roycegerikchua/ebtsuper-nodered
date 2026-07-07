# EBTSuper Node-RED

Supervisory Node-RED instance for Eng Bee Tin operations. Runs on `ebtsuper.server.ubesvr.com` with SSO authentication.

## Features

### Core Dashboard
- **Supervisor's Menu** - Central dashboard with links to all tools
- **SSO Login** - UBEPOS SSO authentication (sso.server.ubesvr.com)
- **Service Worker** - PWA support for mobile install

### Tools

| Tool | Route | Description |
|------|-------|-------------|
| Branch OTP Challenge | `/totp` | Generate time-based OTP for branch access |
| POS Unlock Code | `/unlockpos` | Generate unlock codes for POS terminals |
| Change Password | `/pwdchange` | Change branch POS password |
| Remote Stocktake | `/stake` | Remote stock take monitoring |
| Cash Drawer Status | `/cdmonitor` | Live cash drawer monitoring |
| Cash Drawer Reports | `/cdmonitor/summary` | Cash drawer summary reports |
| Deactivate Staff | `/staff-inactive` | Deactivate staff POS login |
| Staff Management | `/staff-listing` | Admin staff management |
| Elevator Users | `/currentElevatorUsers` | Manage elevator access users |
| Safe Control | `/safectrl` | Safe timer control panel |
| Sales Analysis | `/sales-analysis` | Hourly sales analysis dashboard |
| Branch Pending Orders | `/BranchPendingOrders` | View pending branch orders |
| Shift Scheduling | `/shift-ui`, `/timekeeping` | Staff shift management |
| TTLock Integration | `/ttlock` | Smart lock management |

### External Links (from Dashboard)
- Stock Take Analysis
- PWD ID Checker
- Customer Complaints (CCFS)
- Branch Transfer Viewer
- Check Open Branches
- Branch Photo Monitoring
- Product Search
- Branch Stock Matrix
- Branch App Versions

### Admin-Only Tools
- Manage Elevator Users
- Truck Tracking
- Staff Management
- Safe Control
- Hourly Sales Analysis

## Tech Stack

- **Runtime:** Node-RED on Node.js
- **Auth:** JWT SSO via sso.server.ubesvr.com
- **Database:** MSSQL (192.168.27.27) + MySQL (192.168.111.112)
- **Proxy:** Nginx Proxy Manager at ebtsuper.server.ubesvr.com

## Deployment

Runs in Docker on the OMV host (192.168.111.112):

- **Container:** `SupervisorNodeRED`
- **Data:** `/root/branchKeyGen/`
- **Port:** Internal (proxied via NPM)
- **Restart:** `docker restart SupervisorNodeRED`

# AXIL — Factory Management Progressive Web App (PWA)

> **"AXIL — AN END TO SEARCH"**  
> Tailored for Garment Manufacturing & Wholesale Shirt Factory Operations.

---

## 🏭 Operational Factory Flow Overview

AXIL digitalizes every stage of the shirt manufacturing lifecycle:
1. **Fabric Inward**: Meters and rolls received in Godown.
2. **Cutting Master**: Lot number generated, design assigned, cut piece count entered.
3. **Jobber & Machine Allocation**: Cut pieces sent to Jobbers with 10–20 machines and divided among Karigars.
4. **Stitching & Time/Speed Recording**: Karigar taps **START WORK** (auto-records start timestamp) and **COMPLETE WORK** (auto-records end timestamp, calculates pieces/hour and earnings).
5. **Flexible Process Routing**: Automatic sequencing through Screen Printing / Embroidery / Washing / Gaaj-Button (Buttonholing & Buttoning) / Press & Packing.
6. **Department Handover & Shortage Spotting**: Receiving department counts pieces; missing pieces are immediately flagged against the sending department.
7. **Alterations Tracking**: Defective pieces logged against specific karigars with instant notification alerts.
8. **Dynamic Lot Cost Sheet**: Comprehensive calculation of Fabric + Cutting + Stitching + Washing + Gaaj-Button + Press/Packing + Accessories = Total Lot Cost & Cost per Piece.
9. **Finished Godown & Dispatches**: Stock inward, order progress, and dispatch tracking with Transport LR numbers and 1-click WhatsApp messaging.

---

## 🚀 How to Run the Application

### Option A: 1-Click Launch (Recommended for Owner)
Simply double-click the desktop launcher:
```bat
start_axil.bat
```
This automatically boots the FastAPI backend and opens `http://localhost:8000` in your web browser.

### Option B: Manual Command Line
From the project folder `C:\Users\stkab\.gemini\antigravity\scratch\axil-pwa`:
```powershell
py -m uvicorn backend.main:app --host 0.0.0.0 --port 8000 --reload
```

---

## 📱 Mobile Floor Installation (PWA on Android / iOS)

1. Connect the phone or tablet to the factory's local Wi-Fi network.
2. Open Chrome or Safari and enter `http://<YOUR_PC_LOCAL_IP>:8000/worker.html` (e.g. `http://192.168.1.15:8000/worker.html`).
3. Tap the browser menu (`⋮` or Share icon) &rarr; **"Add to Home Screen"** / **"Install App"**.
4. The **AXIL** app icon will appear directly on the worker's home screen and run as a standalone full-screen mobile app!

---

## 🔑 Default User Accounts

* **Owner / Admin**:
  * Username: `admin`
  * Password: `axil@2026`
  * Access: Full command center, all reports, costing, payments, attendance, and settings.
* **Worker / Karigar Quick PIN**:
  * PIN: `1234`
  * Select worker from the 1-tap list (e.g., Dinesh Kumar `KAR-101`, Suresh Prajapati `KAR-102`).
  * Access: Simplified touch interface, big tactile start/complete buttons, personal attendance, and alteration alerts.

---

## 🗄️ Database & Automated Backup

* **Database Engine**: SQLite 3 (`data/axil_factory.db`) with Foreign Keys and WAL Mode enabled.
* **To create an instant backup snapshot**:
  ```powershell
  py backend/backup.py
  ```
  Snapshots are saved to the `backups/` directory with automatic timestamps.

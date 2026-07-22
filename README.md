# 🤖 ShamScouting: FRC Offline Scouting Suite

Welcome to **ShamScouting**, a 100% offline-first, high-efficiency scouting ecosystem designed for FRC competitions. Built with pure HTML5, CSS3, and Vanilla JavaScript to ensure zero build overhead and instant loading over GitHub Pages.

---

## 🔗 Live Application Links

Bookmark or save these pages to your mobile device's **Home Screen** prior to arriving at the venue:

* 📱 **[Match Scouting Form](https://grahaml03.github.io/ShamScouting/match_scouting.html)**
  * *For stands scouts.* Fill out match performance data and generate a low-density, compressed QR code.
* 📷 **[Match Receiver Utility](https://grahaml03.github.io/ShamScouting/match_receiver.html)**
  * *For stands lead/tablet operator.* Scan stands scouts' QR codes, track match completion, and export data to a USB drive (`export_matches.csv`).
* 📋 **[Pit Scouting Form](https://grahaml03.github.io/ShamScouting/pit_scouting.html)**
  * *For pit scouts.* Collect physical robot metrics, mechanism specs, and auton preferences into a 'P|' payload QR code.
* 🛠️ **[Pit Receiver Utility](https://grahaml03.github.io/ShamScouting/pit_receiver.html)**
  * *For pit tablet operator.* Ingest pit scouting QR codes, track scouted teams index, and export to a USB drive (`pit_scouting_export.csv`).

---

## 🚀 How to Use (Offline Workflow)

### 1. Preparation (At Home / Hotel with Wi-Fi)
1. Open all required links above on your personal devices.
2. Select **"Add to Home Screen"** on Chrome/Safari to install as Progressive Web Apps (PWAs).
3. Confirm pages open completely without an internet connection.

### 2. Stand & Pit Data Transfer Pipeline
[Scout Phone] ──(Generates QR)──► [Receiver Tablet Webcam] ──(Exports CSV)──► [USB Drive] ──► [ShamStrategy Desktop]
1. **Scouting:** Scouts fill out forms after each match or pit visit. Clicking **Submit** displays a dense, low-light optimized QR code.
2. **Receiving:** Station the Receiver tablet continuously running the webcam scanner. Scan each scout's QR code.
   * 🟢 **Green Flash + High Tone:** Valid scan saved to storage.
   * 🔴 **Red Flash + Low Tone:** Duplicate or corrupt scan rejected.
3. **Pits Transfer:** Use the **Export to USB (.CSV)** button at regular intervals to dump records onto a physical flash drive for strategy integration into **ShamStrategy**.

---

## 💻 Tech Stack
* **Frontend:** Standalone HTML5 / CSS3 / Vanilla JS
* **Data Transfer:** Pipe-delimited ASCII string compression
* **Libraries:** `qrcodejs`, `html5-qrcode`, `PapaParse`
* **Storage:** LocalStorage & IndexedDB (Zero Cloud Dependencies)

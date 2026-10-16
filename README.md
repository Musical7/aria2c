# aria2c - High-Speed Command Line Downloader Guide

คู่มือและตัวอย่างคำสั่งการใช้งาน **aria2c** โปรแกรมช่วยดาวน์โหลดไฟล์ผ่าน Command Line แบบเปิดหลาย Connection เพิ่มความเร็วเต็มสปีด รองรับโปรโตคอล HTTP, HTTPS, FTP, SFTP, BitTorrent และ Metalink

---

## ⚡ คุณสมบัติเด่น
* **Multi-Connection Download:** แบ่งไฟล์ออกเป็นหลายส่วน (Segment) เพื่อดาวน์โหลดพร้อมกัน ช่วยเร่งความเร็วเต็มแบนด์วิดท์
* **Lightweight:** กินทรัพยากรเครื่องน้อยมาก ทำงานเบาและรวดเร็ว
* **Remote Control (RPC):** รองรับการเชื่อมต่อกับ Web UI (เช่น aria2-webui, AriaNg) หรือสคริปต์อัตโนมัติ
* **Resume Capability:** รองรับการดาวน์โหลดต่อจากจุดเดิมหากเน็ตตัดหรือหยุดชั่วคราว

---

## 📥 การติดตั้ง (Installation)

### Windows
* **ผ่าน Winget (แนะนำ):**

```

powershell
winget install aria2.aria2

```
* **ผ่าน Chocolatey:**

```

powershell
choco install aria2

```

### Linux (Ubuntu/Debian)

```

bash
sudo apt update && sudo apt install aria2 -y

```

---

## 🚀 คำสั่งใช้งานที่ใช้บ่อย (Usage Examples)

### 1. ดาวน์โหลดไฟล์ทั่วไป

```

powershell
aria2c "[https://example.com/file.zip](https://example.com/file.zip)"

```

### 2. ดาวน์โหลดเร่งสปีดสูงสุด (16 Connections)

```

powershell
aria2c -x16 -s16 "[https://example.com/file.zip](https://example.com/file.zip)"

```

### 3. ดาวน์โหลดพร้อมกำหนดโฟลเดอร์ปลายทาง

```

powershell
aria2c -x16 -s16 -d "D:\Downloads" "[https://example.com/file.zip](https://example.com/file.zip)"

```

### 4. ดาวน์โหลดพร้อมเปลี่ยนชื่อไฟล์ปลายทาง

```

powershell
aria2c -x16 -s16 -o "MyCustomName.zip" "[https://example.com/file.zip](https://example.com/file.zip)"

```

### 5. ดาวน์โหลดหลายไฟล์พร้อมกันจากรายการลิงก์ในไฟล์ข้อความ (links.txt)

```

powershell
aria2c -x16 -s16 -i links.txt

```

---

## 💻 ตัวอย่าง PowerShell Script (ดาวน์โหลดอัตโนมัติ)


```

powershell
$Url = "[https://example.com/largefile.zip](https://example.com/largefile.zip)"
$OutDir = "D:\Downloads"

aria2c -x16 -s16 -k1M --file-allocation=none -d $OutDir $Url

```

---

## ⚙️ สรุปตัวเลือกพารามิเตอร์สำคัญ (Options)

| Option | คำอธิบาย |
| :--- | :--- |
| `-x16` | จำนวน Connection สูงสุดต่อ 1 เซิร์ฟเวอร์ (ตั้งค่าได้สูงสุด 16) |
| `-s16` | แบ่งไฟล์ออกเป็นกี่ส่วน (Segment) สำหรับการดาวน์โหลดแบบขนาน |
| `-k1M` | ขนาดขั้นต่ำของแต่ละ Segment (ช่วยให้แบ่ง Segment ได้ถี่ขึ้น) |
| `-d` / `--dir` | กำหนด ไดเรกทอรี / โฟลเดอร์ ปลายทางสำหรับบันทึกไฟล์ |
| `-o` / `--out` | กำหนดชื่อไฟล์ปลายทางใหม่ |
| `-i` / `--input-file` | โหลดรายการ URL ทั้งหมดจากไฟล์ข้อความที่ระบุ |
| `--file-allocation=none` | ข้ามการจองพื้นที่ดิสก์ล่วงหน้า (ช่วยให้เริ่มดาวน์โหลดทันทีบน SSD/HDD) |
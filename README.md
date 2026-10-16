# aria2c

โปรแกรมช่วยดาวน์โหลดไฟล์ผ่าน Command Line ที่มีความเร็วสูง รองรับโปรโตคอล HTTP, HTTPS, FTP, SFTP, BitTorrent และ Metalink

---

## ⚡ คุณสมบัติเด่น
* **Multi-Connection Download:** แบ่งไฟล์ออกเป็นหลายส่วนเพื่อดาวน์โหลดพร้อมกัน ช่วยเพิ่มความเร็วเต็มสปีด
* **Lightweight:** ใช้ทรัพยากรเครื่องน้อยมาก
* **RPC Interface:** รองรับการเชื่อมต่อกับ Web UI หรือสคริปต์ภายนอก

---

## 🚀 คำสั่งใช้งานพื้นฐาน

### 1. ดาวน์โหลดไฟล์ทั่วไป
```bash
aria2c "[https://example.com/file.zip](https://example.com/file.zip)"

aria2c -x16 -s16 "[https://example.com/file.zip](https://example.com/file.zip)"

aria2c -x16 -s16 -d "D:\Downloads" "[https://example.com/file.zip](https://example.com/file.zip)"

aria2c -i links.txt

Option,ความหมาย
-x16,กำหนดจำนวนการเชื่อมต่อสูงสุดต่อ 1 เซิร์ฟเวอร์ (สูงสุด 16)
-s16,แบ่งไฟล์ออกเป็นกี่ส่วนในการดาวน์โหลดพร้อมกัน
-d / --dir,ระบุโฟลเดอร์สำหรับเซฟไฟล์ที่ดาวน์โหลด
-o / --out,ระบุชื่อไฟล์ปลายทางที่ต้องการเปลี่ยน
-i / --input-file,อ่านลิงก์ดาวน์โหลดจากไฟล์ข้อความ

---

### 📝 ขั้นตอนการบันทึกบน GitHub:
1. วางข้อความด้านบนลงในกล่องข้อความบรรทัดที่ 2 เป็นต้นไป[cite: 8]
2. พรีวิวดูความสวยงามโดยกดแท็บ **Preview** ข้างๆ ปุ่ม Edit ด้านบนซ้าย[cite: 8]
3. เมื่อพอใจแล้ว กดปุ่มสีเขียว **Commit changes...** ที่มุมขวาบนเพื่อบันทึกไฟล์ครับ[cite: 8]

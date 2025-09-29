# Medical Record Audit FE (Next.js)

ระบบตรวจสอบและประเมินเวชระเบียนของโรงพยาบาล  
A hospital system for auditing medical records.

## คุณสมบัติ
- Next.js (App Router) + Tailwind
- รองรับ basePath เช่น `/mra`
- เปลี่ยน API URL ได้หลัง ผ่าน `public/config.json`
- รันด้วย systemd หรือ PM2

---

## 1) เตรียมเครื่อง
- Node.js LTS (>= 18)
- Nginx (แนะนำให้ทำ reverse proxy)
- Git

```bash
node server.js 
```
> แก้ไขไฟล์ ที่อยู่ในโฟล์เดอร์ deploy / medical-record-audit.service ให้ตรงตาม linux ของผู้ใช้
---
## 2) รันคำสั่งเพื่อรัน
``` bash
sudo cp deploy/medical-record-audit.service /etc/systemd/system/
sudo systemctl daemon-reload
sudo systemctl enable medical-record-audit
sudo systemctl start medical-record-audit
sudo systemctl status medical-record-audit -n 50
```
---
### 3) สิทธิ์ไฟล์:
``` bash
sudo chown -R www-data:www-data /opt/medical-record-audit
```
# Maztech Garage V2 — GitHub Pages + Google Sheets

ไฟล์ชุดนี้ใช้สำหรับอัปโหลดขึ้น GitHub Pages repo `maztech-garage-v2`

## ไฟล์ที่ต้องอัปโหลดขึ้น GitHub

- `index.html`
- `README_TH.md`
- `.nojekyll`

## ไฟล์ที่ไม่ต้องอัปโหลดขึ้น GitHub

- `apps-script.gs`

ให้นำโค้ดใน `apps-script.gs` ไปวางใน Google Sheet ไฟล์ใหม่ที่เมนู:

Extensions > Apps Script

จากนั้น Deploy เป็น Web App แล้วนำ URL ที่ลงท้าย `/exec` มาใส่ใน `index.html` ตรงนี้:

```javascript
const CONFIG={
  API_URL:"วางลิงก์ Apps Script Web App ที่นี่",
```

## หลักการเชื่อมข้อมูลเวอร์ชันนี้

- Dashboard ดึงจากชีท `DASHBOARD_DATA` เท่านั้น
- งานซ่อมทั้งหมด ดึงจาก `Job_Header`
- รายละเอียดงานซ่อม ดึงจาก `Job_Detail`
- อะไหล่ / คลัง ดึงจาก `Parts_Master`
- ลูกค้า / รถ ดึงจาก `Customer_Master` และ `Vehicle_Master` หรือ `Car_Master`
- รายรับ-รายจ่าย ดึงจาก `Daily_Cashflow`
- Audit Log ดึงจาก `Audit_Log`
- Settings ดึงจาก `Settings` หรือ `Setup_Data`

## วิธีอัปโหลดขึ้น GitHub

1. เข้า repo `https://github.com/maztech-arch/maztech-garage-v2`
2. ถ้ามีไฟล์ `index.html` เดิม ให้กดเข้าไฟล์ แล้วกด Edit
3. ลบโค้ดเดิมทั้งหมด
4. วางโค้ดจากไฟล์ `index.html` ชุดนี้แทน
5. กด Commit changes
6. ไปที่ Settings > Pages
7. ตั้งค่า Source = Deploy from a branch
8. Branch = main
9. Folder = /root
10. กด Save

เว็บจะอยู่ที่:

https://maztech-arch.github.io/maztech-garage-v2/

## หมายเหตุสำคัญ

ถ้ายังไม่ได้ใส่ Apps Script URL เว็บจะใช้ข้อมูลตัวอย่างใน localStorage ก่อน
เมื่อใส่ Apps Script URL แล้ว ให้กดปุ่ม 🔄 บนแถบด้านบนเพื่อดึงข้อมูลจาก Google Sheet

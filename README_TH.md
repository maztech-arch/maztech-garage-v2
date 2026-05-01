# MazTech Garage Dashboard — GitHub Pages Ready

ไฟล์ชุดนี้ใช้สำหรับอัปโหลดขึ้น GitHub Pages เพื่อทำเว็บแอป Dashboard ของ MazTech Garage

## ไฟล์ในชุดนี้

- `index.html` = หน้าเว็บ Dashboard หลัก
- `apps-script.gs` = โค้ด Google Apps Script สำหรับอ่านชีท `DASHBOARD_DATA`
- `.nojekyll` = กันปัญหา GitHub Pages แปลงไฟล์ด้วย Jekyll

## วิธีใช้แบบสั้น

1. เปิด Google Sheet ของ MazTech Garage
2. ไปที่ Extensions > Apps Script
3. วางโค้ดจาก `apps-script.gs`
4. Deploy > New deployment > Web app
5. ตั้งค่า:
   - Execute as: Me
   - Who has access: Anyone
6. คัดลอก Web App URL ที่ลงท้าย `/exec`
7. เปิดไฟล์ `index.html`
8. แก้บรรทัดนี้:

```js
API_URL: ""
```

ให้เป็น:

```js
API_URL: "https://script.google.com/macros/s/xxxx/exec"
```

9. อัปโหลดไฟล์ทั้งหมดขึ้น GitHub repository
10. เปิด Settings > Pages
11. Source เลือก Deploy from a branch
12. Branch เลือก `main` และ folder เลือก `/root`
13. กด Save
14. รอไม่กี่นาที แล้วเปิดลิงก์ GitHub Pages

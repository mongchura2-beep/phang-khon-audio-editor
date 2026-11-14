# Phang Khon Audio Editor

เว็บไซต์แก้ไขเสียงบนเบราว์เซอร์ โดยนำซอร์สโค้ด AudioMass ต้นฉบับจากโครงการ `pkalogiros/AudioMass` สาขา `production` มาจัดเตรียมและเผยแพร่ผ่าน GitHub Pages พร้อมเปลี่ยนชื่อหน้าเว็บเป็น **Phang Khon Audio Editor**.

## สิ่งที่มีในชุดนี้

- GitHub Actions workflow สำหรับดาวน์โหลดซอร์ส AudioMass ล่าสุดและเผยแพร่ไปยัง GitHub Pages อัตโนมัติ
- ปรับชื่อหน้าเว็บและข้อมูล metadata เป็น Phang Khon Audio Editor
- ใช้ธีม Dark ที่มากับซอร์ส AudioMass ปัจจุบัน
- เก็บไฟล์ `LICENSE` และ `THIRD_PARTY_NOTICES.md` ของต้นฉบับไว้ในเว็บไซต์ที่เผยแพร่

> หมายเหตุ: ไฟล์โปรแกรม AudioMass จะถูกดึงจาก upstream ตอน GitHub Actions ทำงาน จึงไม่ต้องแนบซอร์สโค้ดต้นฉบับซ้ำใน ZIP นี้ และจะได้รุ่นล่าสุดจากสาขา production ในเวลาที่กด Deploy

## วิธีติดตั้งบน GitHub Pages

1. แตกไฟล์ ZIP นี้ลงในคอมพิวเตอร์
2. เข้า https://github.com แล้วสร้าง Repository ใหม่ เช่น `phang-khon-audio-editor`
   - แนะนำตั้งเป็น **Public** เพื่อใช้ GitHub Pages ฟรี
   - อย่าเลือก Add a README, .gitignore หรือ License เพราะมีไฟล์มาให้แล้ว
3. อัปโหลดไฟล์และโฟลเดอร์ทั้งหมดจาก ZIP เข้า Repository (ต้องเห็น `index.html`? ไม่ใช่ — ต้องเห็น `README.md` และโฟลเดอร์ `.github` อยู่ที่ระดับบนสุด)
4. กด **Commit changes**
5. ไปที่ **Settings → Pages**
6. ในส่วน **Build and deployment** เลือก Source เป็น **GitHub Actions**
7. ไปที่แท็บ **Actions** แล้วเปิด workflow ชื่อ **Deploy Phang Khon Audio Editor**
8. กด **Run workflow** หากยังไม่เริ่มทำงานอัตโนมัติ
9. เมื่อ workflow สำเร็จ เว็บไซต์จะอยู่ที่:
   `https://ชื่อผู้ใช้.github.io/ชื่อ-repository/`

ครั้งต่อไปที่มีการ push หรือแก้ไขไฟล์ใน branch `main` ระบบจะ Deploy ใหม่อัตโนมัติ

## ข้อกำหนดและเครดิต

AudioMass เป็นซอฟต์แวร์โอเพนซอร์สภายใต้ MIT License โดยผู้พัฒนา Pantelis Kalogiros โปรดคงไฟล์ `LICENSE` และ `THIRD_PARTY_NOTICES.md` ไว้ตามที่ workflow คัดลอกจาก upstream

- Upstream: https://github.com/pkalogiros/AudioMass
- Live project: https://audiomass.co
- License: https://github.com/pkalogiros/AudioMass/blob/production/LICENSE

ชื่อ Phang Khon Audio Editor เป็นชื่อหน้าเว็บที่นำมาใช้แสดงผล ไม่ได้หมายความว่าเป็นเจ้าของหรือผู้พัฒนา AudioMass ต้นฉบับ

## การอัปเดตเวอร์ชัน

workflow จะดาวน์โหลด branch `production` ทุกครั้งที่ deploy หากต้องการตรึงรุ่นเพื่อความคงที่ ควรเปลี่ยน URL ใน workflow ให้ชี้ไปยัง commit hash ที่ตรวจสอบแล้ว แทนการใช้ branch ล่าสุด

## การแก้ปัญหาเบื้องต้น

- ถ้า Actions ล้มเหลว ให้เปิด Actions → เลือกรายการที่ล้มเหลว → ดูขั้นตอน `Download AudioMass source` หรือ `Deploy to GitHub Pages`
- ถ้า Pages ยังไม่แสดง ให้ตรวจ Settings → Pages ว่าเลือก GitHub Actions แล้ว
- การบันทึกเสียงจากไมโครโฟนต้องเปิดเว็บผ่าน HTTPS และอนุญาตสิทธิ์ไมโครโฟนในเบราว์เซอร์
- การประมวลผลเสียงเกิดขึ้นในเบราว์เซอร์ของผู้ใช้ตามการทำงานของ AudioMass; ไม่ได้มีพื้นที่เก็บไฟล์เสียงบนเซิร์ฟเวอร์ของเว็บไซต์นี้

# GUARDIAN PBVS — Risk Intelligence

เว็บไซต์ React/Vite แบบ static สำหรับ `OrgGuard/GUARDIAN-PBVS-org` และเผยแพร่ด้วย **GitHub Actions → GitHub Pages เท่านั้น**

## ใช้งานในเครื่อง

```bash
npm ci
npm run dev
```

## ตรวจสอบ build

```bash
npm run build
npm run preview
```

## GitHub Pages deployment

ไฟล์ `.github/workflows/deploy-pages.yml` จะทำงานอัตโนมัติเมื่อมีการ push ไปยัง `main` หรือสั่งรันด้วยตนเองจากแท็บ **Actions** โดยจะ:

1. ติดตั้ง dependencies ด้วย `npm ci`
2. build เว็บไซต์ด้วย `npm run build`
3. อัปโหลดโฟลเดอร์ `dist` เป็น Pages artifact
4. deploy artifact ด้วย `actions/deploy-pages`

ใน repository settings ให้ตั้งค่า **Settings → Pages → Build and deployment → Source: GitHub Actions** เพียงครั้งเดียว หลังจากนั้นไม่ต้องใช้การ deploy จาก branch หรือการอัปโหลดไฟล์ `gh-pages` อีก

## หมายเหตุ

ไฟล์รูปภาพอยู่ใน `src/assets` แล้ว จึงไม่พึ่งพา Manus storage เดิม และ Vite ตั้งค่า `base: "./"` เพื่อรองรับทั้ง URL ของ repository และ custom domain

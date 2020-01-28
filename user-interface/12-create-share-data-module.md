
# สร้าง module สำหรับเก็บข้อมูลระหว่าง component

1. สร้างไฟล์ `src/models/share.tsx`

ประกาศตัวแปร เพื่อใช้เก็บข้อมูล และส่งออกไปใช้ใน Module อื่นๆ 

```ts
let shareValue:any = {}; 

export default shareValue; 
```
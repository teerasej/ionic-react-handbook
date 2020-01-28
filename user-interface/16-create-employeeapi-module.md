
# สร้าง EmployeeAPI module และเขียน function ส่งข้อมูลไป Web API

## สร้าง module สำหรับจัดการรับส่ง Request และ Response จาก Web API

สร้างไฟล์ `src/services/EmployeeAPI.tsx`

```ts
// เรียกใช้ Axios
import Axios from 'axios';

// กำหนด endpoint URL ของ Web API
const apiURL = 'http://localhost:3000';

// สร้าง function เพื่อเอาไปใช้งานใน module อื่นๆ 
// โดยมีการกำหนดรับค่าชื่อ นามสกุล และ email 
export const createEmployee = async (firstName: any, lastName: any, email: any) => {

    // กำหนด route URL 
    let routeURL = '/employees/create';

    // สร้าง 
    let newEmployee = {
        first_name: firstName,
        last_name: lastName,
        email: email
    }

    // กำหนดกรอบ try เพื่อดักจับ error ที่อาจเกิดขึ้น
    try {
        
        // ใช้ Axios ส่ง POST request โดยระบุ URL และส่ง JavaScript object ไปยัง Web API
        let result = await Axios.post(
            apiURL + routeURL,
            newEmployee
        );

        // คืนค่าที่ได้จาก web api ออกไปใช้งาน
        return result;
        
    } 
    // ถ้ามี error เกิดขึ้นในกรอบ try โค้ดในกรอบ catch จะทำงานทันที
    catch (e) {
        // ดูข้อมูล error ที่ได้ผ่าน console และส่งค่าออกไป
        console.log(e);
        return e;
    }

} 
```

## ไฟล์ **src/services/EmployeeAPI.tsx**

```ts
import Axios from 'axios';

const apiURL = 'http://localhost:3000';

export const createEmployee = async (firstName: any, lastName: any, email: any) => {

    let routeURL = '/employees/create';

    let newEmployee = {
        first_name: firstName,
        last_name: lastName,
        email: email
    }

    try {
        let result = await Axios.post(
            apiURL + routeURL,
            newEmployee
        );
        return result;
    } catch (e) {
        // console.log(e);
        return e;
    }

} 
```
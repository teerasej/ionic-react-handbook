
# เขียน function ร้องขอข้อมูลพนักงาน ใน EmployeeAPI module

เปิดไฟล์ **src/services/EmployeeAPI.tsx**

## เพิ่ม function สำหรับส่ง Request ไปขอข้อมูลจาก Web API

```js
export const getEmployees = async () => {

    // กำหนด Route URL
    let routeURL = '/employees';

    try {
        // ส่ง GET Request
        let result = await Axios.get(
            apiURL + routeURL
        );

        // คืนค่าที่ได้จาก Web API ออกไปใช้งาน
        return result;
    } catch (e) {
        // console.log(e);
        return e;
    }
} 
```

## ไฟล์ **src/services/EmployeeAPI.tsx**

```js

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

export const getEmployees = async () => {

    let routeURL = '/employees';

    try {
        let result = await Axios.get(
            apiURL + routeURL
        );
        return result;
    } catch (e) {
        // console.log(e);
        return e;
    }
}
```

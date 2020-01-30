
# เรียกใช้ Geolocation Feature ของ Capacitor

เปิดไฟล์ **src/pages/Home.tsx**

## 1. เรียกใช้ Capacitor plugins

```js
import { Plugins } from '@capacitor/core';
const { Geolocation } = Plugins;
```

## 2. เรียกใช้ Geolocation 

ตอนนี้จะมีปุ่มที่เรียกใช้ฟังก์ชั่น `startGetGPS` อยู่เราจะเรียกใช้คำสั่ง `Geolocation.getCurrentPosition()`

```js
const startGetGPS = async () => {
    console.log('getting gps');
    const coordinates = await Geolocation.getCurrentPosition();
    console.log('Current', coordinates);
}
```

ทดสอบใช้งานใน Ionic serve เพื่อทดสอบใช้งาน


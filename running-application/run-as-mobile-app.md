
# การรันโปรเจคแบบ Mobile Application

## ติดตั้ง module เพิ่มเติม

```bash
npm install -g ionic native-run
```

## 1. การ build ไฟล์โปรเจค เพื่อเอาลง Mobile Platform

1. เปิดโฟลเดอร์โปรเจคขึ้นมาใน Visual Studio Code
2. เปิด **Terminal > New Terminal**
3. รันคำสั่ง เพื่อเตรียมไฟล์ web สำหรับใช้งานใน Mobile Application

```bash
ionic build
```

เสร็จขั้นตอนนี้ จะได้โฟลเดอร์ **build** เพิ่มขึ้นมาในโปรเจค

## 2. เตรียม Mobile Platform สำหรับสร้างไฟล์แอพพลิเคชั่น

รันคำสั่ง เพื่อให้ Ionic ดาวน์โหลดโปรเจค mobile application มาไว้ในโปรเจค Ionic

### ติดตั้ง Android platform 

ต้องมีการ [setup Android SDK ให้เรียบร้อย](../1-setup-environment.md)

```bash
ionic capacitor add android
```

### ติดตั้ง iOS platform 

** ใช้ได้บนเครื่อง MacOS เท่านั้น และต้องมีการ [setup iOS SDK ให้เรียบร้อย](../1-setup-environment.md)

```bash
ionic capacitor add ios 
```

## 3. กำหนด Application ID 

1. เปิดไฟล์ `capacitor.config.json`
2. กำหนด `appId` ในรูปแบบของ Reverse Domain Name 

```json
{
  "appId": "io.ionic.starter",
  ...
}
```

เช่น 
- ถ้าเว็บไซต์องค์กรเราคือ **nextflow.in.th** สามารถเขียนเป็น `th.in.nextflow.app` ได้
- ถ้าเราไม่มีเว็บไซต์ ก็สามารถเขียนได้ในรูปแบบคล้ายกัน `com.teerasej.myapp`

## 4. ทดสอบรันแอพพลิเคชั่นบนอุปกรณ์จริง

- [ทดสอบบนอุปกรณ์ Android](run-on-android-device.md) 
- [ทดสอบบนอุปกรณ์ iOS](run-on-ios-device.md)
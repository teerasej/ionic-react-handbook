
# ทดสอบบนอุปกรณ์ Android 

- [ทดสอบบนอุปกรณ์ Android](#%e0%b8%97%e0%b8%94%e0%b8%aa%e0%b8%ad%e0%b8%9a%e0%b8%9a%e0%b8%99%e0%b8%ad%e0%b8%b8%e0%b8%9b%e0%b8%81%e0%b8%a3%e0%b8%93%e0%b9%8c-android)
  - [1. ปลดล๊อค Developer Option (ตัวเลือกนักพัฒนา) ใน Setting ของอุปกรณ์ Android](#1-%e0%b8%9b%e0%b8%a5%e0%b8%94%e0%b8%a5%e0%b9%8a%e0%b8%ad%e0%b8%84-developer-option-%e0%b8%95%e0%b8%b1%e0%b8%a7%e0%b9%80%e0%b8%a5%e0%b8%b7%e0%b8%ad%e0%b8%81%e0%b8%99%e0%b8%b1%e0%b8%81%e0%b8%9e%e0%b8%b1%e0%b8%92%e0%b8%99%e0%b8%b2-%e0%b9%83%e0%b8%99-setting-%e0%b8%82%e0%b8%ad%e0%b8%87%e0%b8%ad%e0%b8%b8%e0%b8%9b%e0%b8%81%e0%b8%a3%e0%b8%93%e0%b9%8c-android)
  - [2. รันโปรเจคในอุปกรณ์พกพา](#2-%e0%b8%a3%e0%b8%b1%e0%b8%99%e0%b9%82%e0%b8%9b%e0%b8%a3%e0%b9%80%e0%b8%88%e0%b8%84%e0%b9%83%e0%b8%99%e0%b8%ad%e0%b8%b8%e0%b8%9b%e0%b8%81%e0%b8%a3%e0%b8%93%e0%b9%8c%e0%b8%9e%e0%b8%81%e0%b8%9e%e0%b8%b2)
    - [เช็คการเชื่อมต่อ โดยใช้โปรแกรม ADBDriverInstaller](#%e0%b9%80%e0%b8%8a%e0%b9%87%e0%b8%84%e0%b8%81%e0%b8%b2%e0%b8%a3%e0%b9%80%e0%b8%8a%e0%b8%b7%e0%b9%88%e0%b8%ad%e0%b8%a1%e0%b8%95%e0%b9%88%e0%b8%ad-%e0%b9%82%e0%b8%94%e0%b8%a2%e0%b9%83%e0%b8%8a%e0%b9%89%e0%b9%82%e0%b8%9b%e0%b8%a3%e0%b9%81%e0%b8%81%e0%b8%a3%e0%b8%a1-adbdriverinstaller)
    - [ทำการ build ไฟล์โปรเจค](#%e0%b8%97%e0%b8%b3%e0%b8%81%e0%b8%b2%e0%b8%a3-build-%e0%b9%84%e0%b8%9f%e0%b8%a5%e0%b9%8c%e0%b9%82%e0%b8%9b%e0%b8%a3%e0%b9%80%e0%b8%88%e0%b8%84)
    - [การสร้าง Emulator](#%e0%b8%81%e0%b8%b2%e0%b8%a3%e0%b8%aa%e0%b8%a3%e0%b9%89%e0%b8%b2%e0%b8%87-emulator)
    - [วิธีการเปิดโปรเจคกับ Android Studio](#%e0%b8%a7%e0%b8%b4%e0%b8%98%e0%b8%b5%e0%b8%81%e0%b8%b2%e0%b8%a3%e0%b9%80%e0%b8%9b%e0%b8%b4%e0%b8%94%e0%b9%82%e0%b8%9b%e0%b8%a3%e0%b9%80%e0%b8%88%e0%b8%84%e0%b8%81%e0%b8%b1%e0%b8%9a-android-studio)
  - [การ Sync Project Android กับ Gradle](#%e0%b8%81%e0%b8%b2%e0%b8%a3-sync-project-android-%e0%b8%81%e0%b8%b1%e0%b8%9a-gradle)
  - [รันแอพพลิเคชั่นจากเมนู](#%e0%b8%a3%e0%b8%b1%e0%b8%99%e0%b9%81%e0%b8%ad%e0%b8%9e%e0%b8%9e%e0%b8%a5%e0%b8%b4%e0%b9%80%e0%b8%84%e0%b8%8a%e0%b8%b1%e0%b9%88%e0%b8%99%e0%b8%88%e0%b8%b2%e0%b8%81%e0%b9%80%e0%b8%a1%e0%b8%99%e0%b8%b9)

## 1. ปลดล๊อค Developer Option (ตัวเลือกนักพัฒนา) ใน Setting ของอุปกรณ์ Android

[ทำตามขั้นตอนใน Link นี้](https://nextflow.in.th/2014/enable-android-developer-option/) 

## 2. รันโปรเจคในอุปกรณ์พกพา

- ทำการ[เตรียมโปรเจคให้พร้อมสำหรับการรันแอพพลิเคชั่น](run-as-mobile-app.md)
- ทำการเชื่อมต่ออุปกรณ์พกพา เข้ากับ Computer ผ่านสาย USB สายที่ใช้ต้องเป็นสาย data ไม่ใช่สายชาร์จไฟอย่างเดียว

### เช็คการเชื่อมต่อ โดยใช้โปรแกรม ADBDriverInstaller

- [ดาวน์โหลดโปรแกรม ADBDriverInstaller.exe](https://www.dropbox.com/sh/w2j6m49qr0za1f2/AAC6fI6c0PYlTXZqQW9l4uI5a?dl=0) 

ถ้าเปิด **USB Debugging** ใน **Developer Option** ของมือถือ Android แล้วเครื่องคอมพิวเตอร์สามารถเห็นอุปกรณ์ Android ที่เชื่อมต่ออยู่ จะปรากฎรายชื่อในตารางของโปรแกรม ดังตัวอย่างด้านล่าง

ถ้ามี Driver ที่ใช้ได้ จะขึ้นไอคอนสีเขียวแบบภาพด้านล่าง

![androidadbdriverinstallerv21100887873](https://user-images.githubusercontent.com/85179/73062045-0c5fa000-3ece-11ea-9158-b6b8464431cf.jpg)


ถ้าไม่มี Driver ที่ใช้ได้ จะขึ้นไอคอนสีเหลือง หรือสีแดง แบบภาพด้านล่าง ให้กดปุ่ม **Install** เพื่อเริ่มการดาวน์โหลด และติดตั้ง Driver

![8f8160cace9cc7945a5d33db3d38fc90](https://user-images.githubusercontent.com/85179/73062009-fbaf2a00-3ecd-11ea-9d45-91b6bf45a567.jpg)

### ทำการ build ไฟล์โปรเจค

หากมีการเปลี่ยนแปลงโค้ดในโปรเจค และต้องการเอาไปใช้ใน Mobile application ให้รันคำสั่ง 

```bash
ionic capacitor copy android
```

### การสร้าง Emulator 

ถ้าต้องการรันทดสอบบน Emulator และยังไม่ได้สร้าง Android Virtual Device [ให้ทำตามขั้นตอนนี้](https://nextflow.in.th/2019/android-how-to-create-virtual-device-thai/)

> สามารถรันได้บน Hyper-V ถ้าใช้ Emulator เวอร์ชั่น 27.3.8 เป็นต้นไป และทำงานบน Windows 10 


### วิธีการเปิดโปรเจคกับ Android Studio 

เราสามารถสั่งเปิด Android Studio ได้จาก Terminal โดยใช้คำสั่ง 

```bash
ionic capacitor open android 
```

หรือ

```bash
npx cap open android
```


## การ Sync Project Android กับ Gradle

ถ้าไม่สามารถเลือกอุปกรณ์พกพา หรือ Emulator จากรายการได้ ให้ทำตามขั้นตอนต่อไปนี้

1. คลิกขวาที่โปรเจค Android
2. เลือกคำสั่ง **Synchronize 'android'**

![2020-01-24_20-20-53](https://user-images.githubusercontent.com/85179/73072183-2d80ba80-3ee7-11ea-80b0-3eec9a7eb966.png)

## รันแอพพลิเคชั่นจากเมนู

<img width="447" alt="Screen Shot 2020-01-25 at 22 32 44" src="https://user-images.githubusercontent.com/85179/73123455-b882b300-3fc2-11ea-9797-0fd5dddaede3.png">




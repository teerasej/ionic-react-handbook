
# ทดสอบบนอุปกรณ์ iOS

> ควรใช้อุปกรณ์ iOS เวอร์ชั่นอัพเดตล่าสุด และ Xcode เวอร์ชั่นอัพเดตล่าสุด 



## 1. เพิ่ม Developer Account ใน Xcode 

### 1.1 เปิด Preference ของ Xcode

1. เชื่อมต่ออุปกรณ์ iOS เข้ากับคอมพิวเตอร์ MacOS 
2. เปิดโปรแกรม Xcode 
3. เปิดเมนู Xcode > Preference 

![2020-01-23_22-53-21](https://user-images.githubusercontent.com/85179/73000367-5778a500-3e33-11ea-96a5-198275f94258.png)

### 1.2. เพิ่ม Developer Account 

1. เลือก Account
2. กดเพิ่ม account
3. เลือก Apple ID
4. กด Continue


![2020-01-23_22-56-30](https://user-images.githubusercontent.com/85179/73000734-e7b6ea00-3e33-11ea-93f6-fec339ac1e0c.png)

5. กรอก Apple ID ที่มี และรหัสผ่านให้เรียบร้อย

### 1.3. ถ้าเพิ่มสำเร็จ จะมีรายการเพิ่มในส่วนของ Account 

![2020-01-23_23-02-11](https://user-images.githubusercontent.com/85179/73001097-7af01f80-3e34-11ea-8434-3ae716258054.png)


## 2. เปิดโปรเจคในโปรแกรม Xcode

1. ทำการ[เตรียมโปรเจคให้พร้อมสำหรับการรันแอพพลิเคชั่น](run-as-mobile-app.md)
2. รันคำสั่งเพื่อเปิดโปรแกรม Xcode 

```bash
npx cap open ios
```

## 3. รันโปรเจคในอุปกรณ์พกพา

หลังจากเสียบอุปกรณ์ iOS เข้ากับ Mac ที่รัน Xcode อยู่

1. เลือก **Project Navigator > App**
2. เลือก **Target > App**
3. เลือก **Signing & Capabilities** 
4. เลือก **Developer Account** จากตัวเลือก **Team** และรอให้ Xcode ทำงานจนเสร็จ

![2020-01-25_22-37-16](https://user-images.githubusercontent.com/85179/73123817-adca1d00-3fc6-11ea-934d-8a7e5717e4b7.png)


5. เลือกส่วนของ Device หรือ Simulator จากรายการด้านบน และกดปุ่ม Run 

![2020-01-25_23-00-09](https://user-images.githubusercontent.com/85179/73123819-af93e080-3fc6-11ea-9e92-d831d5b1ab89.png)

## ในกรณีที่ยังไม่ได้จ่ายค่า Developer Account $99

เวลารันแอพบนเครื่อง iOS จะ pop up แจ้งใน Xcode ว่าให้เข้าไปตั้งค่าใน Setting > General > Device Management ไม่งั้นจะรันแอพบนเครื่องไม่ได้

ให้ไปที่ Setting > General 

![images](https://user-images.githubusercontent.com/85179/73123858-41035280-3fc7-11ea-883b-3e5cd86ce52e.jpg)

เลือกเข้า Device Management

![devicemanagement](https://user-images.githubusercontent.com/85179/73123885-7f990d00-3fc7-11ea-9cea-5fd70682c420.png)

เลือก Profile ของ Developer Account ที่เราใช้ใน Xcode

![Profiles](https://user-images.githubusercontent.com/85179/73123890-832c9400-3fc7-11ea-9deb-9b1f6c9d77d8.png)


กดเลือก Trust 

![sidebyside](https://user-images.githubusercontent.com/85179/73123893-87f14800-3fc7-11ea-9f37-2cbec7f30b4c.jpg)

จากนั้นให้กดรันแอพ จากใน Xcode อีกครั้ง
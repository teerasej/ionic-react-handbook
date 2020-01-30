
# กำหนด Permission เพื่อเข้าถึงอุปกรณ์

Permission คือการเขียนกำหนดการขอเข้าใช้ความสามารถต่างๆ ในมือถือของผู้ติดตั้งแอพ หากไม่ใส่ให้ถูกต้อง ตัวแอพจะไม่สามารถเรียกใช้งานความสามารถดังกล่าวได้

## Android 

1. เปิดไฟล์ **android -> app -> src -> main -> AndroidManifest.xml**
2. เช็คให้แน่ใจว่ามีโค้ด xml ด้านล่างอยู่ในไฟล์ ถ้าไม่มี ให้เพิ่มเข้าไป

```xml
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-feature android:name="android.hardware.location.gps" />
```

## iOS 

1. เปิดไฟล์ **iOS -> App -> App -> Info.plist**
2. เพิ่ม Permission ค่า 2 ค่านี้ใน `<dict>`

```xml
    ...
	<key>NSLocationWhenInUseUsageDescription</key>
	<string>Main</string>
	<key>NSLocationAlwaysUsageDescription</key>
	<string>Main</string>
</dict>
```

- `NSLocationWhenInUseUsageDescription`: ข้อความแสดงเมื่อขอเข้าใช้ตำแหน่งปัจจุบัน
- `NSLocationAlwaysUsageDescription`: ข้อความแสดงเมื่อขอเข้าใช้ตำแหน่ง ตลอดเวลา
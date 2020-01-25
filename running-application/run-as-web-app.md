
# การรันโปรเจคแบบ Web Application

1. เปิดโฟลเดอร์โปรเจคขึ้นมาใน Visual Studio Code
2. เปิด **Terminal > New Terminal**
3. รันคำสั่ง เพื่อเปิดการทำงานของ Web server

```bash
ionic serve
```

หาก Web server เปิดใช้งานแล้ว จะเป็น log แสดงขึ้นมาเป็น URL ของการเปิดเข้าชมเว็บแอพ และมีการเปิด Web Browser ด้วย

```bash
[react-scripts] You can now view MyApp in the browser.
[react-scripts]   Local:            http://localhost:8100/
[react-scripts]   On Your Network:  http://172.20.10.4:8100/
[react-scripts] Note that the development build is not optimized.
[react-scripts] To create a production build, use npm run build.

[INFO] Development server running!
       
       Local: http://localhost:8100
       
       Use Ctrl+C to quit this process

[INFO] Browser window opened to http://localhost:8100!
```

## การปิดการทำงานของ Web Server

1. คลิกเลือก Terminal 
2. กดปุ่มลัด Ctrl + C (ถ้ามีการถาม `Y/n` ให้พิมพ์ `Y` และกด enter)
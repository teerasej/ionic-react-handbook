
# การสร้างโปรเจค

## ระวังการใช้งานบน Windows

- Android มักจะมีปัญหากับ
  - ระบบ Windows ที่ตั้งภาษาของระบบเป็น**ภาษาไทย** 
  - วันเวลาเป็น **พุทธศักราช (พ.ศ.)**
  - ที่อยู่ path ของโปรเจค มีภาษาไทย
- หากพบปัญหาตอน build app android ให้ลอง
  - เปลี่ยนภาษาหลักของระบบ เป็น **ภาษาอังกฤษ​ (United State)**
  - ปรับวันเวลาเป็น **คริสตศักราช (ค.ศ.)**
  - ย้ายที่อยู่โฟลเดอร์โปรเจค ไปไว้ที่ๆ ไม่มีชื่อภาษาไทยใน path


## สร้างโปรเจคด้วย Visual Studio Code และ Terminal 

1. สร้างโฟลเดอร์ชื่อ **MyProject** ขึ้นมาใน Desktop
2. เปิดโฟลเดอร์ **MyProject** ขึ้นมาในโปรแกรม Visual Studio Code 
3. เปิดเมนู **Terminal > New Terminal**
4. รันคำสั่ง เพื่อเริ่มขั้นตอนการสร้างโปรเจค

```bash
ionic start
```

5. เมื่อถูกถามชื่อโปรเจค `? Project name:` ให้กรอก **CounterApp** และกด enter
6. เลือกโปรเจคเป็น **React**

```bash
Pick a framework! 😁

Please select the JavaScript framework to use for your new app. To bypass this
prompt next time, supply a value for the --type option.

? Framework: 
  Angular | https://angular.io 
❯ React   | https://reactjs.org 
```

7. เลือก Template โปรเจคเป็น **blank**

```bash
Let's pick the perfect starter template! 💪

Starter templates are ready-to-go Ionic apps that come packed with everything
you need to build your app. To bypass this prompt next time, supply template,
the second argument to ionic start.

? Starter template: (Use arrow keys)
❯ blank      | A blank starter project 
  sidemenu   | A starting project with a side menu with navigation in the conten
t area 
```

8. จากนั้นรอให้ระบบดาวน์โหลดไฟล์เพิ่มเติมมาให้เรียบร้อย จะเห็นข้อความดังนี้ 

```bash
[INFO] Next Steps:
       
       - Go to your newly created project: cd ./MyApp
       - Run ionic serve within the app directory to see your app
       - Build features and components: https://ion.link/scaffolding-docs
       - Run your app on a hardware or virtual device:
       https://ion.link/running-docs

Teerasej-MacBook-Pro:ionic-react-app teerasejjiraphatchandej$
```
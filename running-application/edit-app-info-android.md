
# การปรับแต่งตัวแอพ Android

## การเปลี่ยนชื่อ 

1. เปิดโปรเจคใน Android Studio ด้วยคำสั่ง Terminal จากในโฟลเดอร์โปรเจค

```bash
npx cap open android
```

2. จากโปรเจคที่เปิดใน Android Studio ให้เปิดเข้าไปในโฟลเดอร์ตามนี้ 

app -> res -> values -> strings.xml


```xml
<?xml version='1.0' encoding='utf-8'?>
<resources>
    <string name="app_name">LoginApp</string>
    <string name="title_activity_main">Nextflow App</string>
    <string name="package_name">th.in.nextflow.training.ionic.react</string>
    <string name="custom_url_scheme">th.in.nextflow.training.ionic</string>
</resources>
```

- `title_activity_main`: ชื่อแอพที่จะแสดงในอุปกรณ์ Android
- `package_name` และ `custom_url_scheme`: App Id และ URL Scheme
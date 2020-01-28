
# เขียนโค้ดเรียกข้อมูลพนักงาน ไว้ใน function ที่จะทำงานทุกครั้งที่เปิดหน้า Home

เปิดไฟล์ **src/pages/Home.tsx**

## 1. เรียกใช้ function จาก module เพิ่มเติม

```jsx
// เรียกใช้ function ชื่อ useIonViewDidEnter 
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem, IonButtons, IonButton, IonIcon, useIonViewDidEnter } from '@ionic/react';

// เรียกใช้ function ชื่อ getEmployees ที่สร้างไว้ก่อนหน้านี้ 
import { getEmployees } from '../services/EmployeeAPI';
```

## 2. เขียนโค้ดใน function ที่จะทำงานทุกครั้งที่ Component แสดงขึ้นมา

useIonViewDidEnter เป็น function พิเศษ ที่จะทำงานทุกครั้งที่ Component แสดงขึ้นมาบนแอพ 

ซึ่งเราสามารถเขียนโค้ดลงไปให้ทำงานตามกลไกดังกล่าวได้

```js
useIonViewDidEnter(async ()=>{
    console.log('Home page showed.');

    // ส่ง request เรียกข้อมูลพนักงานจาก web api
    let result = await getEmployees();

    // นำข้อมูลที่ได้ กำหนดให้กับตัวแปร state ที่ชื่อ contactArray
    setNewContactArray(result.data);
})
```

## 3. ปรับปรุงให้ JSX ใช้ข้อมูลแบบใหม่ที่ได้จาก Web API 

เพราะแบบเดิมข้อมูลใน Array เป็น String แต่ที่ส่งมาจาก Web API เป็น Object จึงต้องมีการปรับปรุงการเรียกใช้ใน JSX เพื่อไม่ให้เกิด error 

```jsx
let itemList = contactArray.map((item:any) => {
    return (
      <IonItem onClick={() => {
        shareValue.selected = item;
        history.push('/detail');
      }}>{item.first_name} {item.last_name}</IonItem>
    )
  })
```

## 4. ปรับปรุงหน้า Detail ในรูปแบบเดียวกัน 

เปิดไฟล์ **src/pages/Detail.tsx** 

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonBackButton, IonItem, IonLabel } from '@ionic/react';
import React from 'react';
import shareValue from '../models/share';

const DetailPage: React.FC = () => {

    // เปลี่ยนชื่อตัวแปรให้สื่อความหมายมากขึ้น 
    let employee = shareValue.selected;
    return (
        <IonPage>
            <IonHeader>
                <IonToolbar>
                    <IonButtons slot="start">
                        <IonBackButton></IonBackButton>
                    </IonButtons>
                    {/* แสดงชื่อในส่วนหัวของหน้า detail */}
                    <IonTitle>{employee.first_name}</IonTitle>
                </IonToolbar>
            </IonHeader>
            <IonContent className="ion-padding">
                {/* แสดงชื่อ */}
                <IonItem>
                    <IonLabel position="stacked">ชื่อ</IonLabel>
                    <p>{employee.first_name}</p>
                </IonItem>
                {/* แสดงนามสกุล */}
                <IonItem>
                    <IonLabel position="stacked">นามสกุล</IonLabel>
                    <p>{employee.last_name}</p>
                </IonItem>
                {/* แสดง Email */}
                <IonItem>
                    <IonLabel position="stacked">Email</IonLabel>
                    <p>{employee.email}</p>
                </IonItem>
            </IonContent>
        </IonPage>
    );
};

export default DetailPage;
```

# เก็บข้อมูลจาก Input ไว้ใน State ด้วย `useState` Hook

เปิดไฟล์ **src/pages/NewContact.tsx**

## 1. เรียกใช้ `useState` จาก `react` module 

```js
import React, { useState } from 'react';
```

## 2. ประกาศ state hook 

React Hook คือการกำหนดกลไกที่ทำงานกับ Component ได้หลากหลายรูปแบบ เช่นการกำหนดตัวแปร ที่สามารถอัพเดตตัวเองได้ ผ่าน function ที่กำหนด

ในที่นี้เราจะใช้ React hook ที่ชื่อ `useState` 

วิธีประกาศมีรูปแบบดังนี้ครับ

```js
const [ชื่อตัวแปร State, ชื่อ function ที่เอาไว้กำหนดค่าตัวแปร State ใหม่] = useState(ค่าเริ่มต้นของตัวแปร);
```

ในที่นี้ เราจะประกาศตัวแปรชื่อ `name` ที่มีค่าเริ่มต้นคือ `"..."` และสามารถกำหนดค่าใหม่ให้ตัวแปรได้ผ่าน function ชื่อ `setName`

```js
const [name, setName] = useState("...");
```

## 3. กำหนดใช้ค่าตัวแปร State ใน JSX 

เราจะเอาค่าตัวแปรมากำหนดให้กับ JSX `IonInput` ตัวที่ไว้กรอกชื่อพนักงาน

```jsx
<IonInput
    value={name}
></IonInput>
```

จะสังเกตว่าตอนแสดง UI ค่าเริ่มต้นของตัวแปร State จะแสดงในช่องกรอกชื่อ

## 4. สร้างกลไกอัพเดตค่าตัวแปร State เมื่อมีการเปลี่ยนแปลงข้อความใน `IonInput`

`IonInput` จะมี props ตัวหนึงที่กำหนด function ได้ ชื่อว่า `onIonChange` ซึ่งจะทำงานทุกครั้งที่ข้อมูลในช่องกรอกเปลี่ยนแปลง 

เราจะสร้าง function ขึ้นมา และเอามากำหนดใช้กับ 

```jsx
const onNameChange = (e:any) => {
    e.preventDefault();
    console.log(e.target.value);
}

<IonInput
    value={name} 
    onIonChange={onNameChange}
></IonInput>
```

โดยในที่นี้ เรามีการ log ดูค่าที่ได้จาก function ซึ่งก็คือข้อมูลที่กรอกลงในช่องนั่นเอง

## 5. ใช้ function `setName()` เพื่อกำหนดค่าที่ได้จาก `IonInput` ให้กับตัวแปร State

```jsx
const onNameChange = (e:any) => {
    e.preventDefault();
    console.log(e.target.value);
    setName(e.target.value);
}

<IonInput
    value={name} 
    onIonChange={onNameChange}
></IonInput>
```

ดังนั้นการกรอก หรือแก้ไขข้อความใน IonInput ที่ไว้กรอกชื่อ จะเป็นการเอาข้อความนั้นไปเก็บไว้ในตัวแปร state ที่ชื่อ name ด้วย

ตามที่ประกาศไว้ใน `useState` hook ตั้งแต่เริ่มต้น

```js
const [name, setName] = useState("...");
```

## 6. ดึงข้อมูลจากช่อง นามสกุลและ Email ด้วย useState แบบเดียวกัน 

```jsx
    const [name, setName] = useState("");
    const [lastName, setLastName] = useState("");
    const [email, setEmail] = useState("");

    const onNameChange = (e:any) => {
        e.preventDefault();
        console.log(e.target.value);
        setName(e.target.value);
    }

    const onLastNameChange = (e:any) => {
        e.preventDefault();
        console.log(e.target.value);
        setLastName(e.target.value);
    }

    const onEmailChange = (e:any) => {
        e.preventDefault();
        console.log(e.target.value);
        setEmail(e.target.value);
    }

    <IonInput
        value={name} 
        onIonChange={onNameChange}
    ></IonInput>

    <IonInput
        value={lastName} 
        onIonChange={onLastNameChange}
    ></IonInput>

    <IonInput type="email"
        value={email} 
        onIonChange={onEmailChange}
    ></IonInput>

```


## ไฟล์ **src/pages/NewContact.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonButton, IonIcon, IonItem, IonLabel, IonInput, IonFooter } from '@ionic/react';
import React, { useState } from 'react';
import { close } from 'ionicons/icons';
import { RouteComponentProps } from 'react-router';

const NewContactPage: React.FC<RouteComponentProps> = ({ history }) => {

    const [name, setName] = useState("");
    const [lastName, setLastName] = useState("");
    const [email, setEmail] = useState("");

    const onNameChange = (e:any) => {
        e.preventDefault();
        console.log(e.target.value);
        setName(e.target.value);
    }

    const onLastNameChange = (e:any) => {
        e.preventDefault();
        console.log(e.target.value);
        setName(e.target.value);
    }

    const onEmailChange = (e:any) => {
        e.preventDefault();
        console.log(e.target.value);
        setName(e.target.value);
    }

    return (
        <IonPage>
            <IonHeader>
                <IonToolbar>
                    <IonTitle>New Contact</IonTitle>
                    <IonButtons slot="end">
                        <IonButton onClick={() => history.goBack()}>
                            <IonIcon slot="icon-only" icon={close}></IonIcon>
                        </IonButton>
                    </IonButtons>
                </IonToolbar>
            </IonHeader>
            <IonContent>
                <IonItem>
                    <IonLabel position="stacked">ชื่อ</IonLabel>
                    <IonInput 
                        value={name} 
                        onIonChange={onNameChange}
                    ></IonInput>
                </IonItem>
                <IonItem>
                    <IonLabel position="stacked">นามสกุล</IonLabel>
                    <IonInput
                        value={lastName} 
                        onIonChange={onLastNameChange}
                    ></IonInput>
                </IonItem>
                <IonItem>
                    <IonLabel position="stacked">Email</IonLabel>
                    <IonInput type="email"
                        value={email} 
                        onIonChange={onEmailChange}
                    ></IonInput>
                </IonItem>

            </IonContent>
            <IonFooter className="ion-padding">
                <IonToolbar>
                    <IonButton expand="block">บันทึก</IonButton>
                </IonToolbar>
            </IonFooter>
        </IonPage>
    );
};

export default NewContactPage;
```
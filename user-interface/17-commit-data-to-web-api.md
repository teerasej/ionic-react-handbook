
# เรียกใช้งาน createEmployee function ตอนกดปุ่ม Save

เปิดไฟล์ **src/pages/NewContact.tsx**

## 1. สร้าง function ที่จะทำงานตอนกดปุ่ม Save 

```jsx
const onSubmit = () => {
       
}

<IonButton 
    expand="block"
    onClick={onSubmit}
>Save</IonButton>
```

## 2. เรียกใช้งาน createEmployee function จาก EmployeeAPI module 

```js
import { createEmployee } from '../services/EmployeeAPI';

const onSubmit = async () => {

    // ส่งตัวแปร State ทั้ง 3 ตัวให้กับ function
    let result = await createEmployee(name, lastName, email);

    // เช็คว่าถ้า result ที่ได้จาก function มีค่าชื่อ status ถือว่าสมบูรณ์ สั่งให้แอพเปิดกลับไปที่หน้าแอพก่อนหน้า
    // เพราะใน createEmployee() ถ้าเกิด error ขึ้นจะเป็นการ return error object ออกมา และ error object ไม่มีค่า status
    if(result.status != undefined){
        history.goBack();
    } else {
        // pop up ข้อความแทน
        alert('Cannot Save New Employee.' + result);
    }
}
```

## ไฟล์ **src/pages/NewContact.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonButton, IonIcon, IonItem, IonLabel, IonInput, IonFooter } from '@ionic/react';
import React, { useState } from 'react';
import { close } from 'ionicons/icons';
import { RouteComponentProps } from 'react-router';
import { createEmployee } from '../services/EmployeeAPI';

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
        setLastName(e.target.value);
    }

    const onEmailChange = (e:any) => {
        e.preventDefault();
        console.log(e.target.value);
        setEmail(e.target.value);
    }

    const onSubmit = async () => {
        let result = await createEmployee(name, lastName, email);

        if(result.status != undefined){
            history.goBack();
        } else {
            alert('Cannot Save New Employee.' + result);
        }
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
                    <IonButton 
                        expand="block"
                        onClick={onSubmit}
                    >บันทึก</IonButton>
                </IonToolbar>
            </IonFooter>
        </IonPage>
    );
};

export default NewContactPage;
```
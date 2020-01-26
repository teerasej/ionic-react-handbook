
# สร้างปุ่มปิดหน้า New Contact

เปิดไฟล์ **src/pages/NewContact.tsx**

## 1. เรียกใช้ module 

```js
// เรียกใช้ IonButtons, IonButton, IonIcon
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonButton, IonIcon } from '@ionic/react';
// เรียกใช้ Icon ชื่อ close มาแสดงในปุ่ม
import { close } from 'ionicons/icons';
// เรียกใช้ RouteComponentProps เพื่อมากำหนดให้ NewContactPage ใช้งาน history ได้
import { RouteComponentProps } from 'react-router';
```

## 2. กำหนด NewContactPage ให้สามารถใช้งาน History ได้

```js
const NewContactPage: React.FC<RouteComponentProps> = ({history}) => {
    ...
}
```

## 3. สร้างปุ่มปิดที่กำหนด Icon ลงไปใน IonToolbar

```html
<IonToolbar>
    <IonTitle>New Contact</IonTitle>
    <IonButtons slot="end">
        <IonButton onClick={() => history.goBack()}>
            <IonIcon slot="icon-only" icon={close}></IonIcon>
        </IonButton>
    </IonButtons>
</IonToolbar>
```


## ไฟล์ **src/pages/NewContact.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonButton, IonIcon } from '@ionic/react';
import React from 'react';
import { close } from 'ionicons/icons';
import { RouteComponentProps } from 'react-router';

const NewContactPage: React.FC<RouteComponentProps> = ({history}) => {

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
            <IonContent className="ion-padding">
                UI goes here...
            </IonContent>
        </IonPage>
    );
};

export default NewContactPage;
```
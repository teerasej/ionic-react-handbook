
# สร้าง Form


เปิดไฟล์ **src/pages/NewContact.tsx**

## 1. เรียกใช้ module 

```js
// เรียกใช้ IonItem, IonLabel, IonInput, IonFooter
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonButton, IonIcon, IonItem, IonLabel, IonInput, IonFooter } from '@ionic/react';
```

## 2. สร้าง web form 

```html
<IonContent>
    <IonItem>
        <IonLabel position="stacked">ชื่อ</IonLabel>
        <IonInput></IonInput>
    </IonItem>
    <IonItem>
        <IonLabel position="stacked">นามสกุล</IonLabel>
        <IonInput></IonInput>
    </IonItem>
    <IonItem>
        <IonLabel position="stacked">Email</IonLabel>
        <IonInput type="email"></IonInput>
    </IonItem>
</IonContent>
```

## 3. สร้างปุ่มบันทึก

```html
    ...
    </IonContent>
    <IonFooter className="ion-padding">
        <IonToolbar>
            <IonButton expand="block">บันทึก</IonButton>
        </IonToolbar>
    </IonFooter>
</IonPage>
```


## ไฟล์ **src/pages/NewContact.tsx**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButtons, IonButton, IonIcon, IonItem, IonLabel, IonInput, IonFooter } from '@ionic/react';
import React from 'react';
import { close } from 'ionicons/icons';
import { RouteComponentProps } from 'react-router';

const NewContactPage: React.FC<RouteComponentProps> = ({ history }) => {

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
                    <IonInput></IonInput>
                </IonItem>
                <IonItem>
                    <IonLabel position="stacked">นามสกุล</IonLabel>
                    <IonInput></IonInput>
                </IonItem>
                <IonItem>
                    <IonLabel position="stacked">Email</IonLabel>
                    <IonInput type="email"></IonInput>
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
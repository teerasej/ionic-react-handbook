
# สร้างหน้าแอพ สำหรับเพิ่มข้อมูล

1. สร้างไฟล์ **src/pages/NewContact.tsx**
2. ใช้ snippet **ir-page-component** ตั้งชื่อ Component ว่า **NewContactPage**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/react';
import React from 'react';

const NewContactPage: React.FC = () => {

    return (
        <IonPage>
            <IonHeader>
                <IonToolbar>
                    <IonTitle>Page Title</IonTitle>
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

# สร้างหน้า Detail Page

1. สร้างไฟล์ **src/pages/Detail.tsx**
2. ใช้ snippet **ir-page-component** และกำหนดชื่อ Component เป็น **DetailPage**

```jsx
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/react';
import React from 'react';

const DetailPage: React.FC = () => {

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

export default DetailPage; 
```
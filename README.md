# ionic-academy

Modulo 1: <br><br>
[Creazione di un nuovo progetto di Ionic 7](#1)<br>
[Principali Componenti Ionic 7 ](#2)<br>
[Styling e personalizzazione ](#3)<br>
Routing e navigazione<br>
Passaggio di parametri tra le “activity”<br>
Integrazione con servizi<br>
Utilizzo e consumo di API<br>
Lettura e scrittura json<br>
Lettura di risorse remote<br>
Apis (Background Runner, Browser, Device, Camera)<br>
Esempio di uso Apis Geolocation<br>
Ulteriori Apis Capacitor (Preferences, Push Notifications, Network)<br>
Componenti avanzate<br>
Creazione di app con uso dei sensori.<br>
Rilevazione del dispositivo web, android, iOS<br>
Introduzione a ionic capacitor<br>
Ionic Life Cycles<br><br>

___________________________________________________



Modulo 2:<br><br>
Principali Design Pattern<br>
Cordova e Ionic Capacitor<br>
Creazione plugins capacitor<br>
Capacitor: Librerie, sensori nativi, plugin;<br>
Elementi di intelligenza artificiale per migliorare lo sviluppo mobile<br>
Creazione di plugin personalizzati per estendere le funzionalità dell’applicazione.<br>
Integrazione dei plugin personalizzati con l’applicazione Angular/Ionic.<br>
Migrazione di plugin da Cordova a capacitor<br>
Esercitazioni sulla migrazione di plugin in capacitor<br>
Strategie di migrazioni possibili.<br>
Gestione degli hook<br>
Miscellaneous<br>
Breaking Change Ionic 8<br>
Progetto finale<br>
Compilazione per ios<br>
Compilazione per android<br>

_____________________________________


### 1
# Creazione di un nuovo progetto di Ionic 7



Per visionare la versione di ionic possibiamo utilizzare il comando 


```
ionic info
```

### Creazione di un Nuovo Progetto in Ionic 7

Per creare un nuovo progetto in Ionic 7, segui questi passaggi:

1. **Installazione di Node.js e npm**:
   Assicurati di avere Node.js e npm installati. Puoi scaricarli da [nodejs.org](https://nodejs.org/).

2. **Installazione di Ionic CLI**:
   Apri il terminale e installa l'Ionic CLI globalmente con il seguente comando:
   ```sh
   npm install -g @ionic/cli
   ```

3. **Creazione di un nuovo progetto**:
   Usa il comando `ionic start` per creare un nuovo progetto. Ad esempio, per creare un progetto chiamato "MyApp":
   ```sh
   ionic start MyApp blank
   ```
   Puoi sostituire `blank` con altri template come `tabs`, `sidemenu`, etc., a seconda delle tue esigenze.

4. **Navigazione nella directory del progetto**:
   ```sh
   cd MyApp
   ```

5. **Avvio dell'app in modalità di sviluppo**:
   ```sh
   ionic serve
   ```
   Questo comando avvierà un server di sviluppo e aprirà la tua nuova app nel browser.

### Principali Componenti di Ionic 7

Ionic 7 include una varietà di componenti predefiniti che puoi utilizzare per costruire la tua app.


1. **IonHeader**: Utilizzato per creare l'intestazione dell'app.
   ```html
   <ion-header>
     <ion-toolbar>
       <ion-title>Title</ion-title>
     </ion-toolbar>
   </ion-header>
   ```

2. **IonContent**: Contiene il contenuto principale dell'app.
   ```html
   <ion-content>
     <!-- Contenuto va qui -->
   </ion-content>
   ```

3. **IonButton**: Un bottone stilizzato.
   ```html
   <ion-button>Click Me</ion-button>
   ```

4. **IonList e IonItem**: Utilizzati per creare liste.
   ```html
   <ion-list>
     <ion-item>Item 1</ion-item>
     <ion-item>Item 2</ion-item>
   </ion-list>
   ```

5. **IonInput**: Un campo di input.
   ```html
   <ion-item>
     <ion-label>Input</ion-label>
     <ion-input></ion-input>
   </ion-item>
   ```

6. **IonCard**: Una scheda per contenuti visuali.
   ```html
   <ion-card>
     <ion-card-header>
       <ion-card-title>Card Title</ion-card-title>
     </ion-card-header>
     <ion-card-content>
       Card Content
     </ion-card-content>
   </ion-card>
   ```

### Styling e Personalizzazione

Ionic 7 utilizza CSS variables e il framework di stile predefinito per permettere la personalizzazione degli stili. Puoi sovrascrivere questi stili direttamente nel tuo file `src/theme/variables.scss`.

1. **Modifica delle Variabili CSS**:
   Le variabili CSS predefinite possono essere trovate e modificate nel file `variables.scss`. Ecco un esempio di come personalizzare il colore primario:
   ```scss
   :root {
     --ion-color-primary: #3880ff;
     --ion-color-primary-rgb: 56, 128, 255;
     --ion-color-primary-contrast: #ffffff;
     --ion-color-primary-contrast-rgb: 255, 255, 255;
     --ion-color-primary-shade: #3171e0;
     --ion-color-primary-tint: #4c8dff;
   }
   ```

2. **Utilizzo delle Classi CSS**:
   Puoi aggiungere classi CSS direttamente nei tuoi componenti per un'ulteriore personalizzazione.
   ```html
   <ion-button class="custom-button">Click Me</ion-button>
   ```
   E nel file CSS:
   ```css
   .custom-button {
     background-color: #ff5733;
     color: white;
   }
   ```

3. **Stile In-Line**:
   Puoi anche applicare stili in-line direttamente nei tuoi componenti HTML.
   ```html
   <ion-button style="background-color: #ff5733; color: white;">Click Me</ion-button>
   ```

4. **Uso di SCSS**:
   Ionic supporta SCSS (Sass), quindi puoi creare file SCSS per moduli di stile più complessi. Crea un nuovo file `.scss` e importalo nel tuo componente o globalmente.

   Esempio di file SCSS:
   ```scss
   .custom-button {
     background-color: #ff5733;
     color: white;
     &:hover {
       background-color: #e74c3c;
     }
   }
   ```

### Esempio di Applicazione Completa

```html
<!-- src/app/app.component.html -->
<ion-app>
  <ion-header>
    <ion-toolbar>
      <ion-title>
        My Ionic App
      </ion-title>
    </ion-toolbar>
  </ion-header>
  <ion-content>
    <ion-button class="custom-button">Click Me</ion-button>
    <ion-list>
      <ion-item>Item 1</ion-item>
      <ion-item>Item 2</ion-item>
    </ion-list>
  </ion-content>
</ion-app>
```

```scss
/* src/theme/variables.scss */
:root {
  --ion-color-primary: #3880ff;
  --ion-color-secondary: #0cd1e8;
  --ion-color-tertiary: #7044ff;
  /* Altre variabili di colore... */
}

/* src/app/app.component.scss */
.custom-button {
  background-color: #ff5733;
  color: white;
  &:hover {
    background-color: #e74c3c;
  }
}
```















_________________________________________

### 2
#  Principali Componenti Ionic 7


______________________________________

### 3
# Styling e personalizzazione





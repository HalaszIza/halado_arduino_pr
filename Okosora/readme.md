# OkosÓra - Egészségügyi monitor

![Plakát](okosora.png)

---
## Fehér led

📄 Leírás

Ez a fehér LED fény modul tökéletes választás Arduino kezdők számára. 🚀  
Könnyedén csatlakoztatható IO/Szenzor shieldhez, és lehetővé teszi fényhez kapcsolódó interaktív projektek megvalósítását. 💡✨

📝 Megjegyzés:
Más színű LED modulokat is választhatsz, például:
🟡 sárga, 🔴 piros, 🟢 zöld vagy 🔵 kék fényű változatot.

⚙️ Műszaki adatok
- 💡 Fehér LED modul
- 🔢 Típus: Digitális
- 🔌 Csatlakozó: PH2.54 aljzat
- 📏 Méret: 30 × 20 mm
- ⚖️ Tömeg: 3 g

Kapcsolási rajz:

![Kapcsolasi_rajz_1](kapcs_1.png)

Példakód:
``` cpp
int buzzPin = 7;    //Connect Buzzer on Digital Pin7
 void setup()  
 {        
  pinMode(buzzPin, OUTPUT);     
}
 void loop()                     
{
  digitalWrite(buzzPin, HIGH);
  delay(1000);
  digitalWrite(buzzPin, LOW); 
  delay(1000);        
}
```
## Pulzusmérő

📄 Leírás
Ez a modul egy nagyon tiszta infravörös LED-et 💡 és egy fototranzisztort 📷 használ arra, hogy észlelje az ujjadban lévő pulzust.

🫀 A piros LED a pulzusod ritmusára fog villogni!

⚙️ Működési elv
🔦 A fényes LED az ujjad egyik oldalára világít, miközben a fototranzisztor az ujjad másik oldalán méri, hogy mennyi fény jut át rajta.

🩸 Amikor a vér lüktet az ujjadon keresztül, a fototranzisztor ellenállása enyhén változik.
Ez a kis változás teszi lehetővé a pulzus észlelését.

Kapcsolási rajz:

![Kapcsolasi_rajz_2](kapcs_2.png)

Példakód:
``` cpp
int ledPin = 13;
int sensorPin = 0;
double alpha = 0.75;
int period = 20;
double change = 0.0;

void setup()
{
 pinMode(ledPin, OUTPUT);
 Serial.begin(9600);
}
void loop()
{
 static double oldValue = 0;
 static double oldChange = 0;
 int rawValue = analogRead(sensorPin);
 double value = alpha * oldValue + (1 - alpha) * rawValue;
 Serial.print(rawValue);
 Serial.print(",");
 Serial.println(value);
 oldValue = value;
 delay(period);
}
```

## Alkoholszenzor



## Hőmérséklet mérő


## Mátrix led



---
# Teljes rendszer


# Extra feladat

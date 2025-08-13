# Stopperóra LCD kijelzővel és RGB Leddel

![Plakat](stopper_lcd.png)

---

## Gomb 🔘

**📘 Leírás:** Ez egy alap nyomógomb modul 🟠. Egyszerűen bedugható egy IO shield-be, így ideális az első Arduino próbálkozásokhoz 🤖.

**✨ Jellemzők:**
- Széles feszültségtartomány: 3.3V – 5V 🔋
- Könnyen felismerhető érzékelő interfészek – „A” az analóg, „D” a digitális jelekhez 📟
- Szabványos rögzítő furat 🔩
- Áttekinthető ikonokkal jelölve 👀
- Magas minőségű csatlakozó 🔌
- Egyszerűen csatlakoztatható és használható 🧩
- Nagyméretű gomb és strapabíró gombfedél 🔘
- Kiváló interaktív és kreatív projektekhez 🎮🎨

**⚙️ Specifikáció:**
- Tápfeszültség: 3.3V – 5V 🔋
- Interfész: Digitális 📟
- Méretek: 30 × 20 mm 📏
- Tömeg: 4 g ⚖️

**Kapcsolási rajz:**

![Kappcsolási rajz_2](kapcs_2.png)

**Példakód:**
``` cpp
////////////////////////////////////////////////////////////////////
/* # When you push the digital button, the Led on the board will be turned on. Otherwise,the led is turned off.
*/
int redled = 10; // initialize digital pin 10.
int yellowled = 9; // initialize digital pin 9.
int greenled = 8; // initialize digital pin 8.
int inputPin = 5;               // Connect sensor to input pin 5
void setup() {
  pinMode(redled, OUTPUT);      // set LED as output
  pinMode(yellowled, OUTPUT);
  pinMode(greenled, OUTPUT);
  pinMode(inputPin, INPUT);     // set pushbutton as input
}
void loop(){
  int val = digitalRead(inputPin);  // read input value
  if (val == HIGH) {            // check if the input is HIGH
    digitalWrite(redled, LOW);  // turn LED OFF
    digitalWrite(yellowled, LOW);
    digitalWrite(greenled, LOW);
  } else {
    digitalWrite(redled, HIGH); // turn LED ON
    digitalWrite(yellowled, HIGH);
    digitalWrite(greenled, HIGH);
  }
}
////////////////////////////////////////////////////////////////////
```

## RGB Led

Leírás 📘

Ez egy teljes színskálás LED modul 🌈, amely három alapszínt tartalmaz – piros 🔴, zöld 🟢 és kék 🔵. Ezek különálló LED fényekként láthatók.

Programozás után a LED-eket sorrendben be- és kikapcsolhatod 💡, vagy PWM (impulzusszélesség-moduláció) analóg kimenetet is használhatsz arra, hogy a három színt összekeverve különböző színeket hozz létre 🎨.

Specifikáció ⚙️
- Színek: piros 🔴, zöld 🟢, kék 🔵
- Fényerő: magas ✨
- Feszültség: 5V 🔌
- Bemenet: digitális szint 💻
- Méret: 30 × 20 mm 📏
- Tömeg: 3g ⚖️

Kapcsolási rajz:

![Kapcsolasi_rajz_2](kapcs_2.png)

Példakód:
``` cpp
///////////////////////////////////////////////////////////
int redpin = 9;   // Piros LED a 9-as lábra kötve
int greenpin = 10; // Zöld LED a 10-es lábra kötve
int bluepin = 11;  // Kék LED a 11-es lábra kötve
void setup() {
  pinMode(redpin, OUTPUT);
  pinMode(greenpin, OUTPUT);
  pinMode(bluepin, OUTPUT);
}

void loop() {
  digitalWrite(redpin, HIGH);   // Piros LED bekapcsol
  digitalWrite(greenpin, LOW);  // Zöld LED kikapcsol
  digitalWrite(bluepin, LOW);   // Kék LED kikapcsol
  delay(1000);                  // Vár 1 másodpercet

  digitalWrite(redpin, LOW);    // Piros LED kikapcsol
  digitalWrite(greenpin, HIGH); // Zöld LED bekapcsol
  digitalWrite(bluepin, LOW);   // Kék LED kikapcsol
  delay(1000);                  // Vár 1 másodpercet

  digitalWrite(redpin, LOW);    // Piros LED kikapcsol
  digitalWrite(greenpin, LOW);  // Zöld LED bekapcsol
  digitalWrite(bluepin, HIGH);  // Kék LED bekapcsol
  delay(1000);                  // Vár 1 másodpercet
}


///////////////////////////////////////////////////////////
```

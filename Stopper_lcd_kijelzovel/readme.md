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

##

# Közlekedést irányító rendszer

![Feladat leírás](kozlekedes_iranyitas.png)

> Linkek: https://docs.keyestudio.com/projects/KS0522/en/latest/KS0522.html#projects

---
## Közlekedési lámpa 🚥🚦

**📘 Leírás:** A mikrokontroller tanulása során gyakran használnak három LED-et – piros 🔴, zöld 🟢 és sárga 🟡 fényeket – a közlekedési lámpa villogásának szimulálására külső kapcsolatokkal.  

Ezúttal egy különleges modult terveztünk, amely nagyon kényelmes a bekötés szempontjából, és a modulon megtalálható a piros 🔴, sárga 🟡 és zöld 🟢 LED is.  

Ez a modul teljes mértékben kompatibilis az Arduino mikrokontrollerrel 🤖 és a Raspberry Pi rendszerrel 🍓.  

**⚙️ Specifikáció:**
- Működési feszültség: 3.3–5V 🔋
- Interfész típusa: digitális 📟
- Csatlakozó: PH2.54 🔌

**Kapcsolási rajz:**

![Kapcsolási rajz_1](kapcs_1.png)

**Példakód:**
``` cpp
////////////////////////////////////////////////////////////////////
int redled = 10; // initialize digital pin 10.
int yellowled = 9; // initialize digital pin 9.
int greenled = 8; // initialize digital pin 8.
void setup()
{
pinMode(redled, OUTPUT);// set the pin with red LED as “output”
pinMode(yellowled, OUTPUT); // set the pin with yellow LED as “output”
pinMode(greenled, OUTPUT); // set the pin with green LED as “output”
}
void loop()
{
digitalWrite(greenled, HIGH);//// turn on green LED
delay(5000);// wait 5 seconds
digitalWrite(greenled, LOW); // turn off green LED
for(int i=0;i<3;i++)// blinks for 3 times
{
delay(500);// wait 0.5 seconds
digitalWrite(yellowled, HIGH);// turn on yellow LED
delay(500);// wait 0.5 seconds
digitalWrite(yellowled, LOW);// turn off yellow LED
} 
delay(500);// wait 0.5 seconds
digitalWrite(redled, HIGH);// turn on red LED
delay(5000);// wait 5 seconds
digitalWrite(redled, LOW);// turn off red LED
}
////////////////////////////////////////////////////////////////////
```

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

## Servo motor

**🧾 Bevezetés:**
A szervómotor egy pozícióvezérelt forgó működtető egység. ⚙️
Fő részei a következők:
- burkolat 🧱
- áramköri lap 🧩
- mag nélküli motor 🔄
- fogaskerekek ⚙️
- pozícióérzékelő 🎯

A szervómotorhoz különböző fehér motorfelfogató elemek tartoznak, amelyek a motor tengelyére rögzíthetők. ⚪🔩
A kívánt felfogatót szabadon választhatod ki az áramkörhöz. Ez vizuális segítségként szolgál, hogy könnyebben megfigyelhesd a motor forgását 🔁👀.

A szervón három csatlakozó található, amelyeket általában színkód különböztet meg (ez márkánként eltérhet):
- Barna – földelés (GND) 🟤⚡
- Piros – tápfeszültség (5V) 🔴🔌
- Narancssárga – vezérlő jel (PWM jel) 🟠📶

🔄 A szervó forgási szögének vezérlése
A szervó forgási szögét a PWM (Pulse-Width Modulation – impulzusszélesség-modulációs) jel kitöltési tényezőjének szabályozásával lehet vezérelni. 📶⚡
A PWM jel szabványos ciklusa 20 ms (azaz 50 Hz), a pulzusszélesség 1 ms és 2 ms között változik.
Ez a pulzusszélesség felel meg a forgási szögnek, ami általában 0°–90° között van. 🔁📏

**Kapcsolási rajz:**

![Kapcsolási rajz_3](kapcs_3.png)

**Példakód:**
``` cpp
//////////////////////////////////////////////////////////
#include <Servo.h>

Servo servo;

void setup() {
  szervo1.attach(6);
}

void loop() {
  for (int fok = 0; fok <= 180; fok += 5) {
    szervo1.write(fok);
    delay(100);
  }
}
```
> A servo motor mozgását adja meg.

# A végleges rendszer

🛠️ Feladat: Egy vasúti átkelőhely működését modellezzük két közlekedési lámpa, egy sorompó és egy vonat érkezését/távozását figyelő gombok segítségével. A rendszer standby üzemmóddal is rendelkezik, amely jelzi a rendszerszünetet.

🔹 Rendszer elemei:
- 🚥 Két közlekedési lámpa (váltakozó működéssel).
- 🚧 Sorompó szervomotorral vezérelve.
- 🚆 Vonat érkezése és távozása gombnyomásra.
- 🔄 Standby mód, amely sárga villogással jelzi a rendszerszünetet.

🚀 Program működése:
- Standby mód 🟡 – A gomb megnyomásával a sárga lámpák villognak, és a rendszer megáll.
- Vonat érkezése 🚆 – A gomb megnyomásával a sorompó leereszkedik.
- Vonat távozása 🚄 – A másik gombbal a sorompó felemelkedik.
- Lámpák váltakozása 🚥 – Az egyik lámpa piros, a másik zöld, majd 4 másodpercenként cserélnek.
- Automatikus időzítés ⏳ – millis() segítségével történik, így nincs delay() blokkolás.

**Kapcsolási rajz:**

![Kapcsolási rajz_4](kapcs_4.png)
> Egy kis segítség. Használj switch case-t a lámpák színeinek állapotának változásához.

# Extra feladat:

🚀 Extra feladat 💡🔧 Ha elkészült az alap projekt, és van kedved feltúrbózni, itt egy gondolkodós kihívás! 🤔

💡 Adott egy lámpapárral 🔴🟢 és sorompóval 🚧 létrehozott rendszer. Bővítsd ki a rendszert úgy, hogy minden automatikusan működjön, emberi beavatkozás nélkül! 🔄

**Interaktív LED & szervó 🎛️**
Cél: A meglévő 3 gomb és a szervó használatával készíts interaktív rendszert, ahol a LED-ek és a szervó együtt reagálnak.

Alpontok:
- Gomb 1 – LED-mód 🟡
Nyomva tartva a LED szekvencia leáll, és a sárga LED folyamatosan világít.
Felengedéskor a szekvencia újraindul.

- Gomb 2 – Szervó előre ↗️
A szervó 0° → 180°, blokkolásmentesen, a LED-ek tovább működnek.

- Gomb 3 – Szervó vissza ↘️
A szervó 180° → 0°, blokkolásmentesen.
Ha mindkét gomb egyszerre nyomva, a szervó nem mozdul, LED-ek tovább futnak.

- Extra kihívás ⚡
A LED szekvencia sebessége a gomb nyomásának hosszától függjön (hosszabb nyomás → gyorsabb LED-ek).

✅ Sok sikert! 😊

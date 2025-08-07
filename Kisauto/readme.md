# Vonalkövető kisautó

![Feladat kiírás:](kisauto.png)
> Linkek:    
> https://docs.keyestudio.com/projects/KS0522/en/latest/

## Feladat leírása:
🛠️ Fő funkciók:
- ⚙️ A szenzorok (pl. infravörös érzékelők) segítségével a vonal érzékelése
- 🔄 A motorok vezérlése a vonal követéséhez
- 🧠 Az irányító logika (pl. Arduino kód) megírása
- 🔋 Energiaellátás biztosítása
- 🧪 Tesztelés különböző pályákon

🎯 Cél:
- Megbízható, folyamatos vonalkövetés
- Gyors reagálás kanyarokra és elágazásokra
- Egyszerű, áttekinthető programkód

### Ultrahangos érzékelő működése:

![Kapcsolási rajz](kapcsolas.png)

``` cpp
//**********************************************************************************

const int TrigPin = 31; // Trig megadása, melyik lábra van kötve
const int EchoPin = 30; // Echo megadása, melyik lábra van kötve

int duration = 0; // Állítsd be a 'duration' (időtartam) kezdeti értékét 0-ra
int distance = 0;// Állítsd be a 'distance' (távolság) kezdeti értékét 0-ra

void setup() 
{
  pinMode(TrigPin , OUTPUT); // kimeneti módba áll a TrigPin
  pinMode(EchoPin , INPUT); // bemeneti módba áll az EchoPin
  Serial.begin(9600);  // A soros monitort 9600 baud sebessége, hogy lásd a pingelés eredményét
}
void loop()
{
 // Állítsd a trigPin-t magas szintre 10 mikrosecundum (10 μs) ideig, hogy aktiváld a HC-SR04 szenzort.
  digitalWrite(TrigPin , HIGH);
  delayMicroseconds(10);
  digitalWrite(TrigPin , LOW);

  // Várd meg, amíg a HC-SR04 visszatér magas szintre, és mérd meg ezt a várakozási időt.
  duration = pulseIn(EchoPin , HIGH);

  // Számítsd ki a távolságot az idő alapján
  distance = (duration/2) / 28.5 ;
  Serial.print("Distance: ");
  Serial.print(distance); // Írasd ki a távolság értékét a soros portra.
  Serial.println("cm");
  delay(300); // Várj 100ms két pingelés között (kb 20 pings/sec).
}
//**********************************************************************************
```

### OSOYOO szenzor működése

📦 Áttekintés – OSOYOO 5-csatornás IR követőszenzor  
Az OSOYOO 5-csatornás IR vonalkövető szenzor egy olyan modul, amely öt infravörös (IR) érzékelőt tartalmaz, és digitális bitekként olvassa azokat. 🔍

Ez a szenzor alkalmas összetett környezetekhez is:  
🔧 A beépített érzékenység-szabályzó potenciométerrel állítható a kioldási küszöb, az aktuális körülményekhez igazítva.
📏 Az 5 csatornás IR érzékelő egyszerre képes érzékelni:
- a középső követési vonalat,
- valamint a bal és jobb széleket is.

🛠️ A szenzort csavarokkal és réz- vagy szegecskötéssel könnyedén felszerelhetjük egy okosautóra, így nagy pontosságú vonalkövetés valósítható meg.

💡 Működési elv  
Ez az IR szenzor ITR9909 érzékelőket használ a színek és távolság észleléséhez.  

🔁 Az elv a következő:
Az infravörös fény különböző mértékben verődik vissza a felületekről:
- a fehér szín visszaveri a fényt 🤍,
- a fekete elnyeli azt ⚫.

Az eszköz a visszavert fény erősségét alakítja át áramjellé, így tudja érzékelni a felületet.

- 📍 Fehér felület esetén: magas (HIGH) szintet érzékel
- 📍 Fekete felület esetén: alacsony (LOW) szintet érzékel
- 🔎 Érzékelési magasság: 0–3 cm

A panelen három ITR9909 csoport található, így a bekötés és vezérlés is egyszerűbb.
🛠️ A potenciométer tekerésével állíthatod a szenzor érzékenységét:
- 👉 az óramutató járásával megegyezően növeled,
- 👉 ellenkező irányban csökkented.

⚙️ Hardverfelépítés
Az érzékelőpanel (PCB) fontosabb részei:
- IR adó-vevők (ITR9909) – kibocsátják és érzékelik az infravörös sugárzást 🔦
- Tápellátás jelző LED – ha 5V/3.3V tápfeszültséget kap, világít 🔋💡
- Működési visszajelző LED-ek – ha fekete felületet észlel (LOW jel), a piros LED világít, és az OUT láb LOW szintet ad 🔴
- Érzékenység-potenciométer – tekerhető, beállítható vele az érzékelési távolság
- 74HC14D chip – egy Schmitt-trigger bemenetű hatos inverter, ami segít a gyenge bemeneti jeleket tisztán, digitálisan értelmezhető jellé alakítani

Kimeneti interfészek –
- VCC: 5V vagy 3.3V
- GND: földelés
- IR1-IR5: digitális I/O jelek
- Rögzítő furat – az érzékelő stabil rögzítéséhez 🔩

📐 Főbb jellemzők
- 🔌 Működési feszültség: 3.3–5V DC
- 🔍 5-csatornás érzékelő, egy vonalban elhelyezve
- 📏 Digitális, tiszta kimenet (LOW szint, ha észlel)
- ⚫ Kifejezetten érzékeny sötét felületre (fekete)
- 💡 Beépített LED-ek visszajelzéshez
- 🛠️ Állítható érzékenység (potenciométerrel)
- 📶 TTL-szintű digitális jelek
- 📏 Érzékelési magasság: 0–3 cm
- 🔧 M3 méretű rögzítési lehetőség (rugalmasan szerelhető)

🧠 Mi az elv a vonalkövető robot mögött?
A vonalkövető robot működése a fény és színek viselkedésén alapul.
🌈 Tudnod kell:
- a fehér felület visszaveri,
- a fekete felület elnyeli az infravörös fényt.

Ezt a különbséget használjuk ki a robot irányításához. 🤖

⚙️ Hogyan működik?
Ebben a projektben két IR érzékelő modult használunk – egyet balra, egyet jobbra:
- 🤍 Ha mindkét szenzor fehér felületet érzékel → a robot egyenesen előre halad.
- ⚫ Ha a bal érzékelő fekete vonalra ér → a robot balra fordul.
- ⚫ Ha a jobb érzékelő fekete vonalra ér → a robot jobbra fordul.
- 🤍 Ha újra fehér felületet érzékelnek → a robot tovább halad előre.
- ⚫⚫ Ha mindkét szenzor fekete vonalat észlel → a robot megáll. 🛑

🚗 Alkalmazások
Ez a típusú IR szenzor széles körben használt:
- 🧭 akadálykerülő robotokban,
- 🚘 okosautókban,
- 🏭 gyártósoros számlálásban,
- 🛤️ fekete-fehér vonalkövetéshez.

---
> Illetve innen kicsit részletesebben tudsz tájékozódni a szenzor és az autó működéséről:
> https://osoyoo.com/2022/07/05/v2-metal-chassis-mecanum-wheel-robotic-for-arduino-mega2560-lesson3-5-point-line-tracking/
---
Egy kis segítség, ha esetleg nagyon elakadnátok:  
https://github.com/sribence/GAMF_Arduino/tree/main/Kisauto

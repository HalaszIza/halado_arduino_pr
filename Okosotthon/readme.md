# OkosOtthon

![Plakát](okosotthon.png)

> Linkek: https://docs.keyestudio.com/projects/KS0522/en/latest/KS0522.html#projects

---
## Csipogó

Leírás 📄   
Az Arduino segítségével sokféle interaktív alkotást készíthetünk, melyek közül az egyik leggyakrabban használt az akusztikai-optikai megjelenítés 🔊💡. Az ebben a kísérletben használt áramkör képes hangot előállítani 🎶.

Általában a kísérlethez piezo hangszórót (buzzer) vagy hangszórót használunk, de a buzzer egyszerűbb és könnyebben kezelhető ✅.

A jelen esetben bemutatott buzzer egy passzív típusú 🔌. Ez önmagában nem tud működni, külső impulzusfrekvenciákra van szüksége az aktiváláshoz 📈. Különböző frekvenciák különböző hangokat eredményeznek 🎵. Az Arduinóval akár egy dallamot is le tudsz programozni, ami szórakoztató és egyszerű élményt nyújt 😄🎼.

Specifikáció ⚙️
- Működési feszültség: 3.3–5V ⚡
- Interfész típusa: digitális 💻
- Méret: 30×20 mm 📏
- Tömeg: 4 g ⚖️

Példakód:
``` cpp
////////////////////////////////////////////////////////////////////
int buzzer= ;//set digital IO pin of the buzzer

void setup() 
{ 
  pinMode(buzzer,OUTPUT);  // set digital IO pin pattern, OUTPUT to be output 
}

void loop() 
{
  unsigned char i,j;  //define variable

  while(1)
  {
    for(i=0;i<80;i++)  // output a frequency sound
      {
        digitalWrite(buzzer,HIGH);  // sound
        delay(1);  //delay1ms 
        digitalWrite(buzzer,LOW);  //not sound
        delay(1);  //ms delay 
      } 
      for(i=0;i<100;i++)  // output a frequency sound
        { 
          digitalWrite(buzzer,HIGH);  // sound
          digitalWrite(buzzer,LOW);  //not sound
          delay(2);  //2ms delay 
        }
  } 
} 
////////////////////////////////////////////////////////////////////
```
## Mozgásérzékelő

Leírás 🕵️‍♂️  
A piroelektromos infravörös mozgásérzékelő képes érzékelni az emberi vagy állati mozgásból származó infravörös jeleket 🧍🐕🌡️, és kapcsolójelet ad ki (HIGH vagy LOW) ⚡.

Széles körben alkalmazható olyan helyeken, ahol emberi mozgás érzékelésére van szükség 🏠🚪🔐.

A hagyományos piroelektromos szenzorok általában nagyobb méretűek, mivel szükséges hozzájuk külön érzékelő, speciális chip és bonyolult perifériás áramkörök 🧩🔌, így megbízhatóságuk is alacsonyabb lehet.

Ez az új piroelektromos mozgásérzékelő kifejezetten Arduinohoz lett tervezve 🤖📦. Beépített digitális érzékelőt használ, kisebb mérettel, nagyobb megbízhatósággal ✅, alacsonyabb energiafogyasztással 🔋, és egyszerűbb áramköri kialakítással 🧠.

Specifikáció ⚙️
- Bemeneti feszültség: 3.3V – 5V (max: 6V) ⚡
- Működési áram: 15 μA 🔌
- Üzemi hőmérséklet: -20 ℃ – 85 ℃ ❄️🔥
- Kimeneti feszültség: HIGH = 3V, LOW = 0V 🔄
- Kimeneti késleltetés (HIGH szint): kb. 2.3–3 másodperc ⏱️
- Érzékelési szög: 100° 🧭
- Érzékelési távolság: akár 7 méter 📏
- Kimeneti LED-jelző: világít, ha a kimenet HIGH 💡
- Lábankénti áramkorlát: max. 100 mA ⚠️
- Méret: 30 × 20 mm 📐
- Tömeg: 4 g ⚖️

Példakód:
``` cpp
////////////////////////////////////////////////////////////////////
byte sensorPin = 3;
byte indicator = 13;
void setup()
{
  pinMode(sensorPin,INPUT);
  pinMode(indicator,OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  byte state = digitalRead(sensorPin);
  digitalWrite(indicator,state);
  if(state == 1)Serial.println("Somebody is in this area!");
  else if(state == 0)Serial.println("No one!");
  delay(500);
}
////////////////////////////////////////////////////////////////////
```

## Füstérzékelő

Leírás 🔥

Ez a lángérzékelő képes érzékelni a tüzet vagy más fényforrásokat, amelyek hullámhossza 760 nm és 1100 nm között van 🌈.
A tűzoltó robot játékokban a láng kulcsszerepet játszik a felderítésben 🤖🚒, mivel az érzékelő a robot "szemeként" működik, segítve a tűzforrás megtalálását 👀🔥.

Specifikáció ⚙️
- Tápfeszültség: 3.3V – 5V ⚡
- Érzékelési tartomány: 20 cm (4.8V) ~ 100 cm (1V) 📏
- Spektrális érzékenységi tartomány: 760 nm – 1100 nm 🌐
- Működési hőmérséklet: -25℃ – 85℃ ❄️🌡️🔥
- Interfész: digitális 💻
- Méret: 44 × 16,7 mm 📐
- Tömeg: 4 g ⚖️

Példakód:
``` cpp
////////////////////////////////////////////////////////////////////
const int flamePin = 2;     // the number of the flame pin
const int buzzPin =  13;      // the number of the BUZZER pin

// variables will change:
int State = 0;         // variable for reading status
void setup()
{
  // initialize the BUZZER pin as an output:
  pinMode(buzzPin, OUTPUT);      
  // initialize the pushbutton pin as an input:
  pinMode(flamePin, INPUT);     
}
void loop()
{
  // read the state of the value:
State = digitalRead(flamePin);
  if (State == HIGH) {     
    // turn BUZZER on:    
    digitalWrite(buzzPin, HIGH);  
  } 
  else {
    // turn BUZZER off:
    digitalWrite(buzzPin, LOW); 
  }
}
////////////////////////////////////////////////////////////////////
```

## Kijelző





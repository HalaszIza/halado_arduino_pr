# OkosOtthon

![Plakát](okosotthon.png)

> Linkek: https://docs.keyestudio.com/projects/KS0522/en/latest/KS0522.html#projects

---
## Mozgásérzékelő

Leírás 📄   
Az Arduino segítségével sokféle interaktív alkotást készíthetünk, melyek közül az egyik leggyakrabban használt az akusztikai-optikai megjelenítés 🔊💡. Az ebben a kísérletben használt áramkör képes hangot előállítani 🎶.

Általában a kísérlethez piezo hangszórót (buzzer) vagy hangszórót használunk, de a buzzer egyszerűbb és könnyebben kezelhető ✅.

A jelen esetben bemutatott buzzer egy passzív típusú 🔌. Ez önmagában nem tud működni, külső impulzusfrekvenciákra van szüksége az aktiváláshoz 📈. Különböző frekvenciák különböző hangokat eredményeznek 🎵. Az Arduinóval akár egy dallamot is le tudsz programozni, ami szórakoztató és egyszerű élményt nyújt 😄🎼.

Specifikáció ⚙️
- Működési feszültség: 3.3–5V ⚡
- Interfész típusa: digitális 💻
- Méret: 30×20 mm 📏
- Tömeg: 4 g ⚖️

``` cpp
////////////////////////////////////////////////////////////////////
int buzzer= ;//set digital IO pin of the buzzer
void setup() 
{ 
pinMode(buzzer,OUTPUT);// set digital IO pin pattern, OUTPUT to be output 
} 
void loop() 
{ unsigned char i,j;//define variable
while(1) 
{ for(i=0;i<80;i++)// output a frequency sound
{ digitalWrite(buzzer,HIGH);// sound
delay(1);//delay1ms 
digitalWrite(buzzer,LOW);//not sound
delay(1);//ms delay 
} 
for(i=0;i<100;i++)// output a frequency sound
{ 
digitalWrite(buzzer,HIGH);// sound
digitalWrite(buzzer,LOW);//not sound
delay(2);//2ms delay 
}
} 
} 
////////////////////////////////////////////////////////////////////
```


## Füstérzékelő


## Csipogó


## Kijelző

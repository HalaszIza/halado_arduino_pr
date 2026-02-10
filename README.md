# halado_arduino_programozas



## Alapok
🤖 Mi az az Arduino?
Egy bevezető az Arduino világába – mire jó, és hogyan használhatjuk.

Az Arduino egy nyílt forráskódú elektronikai platform, amely könnyen használható hardverre és szoftverre épül. 🧩
Az Arduino panelek képesek bemeneteket olvasni – például:
- egy fényt egy érzékelőn 💡
- egy ujjat egy gombon 🖲️
- akár egy Twitter-üzenetet 🐦

és kimenetté alakítani azokat – például:
- egy motor bekapcsolásával ⚙️
- egy LED felvillanásával 💡
- vagy valamilyen online tartalom közzétételével 🌐

📟 A panelnek utasításokat adhatsz, amelyeket a panel mikrokontrollerének küldesz. Ehhez az Arduino programnyelvet használod (a Wiring alapjaira épül), valamint az Arduino szoftvert (IDE), amely a Processing rendszeren alapul. 🧑‍💻

🌍 Mire használják az Arduinót?
Az évek során az Arduino több ezer projekt agya lett:
- hétköznapi eszközök 🧼
- tudományos műszerek 🧪
- művészeti installációk 🎨
- robotok 🤖
- IoT (Internet of Things) megoldások 🌐

👥 Egy világméretű közösség – diákok, hobbisták, művészek, programozók és szakemberek – gyűlt össze a platform köré. Az ő hozzájárulásaik révén hatalmas mennyiségű szabadon elérhető tudás jött létre, ami nagy segítség lehet a kezdőknek és profiknak egyaránt. 📚💡

🏫 Hogyan született az Arduino?
Az Arduino az Ivrea Interaction Design Institute falai között született, mint egy gyors prototípuskészítő eszköz – kifejezetten olyan diákoknak, akiknek nincs előzetes tudásuk elektronikában vagy programozásban. 🎓

Ahogy elterjedt a szélesebb közösségben is, az Arduino panelek fejlődni kezdtek, hogy megfeleljenek az új igényeknek:
- 🔹 Egyszerű 8 bites vezérlőktől
- 🔹 IoT alkalmazásokhoz készült eszközökön át
- 🔹 Viselhető kütyükön 👕
- 🔹 3D nyomtatáshoz 🖨️
- 🔹 Beágyazott rendszerekhez 🧠

egészen sokféle felhasználásra elérhetőek lettek az Arduino eszközök.

---
🔤 Ez a példa tartalmazza a lehető legkevesebb kódot, amely szükséges ahhoz, hogy egy program (vagyis „sketch”) helyesen leforduljon az Arduino szoftverben (IDE). 🛠️💻

📌 A kódban két kötelező rész található:
- a setup() függvény 🧰 – ez egyszer fut le a program elején,
- és a loop() függvény 🔁 – ez folyamatosan ismétlődik a program futása közben.

💻 Kód  
🔧 A setup() függvény akkor fut le, amikor egy sketch (vagyis egy Arduino-program) elindul.
📌 Ezt használjuk változók inicializálására, pin módok beállítására (pl. bemenet vagy kimenet), könyvtárak elindítására, és egyéb induló műveletekhez.

⚠️ A setup() csak egyszer fut le, minden egyes bekapcsolás vagy resetelés után. 🔁🔌

🔁 A loop() működése  
Miután létrehoztad a setup() függvényt, jön a loop() függvény. Ez pontosan azt csinálja, amit a neve is sugall: folyamatosan ismétlődik. ♻️

📲 Ez lehetővé teszi, hogy a program dinamikusan változzon és reagáljon, miközben fut.
👉 A loop() részben írt kódot használjuk arra, hogy aktívan vezéreljük a panelt – például érzékelők figyelése, LED-ek ki- és bekapcsolása, motorok működtetése stb.

📄 Alapváz – a minimális kódszerkezet
Az alábbi kód valójában nem csinál semmit, de hasznos kiindulási sablonként szolgál bármilyen saját sketch megírásához.
🧠 Emellett azt is bemutatja, hogyan kell megjegyzéseket (kommenteket) írni a kódba.

``` cpp
// Ez a setup() függvény - itt fut le minden induláskor
void setup() {
  // Ide írd az induló utasításokat
}

// Ez a loop() függvény - folyamatosan ismétlődik
void loop() {
  // Ide írd a vezérlő kódot
}
```

💬 Kommentek használata
📝 Minden olyan sor, amely // jellel kezdődik, megjegyzésnek számít, így azt a fordító figyelmen kívül hagyja.
Ez azt jelenti, hogy nyugodtan írhatsz utasításokat, magyarázatokat, jegyzeteket a kódod mellé.

✍️ A // jeleket a működő kód után is használhatod, így akár ugyanarra a sorra is írhatsz megjegyzést:

``` cpp
digitalWrite(13, HIGH); // Bekapcsolja a LED-et a 13-as lábon
```

💡 A kommentek különösen hasznosak:
- saját magadnak, hogy később is értsd, mit csináltál,
- másoknak, akik megnézik vagy használják a kódod.

---
Itt pedig még részletesebben megtalálsz mindent a témában kapcsolatban:  
https://docs.arduino.cc/built-in-examples/basics/AnalogReadSerial/?_gl=1*hlw4c8*_up*MQ..*_ga*MTY2NjIyNzEzNy4xNzU0NTc0ODQ5*_ga_NEXN8H46L5*czE3NTQ1ODkxMjgkbzIkZzEkdDE3NTQ1ODk5MzckajYwJGwwJGg1MDkwMjM1MTY.

---
Az alábbi linken pedig még több videót talász az arduino alapjairól:  
https://www.youtube.com/playlist?list=PLGs0VKk2DiYw-L-RibttcvK-WBZm8WLEP

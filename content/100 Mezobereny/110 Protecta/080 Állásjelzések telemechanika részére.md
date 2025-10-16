## 1. Mit jelent ez a gyakorlatban

Ezek a jelek **állapotjelző bemenetek** az E4-DKTVA digitális bemeneti kártyáján, amelyek:

- folyamatosan visszajelzik a **megszakító és a kapcsolókészülékek mechanikai helyzetét**,
    
- a **védelmi és vezérlési logikák** (például távműködtetés, engedélyezés, blokkolás) feltételeként szerepelnek,
    
- **biztonsági interlock** funkciók részei: a védelem például nem engedi meg a bekapcsolást, ha a földelő szakaszoló zárva van.
    

---

## 2. Tipikus funkciók ezekhez a jelekhez kapcsolva

- **Megszakító állás**: a védelem ellenőrzi, hogy a megszakító zárt vagy nyitott, mielőtt új parancsot ad.
    
- **Kocsi állás**: a kapcsolóberendezés csak bennállás esetén működtethető.
    
- **Rugófeszítés**: megszakító bekapcsolásához előfeltétel.
    
- **Földelő szakaszoló állás**: ha a földelő be van zárva, a védelem blokkolja a bekapcsolást.
    

---

## 3. Rendszerszintű szerep

- Ezek a jelek nem indítanak védelmet.
    
- A **digitális bemeneti logika** részei, és feltételeket biztosítanak más funkciókhoz (pl. távolságvédelem, tűzvédelmi parancsok, automatikus visszakapcsolás).
    
- Távfelügyeleti rendszerek (SCADA) számára is továbbíthatók állapotinformációként.
    

---

## 4. Összefoglalás – E4-DKTVA szerepe ezen a rajzon

|Szerep|Leírás|
|---|---|
|Állapotfelügyelet|A mező fő elemeinek mechanikai helyzetét felügyeli|
|Biztonsági reteszelés|Feltételeket biztosít a működéshez, illetve blokkolásokat|
|Kommunikáció|Állapotinformáció SCADA és automatikák felé|
|Logikai feltétel|Távvezérlés, automatikus visszakapcsolás és védelmi működés engedélyezése vagy tiltása|

![[Pasted image 20251016171414.png]]
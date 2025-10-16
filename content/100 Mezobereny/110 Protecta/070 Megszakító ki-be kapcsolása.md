## 1. A rajz főbb részei

|Rész|Funkció|
|---|---|
|Felső zóna|Védelmi készülékek (E4-DKTVA) és trip relék (Ki1, Ki2)|
|Középső zóna|Sorkapcsok, megszakítóvezérlés|
|Alsó zóna|Segédáramkör – indítás, bekapcsolás, rugófelhúzás, blokkolás|

---

## 2. E4-DKTVA – TRIP kimenetek (Ki1, Ki2)

A rajzon jól látható:

`Ki1 → X1:46 Ki2 → X1:49`

Ezek az E4-DKTVA trip kimenetei, amelyek a megszakító kioldó tekercseire mennek.

- Ki1: elsődleges védelmi kioldás (például távolságvédelem, túláramvédelem).
    
- Ki2: tartalék vagy szelektív kioldás (például zárlati tartalék védelem, MBV).
    

Ezek a kimenetek közvetlenül működtetik a Ki reléket, amelyek galvanikusan elválasztva a megszakító működtető körére hatnak.

---

## 3. Megszakító vezérlő kör

A kioldási jelek az alábbi láncon keresztül jutnak el a megszakítóig:

`E4-DKTVA → Ki1 / Ki2 relé → X101 sorkapcsok → megszakító kioldótekercs (Q0)`

A megszakító táplálás blokkjában található:

- K01 jelölésű relék vagy kontaktorok, amelyek a kioldó kör áramútját biztosítják,
- S11 és S12 kapcsolók, amelyek engedélyezéseket és visszajelzéseket adnak,
- Q0, amely a megszakító működtető áramkörét jelöli.

Ez a logika biztosítja, hogy a védelem csak engedélyezett állapotban oldjon le, és a működés ellenőrzött módon történjen.

---

## 4. Védelmi működés sorrendje

Ha a távolságvédelem hibát érzékel:

1. Az E4-DKTVA belső logikája aktiválódik.
2. A Ki1 trip kimenet aktiválódik.
3. A Ki1 relé zár, és feszültséget ad a megszakító kioldótekercsre.
4. A megszakító leold.
5. A visszajelzések (S11/S12) az E4-DKTVA felé közlik, hogy a megszakító nyitott állapotba került.

Ha a fő védelem nem működik, a Ki2 szolgálhat másodlagos kioldási parancsra.

---

## 5. Blokkolások, engedélyek és segédlogika

Az alsó áramkörben található funkciók:

- „Pumpálás gátlás” – megakadályozza a végtelen kioldási kísérleteket tartós hiba esetén.
    
- „Bekapcsolás” és „Rugófelhúzás” logikák – a normál üzem működési feltételeit biztosítják.
    
- J+, AM+, TM+ – segédtáp és vezérlési feszültségek.
    

Ezek nem közvetlenül a védelmi működést végzik, hanem a működési kör biztonságát és előfeltételeit biztosítják.

---

## 6. Összefüggés a teljes rendszerrel

Az E4-DKTVA működése ebben a körben a következőképpen foglalható össze:

- Analóg jelek alapján érzékel hibát.
- Digitális bemeneteken keresztül kap engedélyező és blokkoló jeleket.
- Trip kimenetein keresztül működteti a megszakítókat (Ki1 / Ki2 relé).
- A működést a megszakító visszajelzése zárja.

A Ki1/Ki2 jelút a védelem legkritikusabb része, mert ez adja a megszakítónak a tényleges kioldási parancsot.

---

## 7. Összegzés – E4-DKTVA szerepe ezen az ábrán

|Elem|Funkció|Kapcsolódás|
|---|---|---|
|Ki1 / Ki2 Trip|Védelmi kioldás parancs|E4-DKTVA → megszakító|
|X1:46, X1:49|Kimeneti pont|Relék felé|
|K01 relék|Engedélyezés, galvanikus leválasztás|Trip áramkör|
|S11, S12|Visszajelzések|Állapotvissza a védelembe|
|J+, AM+, TM+|Tápfeszültségek|Segédüzem|
|Q0|Működtető kör|Megszakító fizikai működtetése|

Lényegében az E4-DKTVA ebben a kapcsolásban a védelmi logika végrehajtó eleme: a hibadetektálás után kiadja a Trip jelet, amely a megszakító kioldását elindítja, miközben a körben lévő blokkolások és engedélyezések a biztonságos működést garantálják.

![[Pasted image 20251016171021.png]]
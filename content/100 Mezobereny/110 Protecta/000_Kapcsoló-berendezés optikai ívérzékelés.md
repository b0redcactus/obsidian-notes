![[Pasted image 20251014163659.png]]
## 1. **Felépítés logikailag három szintre bontható**

`[ Felső szint ]    → Helyi érzékelők (SE1, SE2, SE4) [ Középső szint ]  → WAMP 125 érzékelő rendszer [ Alsó szint ]     → Védelmi relé (pl. távolságvédelem, IED)`

---

##  2. **Felső szint – SE érzékelők**

- **SE1 – Gyűjtősín tér**
- **SE2 – Megszakító tér**
- **SE4 – Kábel tér**

Ezek az `SE` (Sensor Element) jelölésű eszközök:

- **Ívhiba érzékelők / fényérzékelők / hibahely detektorok**
- Általában **optikai érzékelők** (pl. fényívet észlelnek), vagy hő/feszültségérzékelők.
    

A rajzon látható, hogy az érzékelők **X2 sorkapcson** keresztül csatlakoznak a WAMP 125-höz:

|Érzékelő|Csatlakozás|Funkció|
|---|---|---|
|SE1|X2:1–2|Gyűjtősín tér érzékelés|
|SE2|X2:5–6|Megszakító tér érzékelés|
|SE4|X2:11–12|Kábel tér érzékelés|

 Ha például egy ívhiba lép fel a kábelcsatlakozásnál, az **SE4 érzékelő** ad jelet.

---

## 3. **Középső szint – WAMP 125 érzékelő egység**

**WAMP 125** → egy **ívhiba detektáló / érzékelő és logikai feldolgozó egység**.

Feladata:

- Fogadja az SE érzékelők jeleit,
- Logikai feltételek alapján dönt: **hiba → kioldás**,
- Továbbítja a **kioldási jelet a védelmi relé felé**.

A rajzon látható kimenetek:

- `X5:4 / X5:5` → T1 kioldás
- `X5:7 / X5:8` → T2 kioldás

Ez **két külön kioldási áramkör**, pl.:

- T1 → megszakító azonnali kioldás
- T2 → tartalék vagy más logikai funkció (pl. szelektív kioldás)

 _A WAMP 125 tehát nem maga old le nagyáramot — csak jelet ad a fő védelmi készüléknek._

---

##  4. **Alsó szint – Védelmi készülék (IED)**

A rajz alján látható:

`E4-DKTVA`

Ez a **védelmi relé (IED)**, amely ténylegesen **vezérli a megszakítót**.

Bemenetei:

- `E/13` → Gyűjtősín tér (IN12)
- `E/14` → Megszakító tér (IN11)
- `E/15` → Kábel tér (IN10)
    

Ezek a **WAMP kimenetekről érkező digitális jelek**, amik:

- informálják a védelmet arról, **hol keletkezett az ívhiba**,
- és ha szükséges, **indítják a kioldási folyamatot**.

---

## 5. **Kioldási logika (T1 – T2)**

A WAMP két független kioldó jelet kezel:

|Típus|Kimenet|Funkció (tipikus)|Csatlakozás|
|---|---|---|---|
|T1|X5:4–5|Fő kioldás|E/13–15|
|T2|X5:7–8|Tartalék / késleltetett kioldás|E/13–15|

Pl. ha SE4 jelez:

1. WAMP 125 érzékeli a hibát a kábel térben.
2. T1 kimenet aktiválódik.
3. IED (DKTVA) bemenete ezt érzékeli,
4. IED **kioldja a megszakítót**.
    

---

## 6. **Tipikus alkalmazás**

Ez a kapcsolás nagyon gyakori:

- **22 kV-os cellákban** (kábel, megszakító, gyűjtősín),
- **ívhiba-védelemként**, a normál túláram- vagy távolságvédelem **kiegészítésére**,
- **gyors kioldásra** (tipikusan < 30 ms) az emberi élet és berendezések védelmére.
    

A WAMP rendszer:

- gyorsabban reagál, mint a klasszikus relé (mert nem kell áramot mérnie),
- pontosan **lokalizálja a hibát**, így segít a karbantartásban is,
- külön kezeli a gyűjtősín / megszakító / kábel hibákat.
    

---

## 7. Összegzés

|Rész|Funkció|
|---|---|
|SE1 / SE2 / SE4 érzékelők|Helyi ívhiba érzékelés a cella különböző pontjain|
|WAMP 125 modul|Jelek feldolgozása, kioldási logika (T1/T2)|
|IED (DKTVA)|Kioldás végrehajtása és rendszer védelme|
|T1 / T2 áramkör|Elsődleges és tartalék kioldás|
|X1 / X5 sorkapcsok|Fizikai csatlakozás az érzékelők, WAMP és IED között|

 Ez tehát **nem távolságvédelmi mérés**, hanem egy **ívhiba-érzékelésen alapuló gyorsvédelmi rendszer**, ami az IED-del együttműködve nagyon gyors leoldást biztosít.

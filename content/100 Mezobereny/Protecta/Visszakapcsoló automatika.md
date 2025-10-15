A **automatikus visszakapcsolás** (_Auto Reclose – AR_) egy kiegészítő logika, amely a **leoldás után** egy **időzített visszakapcsolást** indít el:

### Tipikus működés:

1. **Hiba érzékelés** → távolságvédelem leoldja a megszakítót.
2. **Szünet** (pl. 0,3–1 s) → vár, hogy az átmeneti hiba megszűnjön.
3. **Visszakapcsolás** → a megszakító újra zár.
4. Ha a hiba **megszűnt** → hálózat helyreáll.
5. Ha a hiba **tartós** → a relé újra leold, és **zárva marad** (zárlat izolálva).
    

📌 A legtöbb középfeszültségű AR rendszer:

- **1 vagy 2 automatikus visszakapcsolást** engedélyez,
- **szelektíven** működik (csak ott kapcsol vissza, ahol kell),
- **külön beállítható** feszültségfüggő vagy időfüggő logikával.
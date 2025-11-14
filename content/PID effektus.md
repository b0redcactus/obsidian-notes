A „Potential Induced Degradation” (PID) olyan jelenség, amikor a PV-modulok kimeneti teljesítménye csökken, mert a panel feszültsége a földhöz képest egy kedvezőtlen potenciálra áll be, és ezen keresztül áramokon keresztül károsodás, kapacitás-vesztés alakulhat ki. 
Tehát a PV modul negatív vagy pozitív „téves” potenciálja a földhöz képest lehet igazán káros.

A Huawei PID-modul célja, hogy ezt a potenciálkülönbséget kontrollálja, vagyis **megelőzze**, hogy a panel-föld közötti feszültség olyan értéket vegyen fel, ami PID-effektust okozhat. [huawei+1](https://solar.huawei.com/~/media/Solar/attachment/pdf/eu/service/download/SmartPID2000%20User%20Manual.pdf?utm_source=chatgpt.com)  
Konkrétan:

- A modul képes **kétféle kompenzációs módot** használni: „N/PE” (nullavezető/föld kompenzáció) és „PV/PE” (PV-terminál/föld kompenzáció) módokat. [support.huawei.com+1](https://support.huawei.com/enterprise/en/doc/EDOC1100033491/ca2c8120/overview?utm_source=chatgpt.com)
    
- Amikor például az inverter hálózatra táplál (nappal), akkor az N/PE módot alkalmazza a fázis/föld viszonyában. Este, amikor nincs betáplálás, átkapcsolhat PV/PE módba. [support.huawei.com+1](https://support.huawei.com/enterprise/en/doc/EDOC1100033491/ca2c8120/overview?utm_source=chatgpt.com)
    
- A modul része lehet olyan rendszereknek, amelyek transzformátorral vagy elválasztással dolgoznak, tehát „doboz-transzformátor” (box-type transformer) alá is telepíthető. [support.huawei.com+1](https://support.huawei.com/enterprise/en/doc/EDOC1100033491/ca2c8120/overview?utm_source=chatgpt.com)


### Hogyan működik röviden

- A modul bemenetén a háromfázisú AC (fázisok A, B, C) és a föld (PE) illetve az inductor közé („N” középpont) jön kapcsolat. [support.huawei.com+1](https://support.huawei.com/enterprise/en/doc/EDOC1100033491/ca2c8120/overview?utm_source=chatgpt.com)
    
- A PID-modul-induktor páros olyan „injekciós” feszültséget tesz a rendszerbe, hogy a PV modul/föld közötti feszültség a biztonságos határon belül maradjon. [support.huawei.com](https://support.huawei.com/enterprise/en/doc/EDOC1100033424/9c5aa170/pvess-scenario?utm_source=chatgpt.com)
    
- Ezen túl a modul ragyogóan „központi kompenzáció” módban dolgozik, azaz egy modul akár több inverterhez tartozó PV-csoportot is képes lefedni. [support.huawei.com](https://support.huawei.com/enterprise/en/doc/EDOC1100033491/ca2c8120/overview?utm_source=chatgpt.com)
    
- A modul kommunikál az adatgyűjtővel (pl. a Huawei SmartLogger-ral) és riasztást is tud küldeni, ha pl. az izolációs ellenállás túl alacsony. [support.huawei.com](https://support.huawei.com/enterprise/en/doc/EDOC1100033424/9c5aa170/pvess-scenario?utm_source=chatgpt.com)


### Miért hasznos ez a transzformátor-dobozban / PV rendszerben

- Növeli a PV rendszer hozamát azáltal, hogy csökkenti a PID okozta teljesítménycsökkenést. [huawei+1](https://solar.huawei.com/~/media/Solar/attachment/pdf/eu/service/download/SmartPID2000%20User%20Manual.pdf?utm_source=chatgpt.com)
    
- Csökkenti a panel-föld közötti potenciál-különbségekből fakadó kockázatokat (pl. szigetelés-hiba).
    
- Segíti a rendszer biztonságos üzemét és monitoringját azáltal, hogy beépített kommunikációval, riasztásokkal rendelkezik.


### Fontos telepítési és üzemeltetési tudnivalók

- A semleges vezetéket (N) a háromfázisú rendszernél **nem szabad** csatlakoztatni, ha a modul N/PE módot használ – ennek megsértése magas feszültség-kockázatot hozhat. [support.huawei.com](https://support.huawei.com/enterprise/en/doc/EDOC1100033491/ca2c8120/overview?utm_source=chatgpt.com)
    
- A föld (PE) csatlakozás megfelelő és stabil legyen, különben a kompenzáció nem működik rendesen. [support.huawei.com](https://support.huawei.com/enterprise/en/doc/EDOC1100033424?utm_source=chatgpt.com)
    
- A rendszer izolálására vonatkozó követelmények: pl. ha nincs galvanikus kapcsolat az inverter és a föld között, akkor transzformátor vagy más izolációs eszköz szükséges lehet. [support.huawei.com](https://support.huawei.com/enterprise/en/doc/EDOC1100033424/7118cd/overview?utm_source=chatgpt.com)



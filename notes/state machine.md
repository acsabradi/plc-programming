Rajzoljuk fel az állapotátmenet diagramot a kimenetekkel.
Állapotátmenet akkor történik ha
- a kiinduló állapot aktív
- az átmenet feltétele igaz

Bitregiszterekkel követjük mely állapot aktív.
- egyszerre csak egy bit lehet aktív
- állapotátmenetkor gondoskodunk a bitek beállításáról

Automata típusok:
- Mealy: kimenet függ az állapottól és a bemenettől
- Moore: kimenet csak az állapottól függ
	- Írjuk fel az állapot-kimenet táblázatot

Inicializálás:
- Első parancs: Minden állapotbit 0-ba állítva, kivéve a kijelölt start állapot 1-be
- Első parancs helyett first scan bit használata
- Csak az első ciklusban lefutó blokkban (OB100) bitek beállítása

Állapotgép tervezés lépései:
1. Állapotok definiálása
2. Állapotátmenet diagram
3. Ha Moore modell: állapot-kimenet táblázat
4. Állapotátmenet logika
5. Állapot-kimenet leképezés logika
6. Inicializálás

Szabvány funkcióblokkok:
- On-delay timer (TON)
	- Kimenete 1-be vált ha a bemenetén egyhuzamban PT ideig 1 van
- Off-delay timer (TOF)
	- Kimenete 1-be vált ha a bemenete 1-re vált, majd a kimenet 0-ba állása után PT-vel a kimenet 0-ba vált
- Pulse timer (TP)
	- A bemenet felfutó éle indítja a számlálót
- Retentív TON
	- A belső számláló nem ugrik vissza nullára ha a bemeneten 1->0 átmenet van
	- A következő 1->0 bemenet átmenetnél a mentett értéktől folytatja a mérést
- CTU
	- Bemenet 0->1 éleit nézi, minden élre 1-el növeli a belső számlálót, kimenete 1 ha a számláló elérte a PV-t
	- Reset 0-ba állítja a számlálót
- CTD
	- Kimenet 1 ha a számláló elérte a 0-t
	- LD a PV-re állítja a számlálót
- CTUD
- MOVE értékadás
	- ENI: Csak akkor fut le a blokk ha 1
	- ENO: hiba esetén 0
- Matematikai blokk
	- komparálás
	- gyökvonás

Programszervezés
- END tekercs
- label
- szubrutin
	- szubrutin label
	- végén RET tekercs
	- nincs paraméterátadás
		- memóriába tesszük a függvénynek átadandó és a függvény által visszaadandó értékeket
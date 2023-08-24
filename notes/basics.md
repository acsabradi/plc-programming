PLC feladata:
- Technológia működésének nyomon követése a bemenetre kötött szenzorokon keresztül
- Döntéshozatal
- Beavatkozás a technológia működésébe a kimeneteken keresztül

Követelmények:
- Megbízhatóság
- Determinisztikus működés
	- $\downarrow$ worst case válaszidő

PLC ciklusok:
- belső feldolgozás
	- öndiagnosztika
	- ciklusvezérlés
	- kommunikáció
	- számlálók és időzítők kezelése
- bemenetek olvasása
- program végrehajtás
- kimenetek írása

PLC memória:
- program memória
- adat memória
	- rendszer memória
		- konfigurációs adatok
		- státusz infók
		- időzítők
		- számlálók
		- regiszterek
		- stack
		- ==bemeneti kép==
		- ==kimeneti kép==
	- felhasználói memória
		- low end PLC-k esetében hiányozhat

Ciklikus végrehajtás: A ciklus utolsó lépése után azonnal indul a következő ciklus.

Periodikus végrehajtás: A periódusidő a bemenetek olvasásával indul; a következő ciklus csak a periódusidő lejárta után indul (nem számít ha az aktuális ciklus hamarabb végzett)

Ciklusidő hossz:
- Egy elemi lépés (pl. számláló növelése) $\mu s$ nagyságrendű
- Egy ciklus hossza $ms$ nagyságrendű

Worst case válaszidő:
- $\approx$ 2 * ciklusidő
- példa feladat: bemenet másolása kimenetre
	- ha az új jel a bemeneten röviddel a beolvasás után jön, akkor kb. 2 ciklus kell mire az kikerül a kimenetre
- jel késleltetési idők elhanyagolhatók
- ==valós idejű rendszer==

Watchdog:
- Maximum limitet ad meg a ciklusidőnek
- Ha a limitet átlépi a ciklus (pl. végtelen ciklus), akkor a watchdog hibakezelést indít el
- Hibakezelés lépései:
	- hibakezelői rutin indítása
	- leállás
	- kimenetek veszélytelen állapotba állítása
	- hibajelzés

Táp kikapcsolás:
- application context
- rendszer memória
- felhasználói memória mentése

Indítás:
- hidegindítás
	- változók inicializálva a kezdeti értékekre
	- program az elejétől indul
	- memory reset-el is elérhető a hidegindítás
	- akkor is hidegindítás van, ha a PLC öndiagnosztika hibát talál a lementett adatokban
- melegindítás
	- leállítás előtti állapotba visszatérés
	- application context visszatöltve
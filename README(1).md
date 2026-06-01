
# My Dolphin Show – Projekt dokumentáció

## Játékleírás

A játék egy böngészőben futó, Canvas alapú ügyességi játék, amelyben a játékos egy delfint irányít.

### Cél
A cél, hogy a delfin minél több karikán ugorjon át, halakat gyűjtsön, valamint minél magasabb pontszámot érjen el az öt szint teljesítése során.

### Irányítás
- **Egér / érintés:** a delfin vízszintes és függőleges mozgatása.
- **Space billentyű / kattintás / koppintás:** ugrás.
- A levegőben végrehajtott forgások extra pontot adhatnak.

### Játékmenet
- A játék 5 szintből áll.
- Minden szint 60 másodpercig tart.
- A szinteken különböző számú karikát kell teljesíteni:
  - 1. szint: 20 karika
  - 2. szint: 40 karika
  - 3. szint: 60 karika
  - 4. szint: 80 karika
  - 5. szint: 100 karika
- Egy karika teljesítése 50 pontot ér.
- A halak bónuszpontokat biztosítanak.
- Az aranyhal különleges jutalomként egy plusz karikának számít.

---

## Magas szintű logika

A játék egyetlen HTML fájlban valósul meg JavaScript segítségével.

### Fő állapotok

A program állapotgép-szerű működést használ:

- `menu` – főmenü
- `playing` – aktív játék
- `levelend` – szintvégi eredményképernyő
- `summary` – végső összesítő

### Fontosabb objektumok

#### Dolphin (`dol`)
A játékos által irányított delfin.

Tárolt adatok:
- pozíció (`x`, `y`)
- sebesség (`vx`, `vy`)
- irány
- forgási állapot
- vízben vagy levegőben van-e

#### Hoop
A karikák objektumai.

Tulajdonságok:
- pozíció
- sugár
- élettartam
- szín
- teljesítési állapot

#### Fish
A gyűjthető halak.

Tulajdonságok:
- pozíció
- sebesség
- normál vagy aranyhal státusz

#### Particle rendszer
A vízfröccsenések, buborékok és vizuális effektek megjelenítésére szolgál.

### Fontosabb függvények

#### `initGame()`
A teljes játék inicializálása.

#### `initLevel()`
Az aktuális szint adatainak betöltése.

#### `spawnHoop()`
Új karika létrehozása.

#### `spawnFish()`
Új hal generálása.

#### `doJump()`
A delfin ugrásának kezelése.

#### `update(dt)`
A játék logikájának frissítése:
- mozgás
- ütközések
- pontszám
- időzítés
- szintváltás

#### `drawScene()`
A teljes jelenet kirajzolása Canvas segítségével.

#### `drawHUD()`
A játék közbeni információs felület megjelenítése.

#### `drawSummaryScreen()`
A végső eredmények és csillagok kiszámítása.

### Játékhurok

A program a böngésző `requestAnimationFrame()` függvényét használja.

A ciklus:
1. feldolgozza a bemenetet,
2. frissíti a játék állapotát,
3. újrarajzolja a képernyőt.

---

## AI eszközök használata

A projekt fejlesztése során mesterséges intelligencia segítséget is igénybe vett.

### Használt AI eszköz
- ChatGPT

### Miben segített?
- JavaScript kódrészletek generálása
- Canvas grafikai elemek megtervezése
- játéklogikai ötletek kidolgozása
- hibakeresés és optimalizálás
- dokumentáció elkészítése

### Legnagyobb segítség
Az állapotkezelés, a szintlogika és a felhasználói felület gyors prototípusának elkészítése.

---

## Easter Egg (opcionális)

Tipp:
> Néha a legértékesebb hal nem narancssárga. Érdemes figyelni az arany színű látogatót is...

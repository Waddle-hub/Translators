Adatbázistervezés, objektumorientált programozás és tervezés során (lásd: objektum orientált programszerkezet) a has-a (has_a vagy has a) (magyarul „van neki egy …”) egy kompozíció kapcsolat, ahol az egyik objektum (rész/alkotó/tag objektum) „hozzá tartozik” (része vagy tagja) egy másik objektumhoz (az összetett objektumhoz), és a birtoklás szabályainak megfelelően viselkedik. Magyarul egy objektumban előforduló has-a kapcsolat az lényegében annak egy mezője. Több has-a kapcsolat együttesen birtokló hierarchiát alkot.
Gyakran összehasonlításra kerül az is-a (is_a vagy is a) kapcsolattal, mely osztályozási hierarchiát formál (altípusok).
A döntés, hogy egy objektum és az alárendeltje közötti kapcsolat is-a, vagy has-a legyen-e, nem minidig egyértelmű. Ez szükségessé tette bizonyos metalingvisztikai kifejezések megfogalmazását. A C++ STL-ben található container-ek jó példa ként szolgálnak a has-a kapcsolatra.
Kapcsolatok összegezve:
-	Hiperonímia-hiponímia (őstípus-altípus) típusok (osztályok) közötti kapcsolatok, melyek osztályozási hierarchiát definiálnak,
o	Az öröklődési kapcsolatban: egy gyerekosztály (altípus) egy un. „olyan, mint” (is-a) kapcsolattal bír az ő ősosztályával (őstípus);
-	Holonímia-meronímia (egész - rész, egyed - alkotó, tartalmazó - tag) birtokló hierarchiát alkotnak típusok között, ahol
o	az aggregáció (azaz tulajdonos nélkül) kapcsolat:
	az egész has-a kapcsolatban áll a résszel 
o	a kompozíció (azaz tulajdonossal) kapcsolat:
	a meronímia (alkotó) „a része” kapcsolatot alkot a holonímiájával (egyed)
o	a behatároló kapcsolat:
	a meronímia (tag) „a tagja” kapcsolatot alkot a holonímiájával (tartalmazó)
-	koncepció-objektum (típus - token) típusok (osztályok) és objektumok (példányok) közötti kapcsolatok, ahol
o	egy token (objektum) „a példánya” kapcsolatban áll az ő típusával (osztály).

Példák
Egyed-kapcsolat modell
Adatbázisok esetén a has-a kapcsolatokat leggyakrabban az egyed-kapcsolat diagrammokkal ábrázolják. Ahogy azt a jobbra lévő ábra is mutatja, egy felhasználó (account) akár több karakterrel (character) is rendelkezhet. Ez reprezentálja, hogy az felhasználó „has-a” kapcsolatban áll a karakterrel, a felhasználónak van egy (több) karaktere.
UML osztály diagram
Objektum-orientált programozásban ezt a kapcsolatot jól lehet jellemezni a Unified Modeling Language osztálydiagrammal. Ez a fajta has-a kapcsolat kompozícióként is ismert. Ahogy ez az osztálydiagrammon is jól látszik, az autónak van egy karburátora, vagy az autó egy karburátorból „tevődik össze” (composed of -> composition, kompozíció). A fekete színű rombusz kompozíciót jelképez, vagyis a rombuszhoz közelebb eső tárgy a másik tárgyból áll, vagy tartalmazza azt. Eközben a fehér rombusz aggregációt jelöl, ami azt jelenti, hogy a rombuszhoz közelebb eső tárgy birtokolja a másik tárgyat.
C++
Egy másik módja, hogy a való világ mintájára különbséget tegyünk aggregáció és kompozíció között, hogy figyelembe vesszük a tartalmazott objektum relatív élettartamát. Például, ha egy Autó objektum tartalmaz egy Alváz objektumot, az alváz nagyvalószínűséggel egyszer sem lesz kicserélve az Autó teljes élettartama alatt. Élethossza ugyanakkora lesz, mint magának az Autónak; így ez a kapcsolat egy kompozíció. Ugyanakkor, ha ennek az Autó objektumnak van valamennyi Gumiabroncs objektuma, ezek a Gumiabroncs objektumok idővel elkophatnak és többször is lecserélésre kerülhetnek. Vagy ha az Autó használhatatlanná válik, attól a Gumiabroncsok még felhasználhatók maradnak más Autók számára. A Gumiabroncs objektumoknak más az élettartamuk, mint az Autó objektumoknak; következésképpen ez a kapcsolat az aggregációnak felel meg.
Ha egy C++ osztállyal szeretnénk implementálni a fent leírt kapcsolatokat, az Autó objektum tartalmazna egy teljes Alváz osztályt adattagként. Ezen Alváz objektum az Autó osztály konstruktorában kerülne példányosításra (vagy az adattag adattípusaként kerül definiálásra és property-jeit a konstruktorban állítjuk be.) És mivel így teljes egészében részévé válik az Autó osztálynak, mint adattag, ha kitörölnénk az Autó osztály objektumot, az Alváz objektum is megszűnne létezni.
Másik kézről viszont, az Autó osztály adattagjai, melyek Gumiabroncs objektumokra mutatnak, azok nagy valószínűséggel C++ pointerek (mutatók) lesznek. A Gumiabroncs objektumokat képesek vagyunk kívülről példányosítani és törölni, vagy akár egy másik Autó objektum adattagjaihoz is hozzárendelhetők. A Gumiabroncs objektumok teljesen független élethosszal rendelkeznek, melynek semmi köze az Autó objektum törléséhez.

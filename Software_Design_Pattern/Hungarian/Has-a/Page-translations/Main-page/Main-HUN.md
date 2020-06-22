Adatbázistervezés, objektumorientált programozás és tervezés során (lásd: objektum orientált programszerkezet), has-a  (has_a vagy has a) (magyarul „van neki egy …”) egy kompozíció kapcsolat, ahol az egyik object (rész/alkotó/tag object) „hozzá tartozik” (része vagy tagja) egy másik object-nek (a kompozit object-nek), és a birtoklás szabályainak megfelelően viselkedik. Magyarul egy object-ben előforduló has-a kapcsolat az lényegében annak egy mezője. Több has-a kapcsolat együttesen birtokló hierarchiát alkot.
Gyakran összehasonlításra kerül az is-a (is_a vagy is a) kapcsolattal, mely osztályozási hierarchiát alkot (altípusok).
A döntés, hogy egy object és az alárendeltje közötti legkézenfekvőbb kapcsolat is-a, vagy has-a-e legyen, nem minidig egyértelmű. Ez szükségessé tette bizonyos metalingvisztikai kifejezések megfogalmazását. A C++ STL-ben található container-ek jó példa ként szolgálnak a has-a kapcsolatra.
Kapcsolatok összegezve:
-	Hiperonímia-hiponímia (őstípus-altípus) típusok (osztályok) közötti kapcsolatok, melyek osztályozási hierarchiát definiálnak,
o	Az öröklési kapcsolatban: egy gyerekosztály (altípus) egy un. „olyan, mint”  kapcsolattal bír az ő ősosztályával (őstípus);
-	Holonímia-meronímia (egész - rész, egyed - alkotó, tartalmazó - tag) birtokló hierarchiát alkotnak típusok között, ahol
o	az aggregáció (azaz tulajdonos nélkül) kapcsolat:
	az egész has-a kapcsolatban áll a résszel 
o	a kompozíció (azaz tulajdonossal) kapcsolat:
	a meronímia (alkotó) „a része” kapcsolatot alkot a holonímiájával (egyed)
o	a behatároló kapcsolat:
	a meronímia (tag) „a tagja” kapcsolatban áll a holonímiájával (tartalmazó)
-	concept-object (típus - token) típusok (osztályok) és object-ek (példányok) közötti kapcsolatok, ahol
o	egy token (object) „a példánya) kapcsolatban áll az ő típusával (osztály).

Példák
Egyed-kapcsolat model
Adatbázisok esetén a has-a kapcsolatokat leggyakrabban az egyed-kapcsolat diagrammokkal ábrázolják. Ahogy azt a jobbra lévő ábra is mutatja, egy account-nak akár több character-je is lehet. Ez reprezentálja, hogy az account „has-a” kapcsolatban áll a character-rel, az accountnak van egy (több) character-je.
UML osztály diagram
Objektum-orientált programozásban ezt a kapcsolat jól lehet jellemezni a Unified Modeling Language osztály diagrammal. Ez a fajta has-a kapcsolat kompozícióként is ismert. Ahogy ez az osztálydiagrammon is jól látszik, az autónak van egy karburátora, vagy az autó egy karburátorból „tevődik össze” (composed of -> composition, kompozíció). A fekete színű rombusz kompozíciót jelképez, vagyis a rombuszhoz közelebb eső tárgy a másik tárgyból áll, vagy tartalmazza azt. Eközben a fehér rombusz aggregációt jelöl, ami azt jelenti, hogy a rombuszhoz közelebb eső tárgy birtokolja a másik tárgyat.
C++
Egy másik módja hogy különbséget tegyünk aggregáció és kompozíció között a való világ mintájára, hogy figyelembe vegyük a tartalmazott object relatív élettartamát. Például, ha egy Autó object tartalmaz egy Alváz object-et, az alváz nagyvalószínűséggel nem lesz kicserélve az Autó teljes élettartama alatt. Élethossza ugyanakkora lesz, mint magának az Autónak; így ez a kapcsolat egy kompozíció. Ugyanakkor ha ennek az Autó object-nek van valamennyi Gumiabroncs object-je, ezek a Gumiabroncs object-ek idővel elkophatnak és többször is lecserélésre kerülhetnek. Vagy ha az Autó használhatatlanná válik, attól a Gumiabroncsok még felhasználhatók maradnak egy másik Autó számára. A Gumiabroncs object-eknek más az élettartamuk, mint az Autó object-nek; következésképpen ez a kapcsolat az aggregációnak felel meg.
Ha egy C++ osztállyal szeretnénk implementálni a fent leírt kapcsolatokat, az Autó objektum tartalmazna egy teljes Alváz osztályt adattagként. Ezen Alváz objektum az Autó osztály konstruktorában kerülne példányosításra (vagy az adattag adattípusaként kerül definiálásra és property-jeit a konstruktorban állítjuk be.) És mivel így teljes egészében részévé válik az Autó osztálynak, mint adattag, ha kitörölnénk az Autó osztály objektumot, az Alváz objektum is megszűnne létezni.
On the other hand, the Car class data members that point to Tire objects would most likely be C++ pointers. Tire objects could be instantiated and deleted externally, or even assigned to data members of a different Car object. Tire objects would have an independent lifetime separate from when the Car object was deleted.


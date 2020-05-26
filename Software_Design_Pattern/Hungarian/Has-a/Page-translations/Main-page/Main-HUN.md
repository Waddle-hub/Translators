Adatbázistervezés, objektumorientált programozás és tervezés során (lásd: objektum orientált programszerkezet), has-a (has_a vagy has a) egy kompozíció kapcsolat, ahol az egyik object (gyakran nevezik constituted object-nek, vagy rész/constitutent/tag object-nek) „hozzá tartozik” (része vagy tagja) egy másik object-nek (a composite objectn-nek), ésa birtoklás szabályainak megfelelően viselkedik. Magyarul egy object-ben előforduló has-a kapcsolat lényegében annak egy mezője. Több has-a kapcsolat együttesen possessive hierarchiát alkot.
This is to be contrasted with an is-a (is_a or is a) relationship which constitutes a taxonomic hierarchy (subtyping).
A döntés, hogy egy object és az alárendeltje közötti legkézenfekvőbb kapcsolat is-a, vagy has-a-e, nem minidig egyértelmű. Ez szükségessé tette bizonyos metalinguisztikai kifejezések megfogalmazását. A C++ STL-ben található container-ek jó példa ként szolgálnak a has-a kapcsolatra.
Kapcsolatok összegezve:
-	Hypernym-hyponym (őstípus-altípus) típusok (osztályok) közötti kapcsolatok, melyek osztályozási hierarchiát definiálnak,
o	Az öröklési kapcsolatban: egy hyponym (altípus, alosztály) egy un. Type-of kapcsolattal bír az ő hypernym-jével (őstípus, ősosztály);
-	Holonym-meronym (egész/entitás/container-part/constituent/member

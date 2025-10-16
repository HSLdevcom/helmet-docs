---
nav_order: 11
sort: 11
---

# Sanasto

Tässä on esitetty sanastoa joka esiintyy dokumentaatiossa ja mallin käytössä.

* **Agenttimalli** eli yksilömalli mallintaa liikennettä yksilötasolla, kun taas HELMET-mallissa lasketaan yleensä aggregoituja lukuja. Agenttimalli toimii HELMET:ssä vaihtoehtoisena mallijärjestelmänä. 
* **Aggregointi** tarkoittaa tietojen tai aineistojen yhdistämistä ja kokoamista yhdeksi kokonaisuudeksi esim. yksilö- tai rakennustasolta sijoittelualuetasolle.
* **Aluejako** kuvaa koko mallialueen jakoa pienempiin osa-alueisiin. HELMET-malli jakautuu 2098  sijoittelualueeseen. Alueiden rajat on kuvattu paikkatietotiedostossa, ja kutakin aluetta kuvaa mallissa yksi sentroidi.
* **Avoin kiertomatka** on sellainen kiertomatka, jossa ei palata alkupisteeseen eli esim. koti–kyläilypaikka, jossa henkilö jää yöksi kyläilypaikkaan ja tutkimusvuorokausi päättyy ennen paluuta. Ks. myös ”Suljettu kiertomatka”.
* **Diskreetti valintamalli** on tilastollinen malli, jolla analysoidaan valintoja, joissa yksilö valitsee yhden vaihtoehdon monista diskreeteistä eli erillisistä vaihtoehdoista. Esimerkiksi matkalla käytettävä kulkutapa on diskreetti valinta, jossa vaihtoehtoja ovat mm. henkilöauto ja joukkoliikenne.
* **EMME** eli OpenPaths EMME on Bentleyn liikennesuunnitteluohjelmisto, jota käytetään HELMET-mallin sijoittelussa. HELMET-mallin tarjontamalli on laadittu EMME-ohjelmistolla. 
* **Ennustaminen** tarkoittaa mallin käyttöä samoilla parametreillä, mutta eri lähtötiedoilla kuin estimoinnissa.
* **Ennusteskenaario** kuvaa sellaista mallin lähtötietojen yhdistelmää, jolla voidaan kuvata jotakin tulevaa tarkastelutilannetta. Ks. myös ”Skenaario”.
* **Ensisijainen määräpaikka** tarkoittaa kiertomatkan ainoaa määräpaikkaa, jos määräpaikkoja on vain yksi, tai ensimmäistä tärkeää määräpaikkaa, mikäli määräpaikkoja on useita.
* **Estimointi** tarkoittaa mallin parametrien määritystä niin, että malli kuvaa käytetyillä lähtötiedoilla mahdollisimman hyvin lähtöaineistossa (nykytila) havaittua käyttäytymistä.
* **HS15-alue** tarkoittaa Helsingin seudun 14 kuntaa ja Siuntiota. HS15-alue koostuu pääkaupunkiseudusta (4 kuntaa) ja kehyskunnista (11 kuntaa ml. Siuntio) eli yhteensä 15 kunnasta. Ks. myös ”Pääkaupunkiseutu”, ”Kehyskunnat” ja ”Aluejako”. 
* **Helsingin seudun työssäkäyntialue** ks. ”Mallialue”.
* **Hyötyfunktio** eli utiliteettifunktio on tapa kuvata matemaattisesti erilaisten valittavien vaihtoehtojen houkuttelevuutta. Tyypillisesti vaihtoehdoista valitaan se, joka tuottaa parhaan hyötyfunktion arvon. Esimerkiksi reitinvalinnassa paras hyöty saavutetaan minimoimalla reitin yleistettyä matka-aikaa eli matkavastusta. 
* **Kehyskunnat** ovat pääkaupunkiseutua ympäröivät muut HS15-alueen kunnat: Hyvinkää, Järvenpää, Kerava, Kirkkonummi, Mäntsälä, Pornainen, Sipoo, Nurmijärvi, Tuusula, Vihti ja Siuntio. Ks. myös ”HS15-alue” ja ”Pääkaupunkiseutu”.  
* **Kiertomatka  (tour)** kuvaa liikkumista kiertomatkan alkupisteestä yhden tai useamman matkan avulla takaisin samaan pisteeseen eli esim. koti–työpaikka–koti. Kiertomatka voi olla myös avoin, jolloin ei palatakaan alkupisteeseen. Monesti kiertomatkasta   käytetään termiä matkaketju, mutta tässä työssä kyseinen termi on päätetty rajata vain sanastossa erikseen kuvattuun merkitykseen (ks. ”Matkaketju”).  
* **Kiertomatkayhdistelmä** kuvaa kokonaisuutta, jossa vuorokauden aikana tehdään monta kiertomatkaa.
* **Konnektori (connector)** on linkki, joka yhdistää sentroidin muuhun liikenneverkkoon.
* **Kulkutapa** kuvaa matkalla käytettävää liikkumismuotoa, esim. henkilöauto, joukkoliikenne tai pyöräily. Pääasiallinen kulkutapa on tyypillisesti se, jolla kuljetaan kilometreissä pisin osuus matkasta.
* **Kulkutavan valinta** on yksi neliporrasmallin vaiheista ja se määrittää ennustettujen matkojen jaon eri kulkutapojen kesken.
* **Kysyntämalli** on HELMET:ssä yhdistelmä erilaisia matemaattisia malleja, jotka yhdessä tuottavat matkojen määrät ja suuntautumisen kulkutavoittain.
* **Lenkki** on yhden matkan kiertomatka, jolla lähtö- ja määräpaikka ovat samat eli esim. ulkoilulenkki lähtien kotoa ja päätyen kotiin.
* **Linkki (link)** on tarjontamallin kahden solmun välinen yhteys, jolla on erilaisia ominaisuustietoja. Linkki voi olla esimerkiksi liittymien välillä oleva katuosuus.
* **Logit-malli** eli logittimalli on tilastollinen malli, joka kuvaa todennäköisyyttä yhden tai useamman muuttujan lineaarisella yhdistelmällä.
* **Logsum** on yleensä hyödyn summan logaritmi. Logsum yhdistää koko ryhmän hyödyn yhteen lukuun. Logsumia käytetään joskus suoraan saavutettavuuden mittarina, koska se yleistää kaikkien määräpaikkojen saavutettavuutta yhdellä luvulla.
* **Lähtöpaikka ja määräpaikka** kuvaavat matkan tai matkaketjun alkupistettä ja päätepistettä.
* **Lähtötieto** on jokin tietolähde tai yksittäinen tieto, jota käytetään pohjalla mallin estimoinnissa tai mallin käytössä. Lähtötietoja voivat olla esimerkiksi erilaiset tiedot väestöstä tai joukkoliikennelinjastosta.
* **Malli** on matemaattinen kuvaus järjestelmästä. Tässä dokumentissa kuvataan Helsingin seudun työssäkäyntialueen liikkumista kuvaavaa malleja.
* **Mallialue** on kunnista koostuva alue, jonka liikennettä HELMET-malli mallintaa. Mallialue käsittää 39 kuntaa: kaikki 26 Uudenmaan kuntaa ja lisäksi Varsinais-Suomen, Kanta-Hämeen ja Päijät-Hämeen maakuntiin kuuluvia kuntia. Näitä kuvataan tässä työssä myös termillä Helsingin seudun työssäkäyntialue. Nämä kunnat on jaettu HS15-alueeseen ja ympäryskuntiin ja HS15-alue edelleen pääkaupunkiseutuun ja kehyskuntiin. HELMET-aluejako käsittää koko mallialueen. Ks. ”Aluejako”, ”HS15-alue”, ”Ympäryskunnat”, ”Pääkaupunkiseutu”, ”Kehyskunnat”.
* **Mallijärjestelmä** on useamman mallin yhdistelmä, jolla voidaan kuvata monimutkaisempia kokonaisuuksia. HELMET-malli on mallijärjestelmä.
* **Matka (trip)** kuvaa siirtymistä paikasta toiseen pihapiirin ulkopuolella. Matka voidaan kulkea yhdellä tai usealla kulkutavalla, joista yksi on pääasiallinen kulkutapa. Myös ulkoilulenkit ovat matkoja. Matkan lähtöpaikka ja määräpaikka on silloin sama paikka. Matka voi sisältää pieniä pysähdyksiä, esimerkiksi kioskille. Jos matka kuitenkin keskeytyy pidemmäksi aikaa, tästä syntyy kaksi matkaa. Esimerkiksi, jos kulkee töistä kotiin, mutta käy välillä kaupassa, meno töistä kauppaan on yksi matka ja matka kaupasta kotiin toinen. Ks. myös ”Osamatka”.
* **Matkaketju (trip chain)** kuvaa liikkumista matkan alkupisteestä päätepisteeseen eri kulkutavoilla. Matkaketju voi olla esimerkiksi matka kotoa töihin, jolloin aluksi kävellään bussipysäkille, sitten matkustetaan työpaikan bussipysäkille, josta kävellään töihin. Alku- ja päätepiste voivat myös olla samoja, jolloin matkaketju on esimerkiksi kävely kotoa kotiin koiran kanssa. Termiä matkaketju käytetään usein myös kuvaamaan vuorokauden aikana tehtyjen matkojen ketjua, mutta HELMET-mallin yhteydessä siitä on päätetty käyttää termiä kierto-matka.
* **Matkatuotos** on yksi neliporrasmallin vaiheista ja se määrittää kuinka monta matkaa syntyy tietyllä alueella tietyn ajanjakson aikana .
* **Määräpaikka** ks. ”Lähtöpaikka ja määräpaikka”
* **Neliporrasmalli** on tyypillinen strategisen tason liikenne-ennustemallin rakenne. Neljä porrasta ovat matkatuotos, suuntautuminen, kulkutavan valinta ja iteroiva reitin valinta eli sijoittelu.
* **Nested logit (suomennos strukturoitu logittimalli)** on logit-mallin versio jossa ominaisuuksia voidaan mallintaa eri tasolla ja keskenään korreloivat valinnat kuuluvat yhteen valintahaaraan. Parametrit voidaan sitten määritellä koko haaralle tai valintakohtaisesti. 
* **Noodi (node)** ks. ”Solmu”
* **OpenPaths EMME** ks. ”EMME”
* **Osamatka** on yhden lähtöpaikasta määräpaikkaan tehdyn matkan yhdellä kulkutavalla tai kulkuvälineellä tehty osa. Esimerkiksi liityntäpysäköintimatka koostuu vähintään kahdesta osamatkasta, joista toinen tehdään autolla ja toinen joukkoliikenteellä.
* **Parametri** tarkoittaa mallin muuttujan kerrointa. Muuttujat ja niiden parametrit määritellään mallin estimoinnissa. 
* **Pohjakysyntä** on mallin lähtötietona käytettävä kysyntä, josta alkaen mallin iteraatiot lähtevät etsimään tasapainotilaa muuttuneilla lähtötiedoilla. Mallin tulokset eivät ole riippuvaisia käytetystä pohjakysynnästä, kun mallia käytetään oikein, mutta sopiva pohjakysyntä voi auttaa mallia saavuttamaan tasapainotilan lyhyemmässä laskenta-ajassa.
* **Pääkaupunkiseutu** tarkoittaa Helsinkiä, Espoota, Kauniaista ja Vantaata. Ks. myös ”HS15-alue”.
* **Reitin valinta** eli sijoittelu on yksi neliporrasmallin vaiheista ja se määrittelee iteroiden ennustettujen matkojen reitit liikennejärjestelmässä valitulla kulkutavalla. HELMET-mallissa sijoitteluun käytetään Bentley Systemsin OpenPaths EMME -ohjelmistoa.
* **Sentroidi (centroid)**, EMMEssä myös zone, on yksittäistä aluetta tarjontamallissa kuvaava solmu, jonka kautta alueen matkatuotos syöttyy verkolle.
* **Sijoittelu** ks. ”Reitin valinta”
* **Sijoittelualue** ks. ”Aluejako”
* **Skenaario** tarkoittaa malliin kuvattua erilaisten lähtötietojen yhdistelmää, jonka pohjalta voidaan laskea ennuste. Kun mitä tahansa mallin lähtötietoa muutetaan, tästä muodostuu uusi ennusteskenaario. Tyypillisesti termillä skenaario tarkoitetaan kokonaisuutta, joka pitää sisällään tietyn ennustetilanteen kaikki ajanjaksot (vrk, aht, pt, iht). Tästä käytetään HELMET-mallin käyttöohjeissa termiä ”Helmet-skenaario”. Tällainen skenaario voisi olla esimerkiksi MAL2023-suunnitelma, johon kuuluu kaikki suunnitelmassa määritellyt toimenpiteet ja lähtötiedot. HELMET-mallin käyttöohjeissa esiintyy lisäksi termi ”Emme-skenaario”, jolla viitataan sijoitteluohjelma EMME:n logiikkaan, missä jokainen ajanjakso muodostaa oman skenaarionsa (scenario) ohjelman sisällä. Esimerkissä MAL2023-suunnitelma (Helmet-skenaario) jakautuisi viiteen Emme-skenaarioon (lähtötiedot, vrk, aht, pt, iht).
* **Solmu** eli noodi (node) on tarjontamallin perusyksikkö, joka kuvaa pistettä, jolla on tietyt ominaisuudet. Solmu voi olla esimerkiksi pysäkki, risteys tai kohta, jossa kadun ominaisuudet muuttuvat. Solmut yhdistyvät toisiinsa linkeillä.
* **Suljettu kiertomatka** on sellainen kiertomatka, joka päättyy samaan pisteeseen kuin mistä se alkoi eli esimerkiksi koti-työpaikka-koti. Ks. myös ”Avoin kiertomatka”.
* **Suuntautuminen** on yksi neliporrasmallin vaiheista ja se määrittelee matkojen lähtö- ja määräpaikkojen yhdistelmät eli mistä paikasta mihin paikkaan matka tehdään.
* **T-arvo** kuvaa muuttujan tilastollista merkitsevyyttä. Itseisarvoltaan pieni t-arvo tarkoittaa, ettei muuttuja ole tilastollisesti merkitsevä. Tilastollisesti merkitsevän muuttujan t-arvo on tyypillisesti pienempi kuin -1,96 tai suurempi kuin 1,96.    
* **Tarjontamalli** on kuvaus liikenneverkosta ja sen ominaisuuksista. Tarjontamallin osia ovat mm. tiet, kadut ja radat ominaisuuksineen, joukkoliikenteen tarjonta sekä liikenteen hinnoittelu.
* **Toissijainen kiertomatka** on kiertomatka, joka sisältää toissijaisen määräpaikan.
* **Toissijainen määräpaikka** on termi, jota käytetään kiertomatkoilla, joihin kuuluu useampi kuin yksi määräpaikka. Ks. myös ”Ensisijainen määräpaikka”
* **U-linja** liikennöi HSL:n alueen ulkopuolelle, mutta hyväksyy HSL-liput sellaisilla matkoilla, jotka alkavat ja päättyvät HSL-alueen sisällä. HELMET-mallin joukkoliikenneverkolla U-linjat on kuvattu kahteen kertaan: koko reitin kattavana linjana, joka kuvaa pitkämatkaista liikennettä linjalla, sekä HSL-alueen sisällä HSL-linjana, jossa kelpaavat HSL-liput ja joka kuvaa HSL-alueen sisäisiä matkoja U-linjalla.
* **Ulkoinen liikenne** tarkoittaa matkoja, joiden lähtö- tai määräpaikka on HELMET-mallialueen ulkopuolella. Ulkoisen liikenteen mallintamiseen käytetään eri menettelyä kuin HS15-alueella tai ympäryskuntien alueella. Ks. myös ”Mallialue”.
* **Validointi** tarkoittaa mallin tulosten vertailua riippumattomiin liikkumista kuvaaviin aineistoihin, millä varmistetaan, että malli ennakoi nykytilalle oikean tuloksen. Validointiaineistona ei voida käyttää samaa tietolähdettä, jota on käytetty mallin estimoinnissa.
* **Vastus** kuvaa matkasta matkan tekijälle syntyviä haittoja, kuten etäisyyttä, matka-aikaa ja kustannuksia. Malliajossa hyödynnetään vastusmatriiseja, joihin on koottu eri alueparien väliset vastukset. Matkalle optimaalinen reitti löytyy etsimällä pienin vastus, joka eri matkavaihtoehdoilla on tarjolla. Vastukset muuttuvat mallin iteraatioiden myötä, kunnes liikennejärjestelmä on tasapainotilassa, jossa yksittäinen liikkuja ei omilla valinnoillaan pysty kulkutavan valinnan, määräpaikan valinnan tai reitinvalinnan avulla parantamaan hyötyfunktionsa arvoa.
* **Viivytysfunktio** kuvaa liikennemäärästä johtuvia viiveitä tietyllä tie- tai katuosuudella. Viivytysfunktiot ovat osa matka-ajan laskentaa.
* **Yksisuuntainen matka** ks. ”Matka”
* **Ympäryskunnat** tarkoittavat HELMET-mallin reuna-alueilla sijaitsevia kuntia, jotka eivät kuulu HS15-alueeseen. Ympäryskuntia ovat Askola, Hanko, Hattula, Hausjärvi, Hollola, Hämeenlinna, Inkoo, Janakkala, Karkkila, Kärkölä, Lahti, Lapinjärvi, Lohja, Loppi, Loviisa, Myrskylä, Orimattila, Porvoo, Raasepori, Riihimäki, Salo, Somero ja Tammela. Ks. myös ”HS15-alue” ja ”Helsingin seudun työssäkäyntialue”.

---
nav_order: 6
sort: 6
---

# Tulokset

Tulosten tallennuskansiopolku määritellään Helmet-käyttöliittymän projektiasetuksissa (ks. "[Asennus](kaytto-ohje.md)"). 
Kunkin Helmet-skenaarion (malliajon) tulokset tallentuvat kyseisen Helmet-skenaarion nimellä nimettyyn alikansioon. 
Näihin kansioihin tallentuu kahdentyyppisiä tiedostoja matriiseja ja tekstitiedostoja, joita on kuvattu tässä ohjeessa tarkemmin.

Näiden lisäksi sijoittelutulokset jäävät talteen Emme-pankkiin.
Lisää tietoja sijoittelun tuloksista ja niiden analysoinnista löytyy Emmen dokumentaatiosta. 
Huom! Jos ajat samassa Emme-pankissa useita Helmet-skenaarioita, tarkat matriisitulokset jäävät Emmeen talteen vain, 
jos config-tiedostoon on määritelty matriiseille omat tallennuspaikat (ks. [Mallijärjestelmän käyttö](mallitoiden_yleisohje.md)).

Lisää tietoja kysyntämallien toiminnallisuuksista ja niiden tulosten merkityksestä saat
(KORJATTAVA) [malliraportista](https://staticfiles.hsl.fi/globalassets/julkaisuarkisto/2020/6_2020_helsingin_seudun_tyossakayntialueen_liikenne-ennustejarjestelman_kysyntamallit.pdf).

## Tulokset verrattuna HELMET 4.1:een


Suurimmat eroavaisuudet HELMET 5 ja HELMET 4.1 malliversioiden välillä johtuvat mallin estimoinnista, joka on HELMET 5:ssä tehty vuoden 2023 Liikkumistutkimusaineistolla. Uudessa liikkumistutkimuksessa vuorokauden keskimääräinen matkamäärä on laskenut aiemmasta, johtuen oletettavasti koronaviruspandemian aiheuttamasta etätyön lisääntymisestä. Kulkutapajakauma on myös muuttunut aiemmasta. Kävelyn osuus on hieman kasvanut, kun muiden on laskenut.

Vapaa-ajan matkoista aiempaa suurempi osuus tehdään joukkoliikenteellä: Autolla tehtyjen vapaa-ajan matkojen suorite on laskenut, kun taas joukkoliikenteellä tehtyjen vapaa-ajan matkojen suorite on kasvanut.

Pyöräilyn matkamäärät mallissa ovat huomattavasti alhaisemmalla tasolla kuin HELMET 4.1:ssä. Syynä on kuitenkin HELMET 4.1:n virhe; mallin validoinnissa oli oletettavasti käytetty kesällä laskettuja arkivuorokauden pyöräliikenteen määriä, kun malli muuten kuvaa syksyn arkivuorokauden liikkumista. HELMET 5:ssä pyöräliikenteen mallintamisen kehittäminen on ollut keskeinen kehitystyön kohde, ja pyöräilyn matkamäärät ovat nyt oikeassa suhteessa verrattuna muuhun liikenteeseen.

Kantakaupungissa aiemmin havaitut liian suuret autoliikenteen määrät on pääosin saatu korjattua tarkistamalla sisääntuloväylien välityskykyä ja lisäämällä pysäköintiin kuluvan ajan apumalli.


## HELMET 5.0 -tuloksiin liittyviä epävarmuuksia


Mallia laadittaessa sen antamia tuloksia on verrattu monipuolisesti erilaiseen havaintoaineistoon ja pyritty saamaan tulokset vastaamaan mahdollisimman hyvin havaintoja.
Tuloksiin liittyy silti tiettyjä epävarmuuksia ja rajoitteita, joista on nostettu tähän keskeisimpiä havaintoja.
Mallin testausta ja testien tuloksia on kuvattu laajemmin raportissa (KORJATTAVA)
[Helsingin seudun työssäkäyntialueen liikenne-ennustejärjestelmän kysyntämallit 2020](https://staticfiles.hsl.fi/globalassets/julkaisuarkisto/2020/6_2020_helsingin_seudun_tyossakayntialueen_liikenne-ennustejarjestelman_kysyntamallit.pdf) (luvut 12 ja 13).

Mallin tuottama kuvaus nykytilanteen liikkumisesta on aiempaa parempi, eikä kysynnän mallintamiseen liittyviä merkittäviä järjestelmätason virheitä ole havaittu.

Kuitenkin paikallisia puutteita on edelleen. Esimerkiksi kehäteiden liikenne hidastuu liikaa ruuhkautumisen vaikutuksesta, mitä ei ole pystytty korjaamaan HELMET 5.0 malliversioon. Mallissa käytössä oleva teiden luokittelu on mahdollisesti liian karkea, jotta sillä voitaisiin kuvata kaikkia tieyhteyksiä riittävällä tarkkuudella. Kehäteiden liikennemäärät ovat kuitenkin niin merkittäviä, että HSL selvittää ongelman syyt, ja se korjataan myöhempään malliversioon.

Joukkoliikenteen osalta etenkin Itä-Helsingissä metron houkuttelemat nousijamäärät ovat liian korkeita, mihin ei ole löydetty selkeää selitystä. 

<!-- Muuta? -->

## Tuloskansion tekstitiedostojen kuvaukset

### Tiedostoissa käytetyt lyhenteet ja termit

#### Helsingin seudun asukkaiden kiertomatkojen päätyypit

| Koodi | Kiertomatkan tyyppi   |
|-------|-----------------------|
| hw    | koti - työ                            |
| hc    | koti - koulu                          |
| hu    | koti - opiskelu                       |
| hs    | koti - ostos/asiointi                 |
| ho    | koti - muu                            |
| hh    | koti - koti (lenkki)                  |
| hoo   | toissijaisen määräpäikän kiertomatka  |
| wo    | työ - joku                            |
| oo    | muu kiertomatka                       |
| *wh*  | työ - koti [1]                        |

[1] Tyyppi *wh* on käännetty versio kotiperäisten työmatkojen (hw) mallista. Sitä käytetään työvoiman saavutettavuuslaskennassa.
Tyyppi *hoo* kuvaa kaksi uutta matkaa suoran meno- tai paluumatkan sijaan. Tuloksissa tämä ryhmä näkyy vain accessibility.txt tiedostossa.

#### Ympäryskuntien asukkaiden kiertomatkojen päätyypit

| Koodi | Kiertomatkan tyyppi |
|-------|---------------------|
| hwp   | koti - työ          |
| hop   | koti - muu          |
| oop   | muu kiertomatka     |

#### Kulkutavat

| Koodi | Kulkutapa      |
|-------|----------------|
| c     | auto                |
| t     | joukkoliikenne      |
| b     | polkupyörä          |
| w     | jalankulku          |
| p     | liityntäpysäköinti  |

#### Sijoitteluluokat

| Koodi   | Kiertomatkan tyyppi                         |
|---------|---------------------------------------------|
| work    | kotiperäiset työ-, koulu- ja opiskelumatkat |
| leisure | muut matkat                                 |

| Nimi          | Vastine suomeksi                   | Sijoitteluyksikkö |
|---------------|------------------------------------|-------------------|
| transit       | joukkoliikenne ml. liityntä        | henkilö           |
| aux_transit   | joukkoliikenteen liityntä erikseen | henkilö           |
| bike          | polkupyörä                         | henkilö           |
| car           | henkilöauto                        | ajoneuvo          |
| van           | pakettiauto                        | ajoneuvo          |
| truck         | kuorma-auto                        | ajoneuvo          |
| trailer_truck | yhdistelmäajoneuvo                 | ajoneuvo          |
| bus [1]       | linja-auto                         | ajoneuvo          |

[1] Busseja ei varsinaisesti sijoitella, koska ne liikkuvat ennalta määriteltyjä reittejä pitkin,
mutta ne ovat autosijoittelussa taustaliikenteenä.

#### Väylätyypit

| Koodi | Väylätyyppi                                                  |
|-------|--------------------------------------------------------------|
| 1     | Moottoritiet                                                 |
| 2     | Maantiet / Useampikaistaiset kaupunkiväylät eritasoliittymin |
| 3     | Useampikaistaiset pääkadut tasoliittymin valoilla            |
| 4     | Pääkadut                                                     |
| 5     | Kokooja-/tonttikadut                                         |

#### Suuralueet

| Koodi          | Selitys                                         | Sijoittelualueet |
|----------------|-------------------------------------------------|------------------|
| helsinki_cbd   | Helsingin kantakaupunki                         | 0 - 999          |
| helsinki_other | Muu Helsinki                                    | 1 000 - 1 999    |
| espoo_vant_kau | Muu pääkaupunkiseutu                            | 2 000 - 5 999    |
| surrounding    | Kehyskunnat (+Siuntio)                          | 6 000 - 15 999   |
| surround_train | Junaliikenteeseen <br /> tukeutuvat kehyskunnat (ml. Siuntio) | 6 000 - 6 999 <br /> 10 000 - 11 999 <br /> 13 000 - 14 999 <br /> 15 500 - 15 999 |
| surround_other | Muut kehyskunnat                                | 7 000 - 9 999 <br /> 12 000 - 12 999 <br /> 15 000 - 15 499 |
| peripheral     | Ympäryskunnat                                   | 16 000 - 30 999  |

### Tiedostot

| Tiedoston nimi                               | Selite | Tarkempi kuvaus |
|----------------------------------------------|--------|-----------------|
| accessibility.txt                            | Kysyntämallin logsum-muuttujat sijoittelualueittain | Logsumit ovat kiertomatkatyyppi- ja kulkutapakohtaisia. Kulkutapamalleista saadaan yhdistetyt logsumit kaikille kulkutavoille. Logsumit voidaan tulkita saavutettavuusmittareiksi. |
| aggregated_demand.txt aggregated_demand.xlsx | Aggregoidut vuorokauden kysyntämatriisit (kiertomatkoja) suuralueittain |
| agents.txt                                   | Agenttilista väestötieteellisine ominaisuuksineen | :exclamation: Vain agenttiajoissa |
| attraction.txt                               | Kiertomatka-attraktio kiertomatkatyypeittäin ja sijoittelualueittain | Kertoo, kuinka monessa kiertomatkassa kyseinen alue on päämäärä |
| car_accessibility.txt                        | Kysyntämallin logsum-muuttuja-aggregointi autokulkutavalla sijoittelualueittain |  |
| car_density.txt                              | Autotiheys (auto/asukas) sijoittelualueittain |
| car_density_areas.txt                        | Autotiheys (auto/asukas) suuralueittain |
| car_density_municipalities.txt               | Autotiheys (auto/asukas) kunnittain |
| car_use.txt                                  | Henkilöauton pääasiallisten käyttäjien (HAP) osuus väestöstä sijoittelalueittain |
| car_use_areas.txt                            | Henkilöauton pääasiallisten käyttäjien (HAP) osuus väestöstä suuralueittain |
| car_use_municipalities.txt                   | Henkilöauton pääasiallisten käyttäjien (HAP) osuus väestöstä kunnittain |
| demand_convergence.txt                       | Kysyntämallin konvergoituminen car_work-kysyntämatriisista laskettuna |  |
| generation.txt                               | Vuorokauden kiertomatkatuotos kiertomatkatyypeittäin sijoittelualueittain |  |
| impedance_ratio.txt                          | Joukkoliikenteen ja henkilöautoliikenteen matka-aika- ja matkakustannussuhteet aamuruuhkassa sijoittelualueittain | Eri matkakohteiden matka-ajat ja -kustannukset on painotettu työmatkojen määrillä kulkutavoittain. Lukuja käytetään autonomistusmallin muuttujina. |
| link_lengths.txt                             | Väylätyyppien yhteenlaskettu pituus (km) verkolla | |
| links.txt                                    | Linkit ominaisuuksineen | :exclamation: Saatavilla vain [Emme-Desktop skriptin](https://github.com/HSLdevcom/helmet-model-system/blob/olusanya/Scripts/emme_tools/helmet_link_printing.py) kautta |
| mode_analysis.csv                            | Kulkutapajakauman muutos alkukysynnästä viimeiseen iteraatioon | :exclamation: Uusi versiossa 5.0 |
| mode_share.txt                               | Kokonaiskulkutapajakaumat kiertomatkatyyppeittäin |
| noise_areas.txt                              | Suuralueiden melualueiden pinta-alat ja väestömäärät |  |
| origins_demand.txt                           | Vuorokauden kiertomatkatuotokset kulkutavoittain ja sijoittelualueittain |
| origins_demand_areas.txt                     | Vuorokauden kiertomatkatuotokset kulkutavoittain ja suuralueittain |
| origins_shares.txt                           | Kokonaiskulkutapajakaumat sijoittelualueittain |
| own_zone_demand.txt                          | Sijoittelualueiden sisäisten kiertomatkojen (joiden alkupiste ja loppupiste ovat samalla sijoittelualueella) määrät suuralueittain |
| pnr_facilities.txt                           | Liityntäpysäköintilaitosten käyttöaste ja vastukset | :exclamation: Uusi versiossa 5.0 |
| result_summary.txt                           | Yhteenveto mallialueen tuloksista: työpaikkojen kasautuminen, työvoimasaavutettavuus, sijoiteltu kysyntä (meno-paluumatkoja), etäisyyssuoritteet, saavutettavuus, kulkutapajakauma (HS15 kiertomatkat, HS15 matkat, koko alueen kiertomatkat)  | Kävely ei sisälly kysyntään, koska sitä ei sijoitella |
| savu.txt                                     | SAVU-vyöhyke, jolle sijoittelualue kuuluu |  |
| sustainable_accessibility.txt                | Kysyntämallin logsum-muuttujat ilman autokulkutapaa sijoittelualueittain ja kiertomatkatyypeittäin |  |
| tour_combinations.txt  | Vuorokauden kiertomatkayhdistelmien tuotosluvut ikäryhmittäin |  |
| tour_combinations.xlsx | Vuorokauden kiertomatkayhdistelmien tuotosluvut ikäryhmittäin |  |
| tours.txt                                    | Agenttien tekemät kiertomatkat ominaisuuksineen | :exclamation: Vain agenttiajoissa |
| transit_congestion.csv                       | Joukkoliikennelinjojen täyttöaste suhteessa istuma- ja kokonaiskapasiteettiin | :exclamation: Uusi versiossa 5.0 |
| transit_kms.txt                              | Vuorokauden etäisyys- ja ajo-aikasuoritteet (km, min) joukkoliikenteen ajoneuvoille |
| transit_stations.txt                         | Juna- ja metroasemien lukumäärä |  |
| trip_lengths.txt                             | Vuorokauden kiertomatkatuotokset kiertomatkatyyppeittäin, kulkutavoittain ja etäisyysluokittain | Etäisyysluokka perustuu henkilöauton ajoetäisyyteen kilometreissa. |
| trips_areas.txt                              | Vuorokauden (meno+paluu)matkatuotokset kulkutavoittain ja suuralueittain |  |
| validation.html                              | Automaattisen validoinnin tulokset. Ajanjaksokohtaiset liikennemäärien ja nopeuksien vertailut laskentapisteissä | :exclamation: Uusi versiossa 5.0 |
| vehicle_kms_areas.txt                        | Sijoitteluluokkien (sekä joukkoliikenteen liityntäkävely erikseen) ja bussien etäisyyssuoritteet (km) koko vuorokaudelle suuralueittain |  |
| vehicle_kms_vdfs.txt                         | Sijoitteluluokkien (sekä joukkoliikenteen liityntäkävely erikseen) ja bussien etäisyyssuoritteet (km) koko vuorokaudelle väylätyypeittäin |  |
| vehicle_kms_vdfs_areas.txt                   | Kokonaisetäisyyssuoritteet (km) koko vuorokaudelle väylätyypeittäin ja suuralueittain |  |
| workplace_accessibility.txt                  | Työpaikkojen kasautuminen (hw, koti-työ-mallin logsum-muuttuja muunnettu henkilömääräksi) ja työvoimasaavutettavuus (wh, työ-koti-mallin logsum-muuttuja muunnettu henkilömääräksi) sijoittelualueittain |  Nimi muutettu versiossa 4.1.0, aikaisemmin workforce_accessibility.txt |
| workplace_accessibility_areas.txt            | Työpaikkojen kasautuminen (hw, koti-työ-mallin logsum-muuttuja muunnettu henkilömääräksi) ja työvoimasaavutettavuus (wh, työ-koti-mallin logsum-muuttuja muunnettu henkilömääräksi) suuralueittain |  |

## Tuloskansion matriisitiedostojen kuvaukset

Matriisitiedostot ovat [omx-formaatissa](https://github.com/osPlanning/omx/wiki) alakansiossa *Matrices*.
Sekä kysyntä- että vastusmatriisit ovat tuntimatriiseja.

| Koodi | Tunti           |
|-------|-----------------|
| aht   | aamuhuipputunti |
| pt    | päivätunti      |
| iht   | iltahuipputunti |

Tuntimatriisit aggregoidaan mallijärjestelmässä koko vuorokauteen kiinteillä kertoimilla (ks. [sijoitteluskripti](https://github.com/HSLdevcom/helmet-model-system/blob/master/Scripts/parameters/assignment.py#L122)).

| Tiedoston nimi (jossa xxx on tunnin koodi) | Selite | Tarkempi kuvaus |
|--------------------------------------------|--------|-----------------|
| demand_xxx.txt | Kysyntämatriisit kulkumuodoittain | Henkilöauto-, joukkoliikenne- ja polkupyörämatriisit on jaettu työ- ja vapaa-ajan matkojen matriiseihin. |
| time_xxx.txt   | Matka-aikamatriisit [min] kulkumuodoittain | Henkilöauto- ja joukkoliikennematriisit on jaettu työ- ja vapaa-ajan matkojen matriiseihin. |
| dist_xxx.txt   | Matkaetäisyysmatriisit [km] kulkumuodoittain | Henkilöauto- ja joukkoliikennematriisit on jaettu työ- ja vapaa-ajan matkojen matriiseihin. |
| cost_xxx.txt   | Tiemaksu- sekä joukkoliikenteen kuukausilippukustannusmatriisit [eur] kulkumuodoittain | Henkilöauto- ja joukkoliikennematriisit on jaettu työ- ja vapaa-ajan matkojen matriiseihin. |



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
[Helsingin seudun työssäkäyntialueen liikenne-ennustemallijärjestelmä 2025](https://staticfiles.hsl.fi/globalassets/julkaisuarkisto/2026/helsingin-seudun-tyossakayntialueen-liikenne-ennustemallijarjestelma-2025_5-2026.pdf).

## Tulokset verrattuna HELMET 4.1:een


Suurimmat eroavaisuudet HELMET 5 ja HELMET 4.1 malliversioiden välillä johtuvat mallin estimoinnista, joka on HELMET 5:ssä tehty vuoden 2023 Liikkumistutkimusaineistolla. Uudessa liikkumistutkimuksessa vuorokauden keskimääräinen matkamäärä on laskenut aiemmasta, johtuen oletettavasti koronaviruspandemian aiheuttamasta etätyön lisääntymisestä. Kulkutapajakauma on myös muuttunut aiemmasta. Kävelyn osuus on hieman kasvanut, kun muiden on laskenut.

Vapaa-ajan matkoista aiempaa suurempi osuus tehdään joukkoliikenteellä: Autolla tehtyjen vapaa-ajan matkojen suorite on laskenut, kun taas joukkoliikenteellä tehtyjen vapaa-ajan matkojen suorite on kasvanut.

Pyöräilyn matkamäärät mallissa ovat huomattavasti alhaisemmalla tasolla kuin HELMET 4.1:ssä. Syynä on kuitenkin HELMET 4.1:n virhe; mallin validoinnissa oli oletettavasti käytetty kesällä laskettuja arkivuorokauden pyöräliikenteen määriä, kun malli muuten kuvaa syksyn arkivuorokauden liikkumista. HELMET 5:ssä pyöräliikenteen mallintamisen kehittäminen on ollut keskeinen kehitystyön kohde, ja pyöräilyn matkamäärät ovat nyt oikeassa suhteessa verrattuna muuhun liikenteeseen.

Kantakaupungissa aiemmin havaitut liian suuret autoliikenteen määrät on pääosin saatu korjattua tarkistamalla sisääntuloväylien välityskykyä ja lisäämällä pysäköintiin kuluvan ajan apumalli.


## HELMET 5.0 -tuloksiin liittyviä epävarmuuksia


Mallia laadittaessa sen antamia tuloksia on verrattu monipuolisesti erilaiseen havaintoaineistoon ja pyritty saamaan tulokset vastaamaan mahdollisimman hyvin havaintoja.
Tuloksiin liittyy silti tiettyjä epävarmuuksia ja rajoitteita, joista on nostettu tähän keskeisimpiä havaintoja.
Mallin testausta ja testien tuloksia on kuvattu laajemmin raportissa 
[Helsingin seudun työssäkäyntialueen liikenne-ennustemallijärjestelmä 2025](https://staticfiles.hsl.fi/globalassets/julkaisuarkisto/2026/helsingin-seudun-tyossakayntialueen-liikenne-ennustemallijarjestelma-2025_5-2026.pdf) (luku 8).

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
| attraction.txt                               | Kiertomatka-attraktio kiertomatkatyypeittäin ja sijoittelualueittain | Kertoo, kuinka monessa kiertomatkassa kyseinen alue on päämäärä |
| car_accessibility.txt                        | Kysyntämallin logsum-muuttuja-aggregointi autokulkutavalla sijoittelualueittain |  |
| car_density.txt                              | Autotiheys (auto/asukas) sijoittelualueittain |
| car_density_areas.txt                        | Autotiheys (auto/asukas) suuralueittain |
| car_density_municipalities.txt               | Autotiheys (auto/asukas) kunnittain |
| car_use.txt                                  | Henkilöauton pääasiallisten käyttäjien (HAP) osuus väestöstä sijoittelalueittain |
| car_use_areas.txt                            | Henkilöauton pääasiallisten käyttäjien (HAP) osuus väestöstä suuralueittain | Vain 7+ vuotiaat
| car_use_municipalities.txt                   | Henkilöauton pääasiallisten käyttäjien (HAP) osuus väestöstä kunnittain | Vain 7+ vuotiaat
| demand_convergence.txt                       | Kysyntämallin konvergoituminen car_work-kysyntämatriisista laskettuna |  |
| generation.txt                               | Vuorokauden kiertomatkatuotos kiertomatkatyypeittäin sijoittelualueittain |  |
| impedance_ratio.txt                          | Joukkoliikenteen ja henkilöautoliikenteen matka-aika- ja matkakustannussuhteet aamuruuhkassa sijoittelualueittain | Eri matkakohteiden matka-ajat ja -kustannukset on painotettu työmatkojen määrillä kulkutavoittain. Lukuja käytetään autonomistusmallin muuttujina. |
| link_lengths.txt                             | Väylätyyppien yhteenlaskettu pituus (km) verkolla | |
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

## Emme-projektin matriisit

### Emme-matriisien sisältö

(Disclaimer: luonnos tehty tekoälyllä, tarkistettu)
Helmet-mallijärjestelmä tallentaa sijoittelussa käytettävät kysyntä- ja vastusmatriisit Emme-pankkiin. Matriisin tunnuksen (`mf`) viimeiset kaksi numeroa kuvaavat matriisin sisältöä alla olevan taulukon mukaisesti. Yleensä joka matriisityyppi alkaa seuraavalla kymmenellä, mutta jos esim. sijoitteluluokkia olisi enemmän, matriisityyppiin voi kuulua myös enemmän kuin 10 matriisia. 
Matriisin koodi riippuu aikajakson muuttujasta eli SAVE_MATRICES_IN_EMME lipusta. Jos lippu ei ole päällä, matriisit tallennetaan mf1-mf99 väliin. Jos on (ja ensimmäinen matriisin numero on UI:ssa oletettu 100) sitten joka aikajakso tallennetaan omaan väliin, eli aht 100-199, pt 200-299 ja iht 300-399. Matriisien vertailua varten suoraan Emmessä (esim. ve0 ja ve1 skenaario), kannattaa myös seuraavalle skenaariolle valita ensimmäisen matriisin numerona vaikka 400, niin seuraava skenario tallentuu väliin 400-699.  

| Matriisi | Nimi                           | Kuvaus                                                                  |
| -------- | ------------------------------ | ----------------------------------------------------------------------- |
| `mf1`    | `demand_car_work`              | Henkilöautojen työmatkojen kysyntä                                      |
| `mf2`    | `demand_car_leisure`           | Henkilöautojen vapaa-ajan matkojen kysyntä                              |
| `mf3`    | `demand_transit_work`          | Joukkoliikenteen työmatkojen kysyntä                                    |
| `mf4`    | `demand_transit_leisure`       | Joukkoliikenteen vapaa-ajan matkojen kysyntä                            |
| `mf5`    | `demand_bike`                  | Polkupyöräliikenteen kysyntä                                            |
| `mf7`    | `demand_trailer_truck`         | Yhdistelmäajoneuvojen kysyntä                                           |
| `mf8`    | `demand_truck`                 | Kuorma-autojen kysyntä                                                  |
| `mf9`    | `demand_van`                   | Pakettiautojen kysyntä                                                  |
| `mf11`   | `time_car_work`                | Henkilöauton matka-aika, työmatkat                                      |
| `mf12`   | `time_car_leisure`             | Henkilöauton matka-aika, vapaa-ajan matkat                              |
| `mf13`   | `time_transit_work`            | Joukkoliikenteen matka-aika, työmatkat                                  |
| `mf14`   | `time_transit_leisure`         | Joukkoliikenteen matka-aika, vapaa-ajan matkat                          |
| `mf15`   | `time_bike`                    | Polkupyörän matka-aika                                                  |
| `mf16`   | `time_walk`                    | Kävelyn matka-aika                                                      |
| `mf17`   | `time_trailer_truck`           | Yhdistelmäajoneuvon matka-aika                                          |
| `mf18`   | `time_truck`                   | Kuorma-auton matka-aika                                                 |
| `mf19`   | `time_van`                     | Pakettiauton matka-aika                                                 |
| `mf21`   | `dist_car_work`                | Henkilöauton matkaetäisyys, työmatkat                                   |
| `mf22`   | `dist_car_leisure`             | Henkilöauton matkaetäisyys, vapaa-ajan matkat                           |
| `mf23`   | `dist_transit_work`            | Joukkoliikenteen matkaetäisyys, työmatkat                               |
| `mf24`   | `dist_transit_leisure`         | Joukkoliikenteen matkaetäisyys, vapaa-ajan matkat                       |
| `mf25`   | `dist_bike`                    | Polkupyörän matkaetäisyys                                               |
| `mf26`   | `dist_walk`                    | Kävelyn matkaetäisyys                                                   |
| `mf27`   | `dist_trailer_truck`           | Yhdistelmäajoneuvon matkaetäisyys                                       |
| `mf28`   | `dist_truck`                   | Kuorma-auton matkaetäisyys                                              |
| `mf29`   | `dist_van`                     | Pakettiauton matkaetäisyys                                              |
| `mf31`   | `cost_car_work`                | Henkilöauton matkakustannus, työmatkat                                  |
| `mf32`   | `cost_car_leisure`             | Henkilöauton matkakustannus, vapaa-ajan matkat                          |
| `mf33`   | `cost_transit_work`            | Joukkoliikenteen matkakustannus, työmatkat                              |
| `mf34`   | `cost_transit_leisure`         | Joukkoliikenteen matkakustannus, vapaa-ajan matkat                      |
| `mf37`   | `cost_trailer_truck`           | Yhdistelmäajoneuvon matkakustannus                                      |
| `mf38`   | `cost_truck`                   | Kuorma-auton matkakustannus                                             |
| `mf39`   | `cost_van`                     | Pakettiauton matkakustannus                                             |
| `mf41`   | `gen_cost_car_work`            | Henkilöauton yleistetty matkakustannus, työmatkat                       |
| `mf42`   | `gen_cost_car_leisure`         | Henkilöauton yleistetty matkakustannus, vapaa-ajan matkat               |
| `mf47`   | `gen_cost_trailer_truck`       | Yhdistelmäajoneuvon yleistetty matkakustannus                           |
| `mf48`   | `gen_cost_truck`               | Kuorma-auton yleistetty matkakustannus                                  |
| `mf49`   | `gen_cost_van`                 | Pakettiauton yleistetty matkakustannus                                  |
| `mf53`   | `congest_time_transit_work`    | Joukkoliikenteen ruuhkautumisen huomioiva matka-aika, työmatkat         |
| `mf54`   | `congest_time_transit_leisure` | Joukkoliikenteen ruuhkautumisen huomioiva matka-aika, vapaa-ajan matkat |

### Joukkoliikennesijoittelun matriisit

Joukkoliikennesijoittelu tuottaa kokonaisvastuksen lisäksi matriiseja, joissa matkan eri osatekijät on eroteltu. Samat matriisit tuotetaan erikseen työmatkojen (`transit_work`) ja muiden matkojen (`transit_leisure`) sijoitteluluokille.

| Matriisi        | Muuttuja                      | Sisältö / mistä muodostuu                                                                                                                                                                         |
| --------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `mf61` / `mf71` | `total_travel_time`           | **Matkan todellinen kokonaisaika:** odotusaika + liikennevälineessäoloaika + liityntä- ja vaihtokävely + nousuihin liittyvä aika                                                                  |
| `mf62` / `mf72` | `actual_total_waiting_times`  | **Kaikki odotusajat:** ensimmäisen liikennevälineen odotus + vaihtojen yhteydessä tapahtuva odotus                                                                                                |
| `mf63` / `mf73` | `actual_first_waiting_times`  | **Ensimmäinen odotusaika:** lähtöpaikan ja ensimmäisen joukkoliikennevälineeseen nousun välinen odotus. Sisältyy `actual_total_waiting_times`-matriisiin eikä sitä pidä summata siihen uudelleen. |
| `mf64` / `mf74` | `actual_in_vehicle_times`     | **Liikennevälineessä vietetty aika:** bussissa, raitiovaunussa, metrossa, junassa, lautassa ym. tapahtuva matkustusaika                                                                           |
| `mf65` / `mf75` | `actual_aux_transit_times`    | **Liityntä- ja vaihtokävely:** kävely lähtöpaikasta pysäkille/asemalle, kävelyt vaihtojen yhteydessä sekä kävely viimeiseltä pysäkiltä/asemalta määränpäähän                                      |
| `mf66` / `mf76` | `actual_total_boarding_times` | **Nousuihin liittyvä aika/vastus:** liikennemuotokohtaiset nousuvastukset sekä vuorovälin hajonnasta aiheutuva lisävastus                                                                         |
| `mf67` / `mf77` | `avg_boardings`               | **Nousujen lukumäärä:** odotettu joukkoliikennevälineisiin nousujen määrä. Ensimmäinen nousu mukaan lukien; vaihtojen määrä on siten likimäärin `avg_boardings - 1`.                              |
| `mf68` / `mf78` | `actual_total_boarding_costs` | **Nousuihin liittyvä erillinen kustannus/vastus:** erityisesti vaihdoille asetettu vaihtovastus. Ei ole sama asia kuin `actual_total_boarding_times`.                                             |

Matriiseista `mf61`–`mf68` koskevat luokkaa `transit_work` ja matriisit `mf71`–`mf78` luokkaa `transit_leisure`.

#### Kokonaismatka-ajan komponentit

`total_travel_time` voidaan esittää komponenttitasolla seuraavasti:

```text
total_travel_time
    = actual_total_waiting_times
    + actual_in_vehicle_times
    + actual_aux_transit_times
    + actual_total_boarding_times
```

Toisin sanoen:

```text
kokonaismatka-aika
    = odotus
    + aika liikennevälineessä
    + liityntä- ja vaihtokävely
    + nousuihin liittyvä aika
```

`actual_first_waiting_times` on `actual_total_waiting_times`-muuttujan osajoukko, joten sitä ei lisätä kokonaisaikaan erikseen. Vastaavasti `avg_boardings` kuvaa nousujen lukumäärää eikä aikaa, ja `actual_total_boarding_costs` on erillinen sijoitteluvastus.

#### Sijoittelussa käytetty vastus

Joukkoliikenteen reitinvalinta ei perustu suoraan yllä olevaan todelliseen kokonaismatka-aikaan. Eri matkan osille käytetään sijoittelussa erilaisia painoja. Nykyisessä Helmet-mallissa esimerkiksi:

| Komponentti                               | Sijoittelun paino |
| ----------------------------------------- | ----------------: |
| Liikennevälineessäoloaika                 |             `1.0` |
| Odotusaika                                |             `1.5` |
| Liityntä- ja vaihtokävely (`aux_transit`) |            `1.75` |
| Nousuaika/-vastus                         |             `1.0` |

Lisäksi vaihtojen yhteydessä käytetään erillistä vaihtovastusta. Sen arvo on työmatkoilla (`transit_work`) 3 minuuttia ja muilla matkoilla (`transit_leisure`) 5 minuuttia vaihtoa kohti.

Ensimmäiselle odotukselle ja myöhemmille odotuksille käytetään myös eri vuoroväliosuutta: ensimmäisellä nousulla odotusaika perustuu 0,3 × vuoroväliin ja myöhemmillä nousuilla 0,5 × vuoroväliin.



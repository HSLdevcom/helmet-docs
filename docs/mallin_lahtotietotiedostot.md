---
nav_order: 5
sort: 5
---

# Lähtötiedot

## Syöttö- ja lähtötietojen kuvaus

Malliajo vaatii aina sekä syöttö- että lähtötietoja. Lähtötiedot kuvaavat malliajon lähtötilannetta, johon syöttötiedoissa kuvattua skenaariota verrataan. Käytännössä lähtötiedot kuvaavat estimoinnin aikaista tilannetta, ja syöttötiedot kuvaavat tarkasteltavana olevaa skenaariota, esimerkiksi MAL suunnitelman tarkasteluvuoden tavoitetilannetta.

### Ennusteskenaarioiden syöttötiedot

Kansio sisältää kullekin tarkasteluvuodelle/skenaariolle alikansion, jossa on lähtötiedot mm. maankäytön ja kustannusten osalta.
Kunkin tiedoston alussa on kuvattu mitä tiedosto sisältää ja mistä tiedot tulevat.
Kansiossa on oltava yksi kappale kustakin tiedostotyypista .cco, .edu, .ext, .lnd, .pop, .pnr, .prk, .tco, .trk sekä .wrk.
Tiedostojen nimillä ei ole merkitystä, ja ne voivat poiketa toisistaan (kansiossa voi esim. olla 2023.pop ja 2023_b.wrk)

**Tiedostot**

<!-- html lista, jotta taulukko ei tipu listan ulkopuolelle -->

<ul>
<li> <b>car</b> = <i>valinnainen tiedosto</i>, johon voi syöttää aluekohtaiset pysäköintinormit (autoa/asukas) sarakkeeseen `prknorm`, esimerkiksi tällä tavalla:  

  <table><thead>
    <tr>
      <th></th>
      <th>prknorm</th>
    </tr></thead>
  <tbody>
    <tr>
      <td>191</td>
      <td>0.7</td>
    </tr>
    <tr>
      <td>192</td>
      <td>0.6</td>
    </tr>
    <tr>
      <td>301</td>
      <td>1.0</td>
    </tr>
  </tbody>
  </table>

  Pysäköintinormit vaikuttavat vain uusien asukkaiden autonomistukseen.</li>

<li> <b>cco</b> = autoilun kilometrikustannus</li>
<li> <b>edu</b> = kunkin ennustealueen oppilaspaikkamäärät peruskoulussa, toisella asteella ja korkeakouluissa</li>
<li> <b>ext</b> = ulkoinen liikenne eli työsäkäyntialueen tienpäät (kasvukerroin verrattuna nykytilaan)</li>
<li> <b>lnd</b> = kunkin ennustealueen rakennetun maa-alan osuus sekä erillistalojen osuus rakennuskannasta</li>
<li> <b>pop</b> = kunkin ennustealueen kokonaisväkiluku sekä eri ikäryhmien osuudet</li>
<li> <b>pnr</b> = liityntäpysäköintilaitosten kapasiteetti ja 12 tunnin hinta</li>
<li> <b>prk</b> = kunkin ennustealueen työpaikan ja asiointimatkojen pysäköintikustannukset</li>
<li> <b>tco</b> = joukkoliikenteen kuukausikustannukset eri vyöhykkeillä</li>
<li> <b>trk</b> = raskaan liikenteen lähtötiedot: yhdistelmäajoneuvoilta kielletyt ennustealueet ja jätteenkäsittelylaitosten ennustealueet</li>
<li> <b>wrk</b> = kunkin ennustealueen kokonaistyöpaikkamäärä sekä eri alojen työpaikkojen osuudet (palvelut, kaupat, logistiikka, teollisuus)</li>
</ul>

### Lähtödata

Kansio sisältää perusvuoden (lähtökohtaisesti 2023, mutta jotkut tiedot voivat olla vanhempia) syöttötietoja (kuvattu yllä)
ja [pohjakysyntämatriiseja](tulokset.md#tuloskansion-matriisitiedostojen-kuvaukset).
Pohjakysyntämatriisit menevät ensimmäiseen sijoitteluun, josta kysyntälaskenta alkaa. Pohjakysyntä kuvaa kysyntää estimointivuoden tilanteessa estimoinnissa käytetyllä verkolla ja syttötiedoilla. Pohjakysyntä ei käytännössä vaikuta malllin tuloksiin, mutta malli on sitä nopeampi, mitä lähempänä pohjakysyntä on lopullista malliajossa laskettua kysyntää.
Perusvuoden syöttötiedot menevät tavaraliikennemalliin ja autonomistusmalliin, jotka molemmat ovat muutosmalleja.
Perusvuoden syöttötiedoissa `car`-tiedosto on (toisin kuin ennusteskenaarion syöttötiedoissa) pakollinen:

* **car** = kunkin ennustealueen autotiheys

### Verkot

Kansio sisältää kullekin tarkasteluvuodelle/skenaariolle alikansion, jossa on liikenneverkon lähtötiedot sekä niiden selostus (readme).

**Tiedostot**

* **base_network_xxx.txt** = liikenneverkon solmut ja linkit sekä niiden attribuutit
* **transit_lines_xxx.txt** = joukkoliikennelinjaston kuvaus: mm. linjatunnus, kulkumuoto, ajoneuvotyyppi (vehicle), reitin otsikko, reitin käyttämät solmut
* **turns_xxx.txt** = kääntymiskiellot eri solmujen välillä
* **extra_links_xxx.txt** = linkkikohtainen tienkäyttömaksu eri aikajaksoilla (aht, pt, iht), pyörätieluokka eri linkeillä, linkin kaltevuus
* **extra_nodes_xxx.txt** = solmun korkeustaso
* **extra_transit_lines_xxx.txt** = joukkoliikennelinjojen vuorovälit eri aikajaksoilla (aht, pt, iht)

Skenaariot voi muodostaa kootusti Modellerissa "[Sijoittelupankin perustaminen](sijopankki.md)"-sivun ohjeiden mukaan.
Moduuli ajaa myös sisään seuraavat kaikille skenaarioille yhteiset tiedot:

* **modes_xxx.txt** auto- ja pyöräverkon kulkutavat
* **vehicles_xxx.txt** joukkoliikenteen ajoneuvotyypit

Lisäksi joissakin skenaarioissa verkot voivat sisältää tiedostoja, jotka määrittävät *network field* -attribuutteja. Network fieldit ovat merkkijonomuotoista dataa, joita voidaan käyttää esimerkiksi kadun nimien, pysäkkien nimien tai joukkoliikennelinjojen linjakilpitekstien tallentamiseen. Nämä tiedot tallennettaisiin verkoille tiedostoihin, jotka ovat muotoa **netfield_links_xxx.txt** HSL:n jakamissa verkoissa näitä ei kuitenkaan ole käytetty.

## Lähtötietojen muokkaaminen

Lähtötietoja voi muokata joko suoraan lähtötietotiedostoihin tai EMME-ohjelmiston (Modeller, Network Editor, Prompt) kautta.

Verkkokuvausperiaatteita on kuvattu tarkemmin "[EMME-verkon kuvaus](emme_verkko.md)" -sivulla.
Noudatathan näitä periaatteita verkonkuvauksia koodatessa, jotta varmistutaan tulosten oikeellisuudesta ja aineistojen yhteiskäyttöisyydestä.

## Lähtötietojen vaikutus ennustemallin eri osiin

* Autonomistus alueittain
  * Kerros- ja pientalojen osuudet
  * Matka-aikasuhteet
* Matkamäärä alueittain
  * Asukasmäärä ikäryhmittäin
  * Autonomistus
* Kulkutavan valinta
  * Alueparien väliset matka-ajat autolla ja joukkoliikenteellä
  * Alueparien väliset etäisyydet polkupyörällä ja autolla
  * Alueparien väliset matkakustannukset: joukkoliikennelipun hinta, autoiun muuttuvat kustannukset (polttoaine, renkaat) ja mahdollinen ruuhkamaksu/tietulli
  * Autonomistus alueittain
* Matkakohteiden valinta
  * Saavutettavuus (matka-aika, etäisyys ja matkakustannus määräpaikkaan eri kulkutavoilla)
  * Työpaikkamäärä määräpaikassa
  * Oppilaspaikkojen määrä määräpaikassa
* Reitin valinta
  * Auto- ja joukkoliikennelinkin matka-aika
  * Pyörälinkin pituus
  * Autolinkin matkakustannus


## Aineistojen ylläpito

HSL ylläpitää lähtötietoaineistoja MAL-suunnittelun ja joukkoliikennesuunnittelun tueksi.
Aineistojen nimissä on yleensä jokin vuosiskenaario, mutta ennusteet eivät koskaan kuvaa tarkkaa vuotta, vaan tiettyä hankkeiden,
maankäyttöjen ja muiden lähtötietojen yhdistelmää.

Tässä on kuvattu yleisesti HSL:n ylläpitämiä lähtötietoaineistoja ja niiden rakennetta.
Ohjeita aineistojen lataamiseen ja käyttöön löydät "[Mallijärjestelmän käyttö](mallitoiden_yleisohje.md)"-sivulta.

### Ennusteskenaarioiden syöttötiedot (maankäyttö, kustannukset ym)

**Lähtötietoja tuotetaan MAL-suunnittelun yhteydessä n. neljän vuoden välein seuraaville skenaarioille:**
* Nykytilan kuvaus
* MAL-suunnitelman tavoitevuoden skenaario
* MAL-suunnitelman pitkän aikavälin tavoiteskenaario
* Välivuosiskenaario

Aineistojen sisältöjä on kuvattu tarkemmin aineiston jakokansiossa, johon saat käyttöoikeuden täyttämällä hakemuslomakkeen EXT-helmet-Teams-ryhmässä.
Tiedostopolun juuren on dokumentit sisältävät aineistojen yleiskuvauksen,
ja tarkempia tietoja löytyy kunkin tiedoston sisältä kommmentteina.

### Verkkokuvaukset

Vuosittain päivitetään tuore nykytilan kuvaus sekä mahdolliset muutokset tulevien vuosien kuvauksiin HSL:n ja kuntien tuottamiin suunnitelmiin perustuen.
Päivitetyt versiot julkaistaan syksyisin. Verkkojen vuosipäivityksiä laaditaan vuosittain kuvaamaan kunkin syksyn liikennetilannetta HSL-liikenteessä. 
Muutostyö käynnistyy tammikuussa HSL:n Liikennöintisuunnitelman hyväksymisen jälkeen, ja viimeistellään kesällä, kun kaikki syksyn muutokset ovat varmistuneet.
Tässä yhteydessä samat muutokset kuvataan myös MAL-verkkojen päivitettäviin versioihin sekä välivuosien verkoille.
Lisäksi tulevaisuuden verkkoihin viedään tiedot esim. valmistuneiden linjastosuunnitelmien tuomista muutoksista. 

Kaukojunaliikennettä ja muiden kuin HSL-alueen bussilinjoja ei päivitetä säännöllisesti vuosipäivitysten yhteydessä.
Kaukojunaliikennettä päivitetään suurempien muutosten yhteydessä, ja viimeisin muutos on syksyltä 2023.
Muiden kuin HSL:n järjestämän linja-autoliikenteen viimeisin päivitys on vuodelta 2023.

Laajempia muutoksia tehdään MAL-suunnittelun yhteydessä n. neljän vuoden välein, ja tässä pohjana käytetään viimeisimmän vuosipäivityksen mukaisia verkkoja.

**Lähtötietoja tuotetaan seuraaville skenaarioille:**
* Nykytilan kuvaus
* MAL-suunnitelman tavoitevuoden skenaario
* MAL-suunnitelman pitkän aikavälin tavoiteskenaario
* Välivuosiskenaario

Aineistojen sisältöjä on kuvattu tarkemmin aineiston jakokansiossa, johon saat käyttöoikeuden täyttämällä hakemuslomakkeen EXT-helmet-Teams-ryhmässä.
Kullekin vuodelle on oma alikansionsa ja niistä löytyy readme-tiedostot, joissa on selostettu yleiskuvaus aineistosta.

Ilmoitathan, mikäli havaitset tarjontakuvauksissa puutteita tai korjaustarpeita.
HSL ylläpitää korjaustarvelistaa sekä tarjontamallin lähtötietojen tarkempia kuvauksia.

Verkkokuvausperiaatteita on kuvattu tarkemmin sivulla "[EMME-verkon kuvaus](https://hsldevcom.github.io/helmet-docs-h5/emme_verkko.html)".
Noudatathan näitä periaatteita verkonkuvauksia koodatessa, jotta varmistutaan tulosten oikeellisuudesta ja aineistojen yhteiskäyttöisyydestä. 

<!-- Raporttilinkki päivitettävä kun julkaistu -->
Lisätietoja mallin käyttämisestä "[Mallijärjestelmän käyttö](mallitoiden_yleisohje.md)"-sivulla.
Taustatietoa verkkokuvausten muodostamisesta ja historiasta löydät raportista [Helsingin seudun työssäkäyntialueen liikenne-ennustejärjestelmän tarjontamallit 2017](https://staticfiles.hsl.fi/globalassets/julkaisuarkisto/2019/helsingin-seudun-tyossakayntialueen-liikenne-ennustejarjestelman-tarjontamallit-6-2019.pdf).
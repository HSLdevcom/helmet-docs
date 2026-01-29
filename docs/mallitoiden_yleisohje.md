---
nav_order: 4
sort: 4
---

# Mallijärjestelmän käyttö

On tärkeää, että mallia käytetään ja muokataan yhtenäisillä periaatteilla. 
Näin saadaan mahdollisimman luotettavia tuloksia, ja mahdollistetaan aineistojen  hyödyntäminen myös muissa projekteissa. 
Myös työn huolellinen dokumentointi on tärkeää, sillä se auttaa aineistojen tulkinnassa ja myöhemmässä hyödyntämisessä. 

HSL:n [lähtötietoaineistot](mallin_lahtotietotiedostot.md) (mm. maankäytöt ja verkkojen tiedot) saat ladattua zip-pakettina, kun olet täyttänyt aineistojen luovutuksen hakemuslomakkeen.
Hakemuslomake löytyy HSL:n Teams-ryhmästä EXT-Helmet, jonne saat käyttöoikeuden HSL:n Liikennejärjestelmäyksiköstä ([liikennemalli@hsl.fi](mailto:liikennemalli@hsl.fi)).
Kutakin projektia varten tulee hakea uudet aineistot, jotta aineistojen käyttöä voidaan seurata sekä varmistutaan, että lähtötiedot ovat aina ajan tasalla.

Voit aloittaa malliprojektin seuraamalla "[Asennus](kaytto-ohje.md)"- ja "[Sijoittelupankin perustaminen](sijopankki.md)" -ohjeita.
Kutakin projektia varten kannattaa luoda yksi yhteinen EMME-pankki, johon kootaan eri HELMET-skenaariot (esim. eri linjastovaihtoehdot).
Pääosin suositellaan käytettäväksi vain HSL:n julkaisemia skriptejä ja näiden oletusparametrejä.
Poikkeamat näihin on syytä dokumentoida huolella (ks. [HSL:n mallitöiden dokumentointiohje](HSL-toiden_dokumentointi.md)).

## Malliajojen ohje

HELMET-käyttöliittymän kautta pääset määrittämään projektin asetukset ja lähtötiedot. Käyttöliittymän asennusohjeet löydät sivulta [Asennus -> HELMET-asennus](https://hsldevcom.github.io/helmet-docs-h5/kaytto-ohje.html#helmet-asennus).

### Asetukset

Mallin ajoa varten tulee määritellä seuraavat asetukset. 

:warning: **Kansiopoluissa ei saa olla ääkkösiä!**

- Suorituskelpoinen EMME Python 
  - Tämän **on oltava** EMMEn mukana tullut ’python.exe’, jotta tietyt edellytykset täyttyvät.
  - esim. `C:\Program Files\Bentley\OpenPaths\EMME 24.00.00\Python311\python.exe`
- GitHubin [HELMET 5.0 Model System](https://github.com/HSLdevcom/helmet-model-system)-sivuston kansio ’Scripts’
  - Kansiossa ovat järjestelmän käyttämät Python-ohjelmat.
  - Version päivitys voidaan tehdä klikkaamalla "Lataa eri versio...". Nämä eivät korvaa skriptien vanhoja versioita, 
  vaan uusimmat versiot skripteistä talletetaan uuteen kansioon.
  - Voidaan käyttää myös olemassa olevaa kansiota.
- Projektin kansiopolku
  - Tänne talletetaan HELMET-skenaarioiden (malliajojen) määrittelyt (.json)
  - Tämä **ei** siis viittaa EMMEn projektitiedostoon (.emp)
- Lähtödatan sisältävä kansio
  - Tässä ovat omissa alakansioissaan alkukysyntämatriisit ja nykytilanteen syöttötiedot (2023)
  - Kansion sisällön saa HSL:ltä (ks. [Lähtötiedot](mallin_lahtotietotiedostot.md))
- Tulosten tallennuspolku
  - Tänne talletetaan ennusteajojen tulokset

Näiden asetusten lisäksi on kehittäjille tarkoitettuja asetuksia helmet-model-system -kansion tiedostossa `dev-config.json`.
Tyypillisesti tavallisilla käyttäjillä ei ole tarvetta muokata näitä lisäasetuksia, mutta joissain käyttötapauksissa voi olla hyötyä myös sellaisista asetuksista, joita ei ole vielä implementoitu käyttöliittymään.
Lisää tietoja `dev-config.json`-tiedoston asetuksista löytyy 
[Scripts-kansion README-tiedostosta](https://github.com/HSLdevcom/helmet-model-system/tree/olusanya/Scripts#configuring-the-model-run-with-dev-configjson).

### Malliajon määrittely

Käyttöliittymässä on tehtävä seuraavat määrittelyt jokaista ajettavaa HELMET-skenaariota kohden:

1.	Skenaarion tai ajon nimi
    - *Skenaario* ei tässä viittaa EMME-skenaarioon, vaan tässä annetaan nimi verkkokuvaus- ja maankäyttötietoyhdistelmälle joka menee yhteen malliajoon.
2.	EMMEn project-tiedosto (`.emp`)
3.	EMME-skenaarion numero. 
   Asetuksista riippuen sijoittelutulokset tallennetaan tähän skenaarioon tai erikseen seuraavaan neljään skenarioon (vrk, aht, pt, iht).
4.	Kansio, jossa ovat syöttötiedot
    - esim. `C:\Helmet\Scenario_input_data\2030`
    - Kansiossa on oltava *yksi* kappale kustakin tiedostotyypista .cco, .edu, .ext, .lnd, .pop, .prk, .pnr, .tco, .trk sekä .wrk. 
      Tiedostojen nimillä ei ole merkitystä, ja ne voivat poiketa toisistaan (kansiossa voi esim. olla 2023.pop ja 2023_b.wrk).
5.	Suoritettavien iteraatiokierrosten enimmäismäärä (yleensä 15)
    - Voit myös tehdä pelkän loppusijoittelun, jolloin iteraatioita ei ajeta. Pelkän
      loppusijoittelun tekeminen vaatii, että kysyntämatriisit omx-muodossa aiemmasta malliajosta
      löytyvät skenaarion tuloskansiosta.
    - Kaikkia iteraatiokierroksia ei ajeta, mikäli kysyntä konvergoituu aiemmin
6.	Valinta, lasketaanko joukkoliikenteen kustannusmatriisi vai käytetäänkö mallijärjestelmän aiemmin laskemaa matriisia 
   (sijaitsee tämän skenaarion tuloskansiossa `Tulosten tallennuspolku\Skenaario nimi`).
7.  Valinta, poistetaanko sijoittelun strategiatiedostot malliajon jälkeen. Strategiatiedostoja tarvitaan erilaisissa analyyseissä, joita voidaan tehdä EMMEn modellerilla malliajon jälkeen.
8.  Valinta, tallennetaanko eri ajanjaksot erillisiin EMME-skenaarioihin.
9.  Valinta, tallennetaanko eri ajanjaksojen (aht, pt, iht) matriisit EMMEn Database-kansioon. Malliajoon ja hankearviointiin tarpeelliset matriisit tallennetaan
    aina .omx-muodossa riippumatta tästä valinnasta.
    - Mikäli halutaan useiden HELMET-skenaarioiden kaikki EMME-matriisit talteen samaan
      EMME-projektiin (.emx-tiedostoihin), voidaan lisäksi ennen jokaista malliajoa määrittää
      ensimmäisen matriisin numero. Yhteen malliajoon tarvitaan aina 300 matriisin numeroavaruus (100 per ajanjakso),
      joten jos ensimmäiseen malliajon matriisit alkavat luvusta 100 (oletus), toisen skenaarion matriisien alku kannattaa asettaa lukuun 400.
    - Ensimmäiset 100 matriisia ovat sijoittelun käytössä sijoittelussa, ja niitä yliajetaan jokaisessa malliajossa.
    - EMME-projektissa matriisit on aina jaettu kaikkien skenaarioiden kesken, eli jos valintaa ei erikseen tehdä, matriisit yliajetaan jokaisen malliajon jälkeen ja eri skenaarioiden matriisien tarkastelu on mahdotonta EMMEssä.

Huom: agenttiajo ja mockajo onnistuu vain dev_config.json tiedoston muokkaamisen kautta. Ohjeet siihen löydät täältä: [Helmet-model-systems Github](https://github.com/HSLdevcom/helmet-model-system/blob/olusanya/Scripts/README.md).

### Hyöty-kustannusanalyysin (hankearvioinnin) määrittely

H/K-analyysillä voidaan verrata ajettujen skenaarioiden hyötyjä ja kustannuksia. Tulokset tulostuvat Excel-tiedostoon tuloskansiossa. Analyysia varten on määriteltävä:

1. Vertailuvaihtoehdon (ve0) tuloskansio (`Tulosten tallennuspolku\Skenaarion nimi`)
2. Hankevaihtoehdon (ve1) tuloskansio

Jos ennusteita on ajettu kahdelle vuodelle (esim. 2040 ja 2060), vertailuvaihtoehto ja hankevaihtoehto on mahdollista määrittää toisellekin ennustevuodelle. Lisätietoa H/K-laskennasta ja vaikutusten arvioinnista on "[Vaikutusten arviointi](vaikutusten_arvionti.md)" -sivulla.

## Tulosten käsittely ja tulkinta

Voit lukea lisätietoa mallin tuottamista tulostiedostoista ja tulosten tulkinnasta [Tulokset](tulokset.md)-sivulla ja
esimerkkejä mallituloksista tehtävistä visualisoinneista [Esimerkkejä tuloksista](esimerkkeja_tuloksista.md)-sivulla.

## Dokumentointi ja aineistojen luovutus

Työn lopuksi kannattaa dokumentoida huolella tehdyt muutokset. 
Yleensä työn tilaajalla on tietyt toiveet siitä, millaiset dokumentit mallitöistä halutaan. 
HSL:n tilaamissa töissä kaikki tehdyt muutokset tulee dokumentoida ja aineistot luovuttaa [HSL:n mallitöiden dokumentointiohjeen](HSL-toiden_dokumentointi.md) mukaan.  

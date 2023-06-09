---
nav_order: 9
sort: 9
---

# HSL:n mallitöiden dokumentointiohje

Tässä ohjeessa kuvataan mallitöiden dokumentointi HSL:n tilaamissa töissä.
Ohjeita voi toki soveltaa myös muissa projekteissa.
Ohjeeseen kannattaa perehtyä jo työn aloitusvaiheessa, jotta työskentelytavat tukevat parhaiten tarvittavien dokumenttien tuottamista.

HSL:n tilaamissa töissä kaikki tehdyt muutokset tulee dokumentoida mallitekniseen muistioon ja tallentaa lisäksi muutostiedostot ja/tai muokatut lähtötiedot.
Alla on kuvattu tarkemmin mallitöissä tuotettavia ja HSL:lle luovutettavia aineistoja.
Lisäohjeita saat tarvittaessa HSL:n yhteyshenkilöiltä.

[Mallin käyttöön](mallitoiden_yleisohje.md) ja [lähtötietojen muokkaamiseen](mallin_lahtotietotiedostot.md) löydät lisätietoja edellisten linkkien kautta.

## Luovutettavat aineistot

Työn päättyessä toimita HSL:n yhteyshenkilölle tässä luetellut aineistot.
Tämän dokumentoinnin tavoitteena on helpottaa tulosten tulkintaa, mahdollistaa tulosten toistettavuus ja helpottaa aineistojen jatkohyödyntämistä.

### Mallitarkastelujen yleiskuvaus

Kirjaa tehdyistä tarkasteluista ja verkkomuutoksista yleiskuvaus omaan dokumenttiinsa ja kirjaa vastaavat asiat myös työn raporttiin.
Esimerkkinä voi käyttää lähtöaineistojen yhteydessä olevia yleiskuvauksia.

Kuvaa lyhyesti myös mm. mahdollisten poikkeavien skriptien ja parametrien käyttö. 

### Mallitekninen muistio

Työn mallitekniseen toteutukseen liittyvät huomiot kirjataan mallitekniseen muistioon, joka luovutetaan työn päättyessä.
Kirjaa käytetyt lähtötiedot ja kaikki näihin tehdyt muutokset mallitekniseen muistioon.
Merkinnästä tulee käydä ilmi, mitä kysyntä- ja tarjontakuvauksen tai malliajon osaa ja ominaisuuksia on muokattu.
Merkitse myös muutosmakro (ems-tiedosto), jolla muutos on toistettavissa ja josta käyvät ilmi käytetyt lukuarvot, tai lähtötietotiedosto, johon muutokset on viety.
Jos olet lisännyt verkolle solmuja, listaa käyttämäsi uudet solmunumerot.
HUOM. Virallisia solmuja saa koodata vain, jos siitä sovitaan erikseen HSL:n kanssa.
Pääsääntönä käytetään aina villejä solmunumeroita (ks. raportti Helsingin seudun liikenteen Emme-verkon kuvaus, joka on saatavilla EXT-Helmet -Teams-ryhmässä).
Kirjaa muistioon, mistä tiedostoista ja/tai kansioista eri tiedot löytyvät.

Dokumentoi muistioon myös muutosten perustelut.

### Tallennettavat muutos- ja lähtötietotiedostot 

- Tallenna kaikista tekemistäsi muutoksista muokatut versiot lähtötietotiedostoista tilaajalle toimitettavaksi
- Tallenna muutosmakrot kaikista tekemistäsi muutoksista: Tallenna kaikista muutoksista ems-tiedostot, ja nimeä tiedostot hankkeen/muutoksen mukaan.
  Tallenna eri skenaarioiden (myös eri tarkasteluvuodet) muutokset eri tiedostoihin.
  Muutokset voi tarvittaessa jakaa vieläkin useampaan osaan, sillä pieniä osia on helpompi jatkokäsitellä kuin liian suuria paloja.
  Koodaa aina erikseen autoverkolle, joukkoliikenneverkolle (sis. vaihdot) ja joukkoliikennelinjastoon tehtävät muutokset,
  jotta näistä muodostuu erilliset muutostiedostot.
- Tarjontamuutoksista (linjat ja vuorovälit), joista ei ole .ems-tiedostoja, toimita tilaajalle muokatut lähtötiedostot,
  ja kirjaa mallitekniseen muistioon, mitä muutoksia olet tehnyt, esim.:
  - Linja 10141 ja 10142 reittimuutos Töölössä
  - Linja 25501 ja 25502 uudet vuorovälit
  - Solmut 123456 ja 123457 lisätty label-tiedot

### Muokatut malliskriptit

Jos työn yhteydessä tehdään muutoksia mallin käyttämiin skripteihin, toimita muokatut skriptit Githubiin.

### Emme-pankit

Työn päättyessä HSL:lle palautetaan työn Emme-pankki, jossa on kaikki tarkastellut skenaariot sijoiteltuina. Lisäksi palautetaan kaikkien skenaarioiden (osa)matriisit.

### Emmen worksheetit

Tallenna luovutettavaan aineistoon tuloksissa esiteltävistä raporttikuvista Emmen worksheetit sekä mahdolliset tunnuslukujen laskentakaavat,
joiden avulla raportit ovat helposti toistettavissa.
Kuvaa tunnuslukujen laskentakaavat projektin raportissa, tai ainakin malliteknisessä muistiossa.

### Emmen ulkopuolisten analyysien dokumentointi

Mikäli työn yhteydessä laaditaan lisätarkasteluja esim. paikkatieto-ohjelmalla, tulee myös näissä mahdollisesti käytetyt laskentakaavat
dokumentoida mallitekniseen muistioon.

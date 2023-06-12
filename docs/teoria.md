---
nav_order: 8
sort: 8
---

# Helmet-mallin teoria

Jensin kommentti: Ohjeissa ei ole kuvattu mallin käyttämiä parametreja, funktioita ja muita oletuksia
Pitäisikö tämän olla "matalan kynnyksen kysyntärapportti"?

## Helmet-parametrien oletuksia
Kaikki Helmet-mallissa käytetyt parametrit löytyy Scripts/parameters kansiossa. Poikkeuksena ovat sijopankin ja skenaarioiden parametrit, mutta ne vaikkuttavat malliajoa vain vähän (?).

| tiedosto                    | selitys                                                          |
|-----------------------------|------------------------------------------------------------------|
| assignment.py               | sijoittelun parametrit (vdf jne.)                                |
| car.py                      | autojen käyttöaste, autotiheys jne.                              |
| departure_time.py           | lähtöajojen jakaumia per kiertomatkatyyppi ja liikennemuoto      |
| destination_choice.py       | määränpäiden jakauma                                             |
| impedance_transformation.py | vastukset                                                        |
| income.py                   | tulojakauma                                                      |
| mode_choice.py              | liikennemuotovalinnan logit-mallin parametreja                   |
| tour_generation.py          | kiertomatkageneraattori                                          |
| zone.py                     | alueiden luokitus, ikäjakauma, jne.                              |

## Helmetin funktiot
Helmetin viivitysfunktiot

Olisi hyvä näitä plotata täällä

## Muut oletukset Helmet-mallinnuksessa
Arvot pysyy samana, Helmet ei voi olettaa liikennekäyttäytymisen muutoksia. 

## Muut raportit
Lisätietoa näissä raporteissa:
https://hslfi.azureedge.net/globalassets/julkaisuarkisto/2020/6_2020_helsingin_seudun_tyossakayntialueen_liikenne-ennustejarjestelman_kysyntamallit.pdf Kysyntäraportti

https://hslfi.azureedge.net/globalassets/julkaisuarkisto/2019/helsingin-seudun-tyossakayntialueen-liikenne-ennustejarjestelman-tarjontamallit-6-2019.pdf
tarjontaraportti


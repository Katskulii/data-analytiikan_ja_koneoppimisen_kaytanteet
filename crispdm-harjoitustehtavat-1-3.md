## Tehtävä: Opiskelijaryhmän tiedot
* **Kaikkien ryhmään** kuuluvien opiskelijoiden nimet ja JAMK:n opiskelijatunnukset
    * Kati Tuunainen (AC8409)
    * Miika Toukola (AC8450)
    * Mika Lipponen (AD7727)
    * Minna Kiviniemi (AC8433)

Huom! Vain yksi vastaus tähän ryhmätehtävään per ryhmä. Kaikki vastaukset arvioidaan koko ryhmän jäsenille samalla tavalla.

#### Tehtävien pisteytys

* Opintojakson opettaja laskee pisteet palautuksen jälkeen

Tehtävien maksimipistemäärät:

| Teht. 1 | Teht. 2 | Teht. 3 | Yhteensä |
|---------|---------|---------|----------|
| 5p      | 5p      | 5p      | max. 15p |

--------------------

## Tehtävien 1-5 alustus 

Tehtävissä **1-5** on kuvitteellinen tilanne, jossa **ryhmänne on konsultoimassa vesiyhtiötä**.

* Datalähteenä on **Yorkshire Water** -yhtiön julkaisemat vedenkäyttötilastot vuosilta **2012-2015**
* Datalähteenä tehtävässä on: https://datamillnorth.org/dataset/yorkshire-water-daily-customer-meter-data--local-area-

Huom! Voitte käyttää tulosten analysoinnissa annettua [Yorkshire Water Jupyter Notebook -dokumenttia](jupyter_data/YorkshireWater_data_analysointi.ipynb). 
Sitä voi ja pitääkin hieman muuttaa data- ja tulosanalyysia varten.


Seuraavassa hieman lisätietoa datasta sen tarjoajan sivuilta:

* A dataset showing daily water consumption readings in cubic metres (m3) from internal and/or external meters in a discrete study in two distribution management areas (DMAs) in Yorkshire between 2013 and 2015.
* This data is taken from a live localised project investigating water use. 
* The data has been anonymised to remove personal data and make it Data Protection Act compliant. 
* The DMAs are also anonymised to prevent any open data activity affecting the results of the ongoing study the data has been taken from.

### Videomateriaali 
Katso videomateriaali aina ennen tehtävien tekemistä. Tämä on tärkeää, koska on hyvä pyrkiä ymmärtämään käsitteitä ennen vastausten kirjoittamista. 
* Tehtävien lopussa on lista hyödyllisistä videoista ja muista lähteistä
* Tehtävissä keskeisin asia on **CRISP-DM -prosessi**
* Ennen tehtäviä kannattaa katsoa videot **01-05**.

### Tehtävät 1-5 vs. CRISP-DM standardi prosessimalli

![CRISP-DM Yleiskuva](img/crisp-dm.png)


--------------------
# Tehtävä 1: Ongelman kuvaaminen  (Business Understanding)

Haetaan vastaukset kysymyksiin: 
* Millainen data on kyseessä?
* Missä yhteydessä tästä datasta voi olla hyötyä?
* Millainen liiketoiminta on datan taustalla?
* Mitä kaikkea datasta voidaan oppia?
* Mitä datasta voidaan nähdä?
* Mitä datasta voidaan tunnistaa?
* Voidaanko datasta havaita jotain poikkeavaa?
* Tarvitaanko tämän lisäksi jotakin muuta lisätietoa?

**Lähteitä:**
* Video - **05 CRISP-DM Alku**
* Katso Myös Video **10: Tekoälyprojektin roolitus**

## Tehtävä 1: Vastaus 

* Millainen data on kyseessä?

Data on kerätty reaalimaailmasta ja näyttää päivittäiset vedenkulutuslukemat kuutiometreinä (m³ = 1,000 litraa) sisäisistä ja/tai ulkoisista mittareista erillisessä tutkimuksessa kahdella jakelun hallinta-alueella (DMA) Yorkshiressa vuosina 2013–2015. Data koostuu yksittäisten kiinteistöjen päivittäisestä vedenkulutuksesta. Mukana erillisessä tiedostossa on myös data kyselytutkimuksesta vuodelta 2019. Se sisältää vastauksia asiakkailta vedenkulutuksesta, kustannuksista ja asiakkaiden kiinteistöjen yleisestä varustelutasosta. Molemmat tiedostot ovat CSV-muodossa.

* Millainen liiketoiminta on datan taustalla?

Datan on koonnut vesiyhtiö Englannissa, Yorkshire Water. Kyseessä on voittoa tavoitteleva yritys joka vastaa Yorkshiressä vedenjakelusta ja jäteveden käsittelystä. Yritys tarjoaa palveluita kuluttajien ja yrittäjien lisäksi myös rakennuttajille. Yorkshire Water ottaa liiketoiminnassaan vahvasti huomioon kestävän kehityksen kouluttaen jatkuvasti omaa väkeään ja tarjoten koulutusta myös sidosryhmilleen e-kurssien muodossa. Halu palvella asiakkaita mahdollisimman laadukkaasti ja laajasti näkyy hyvin yrityksen kotisivuilta.

* Missä yhteydessä tästä datasta voi olla hyötyä?

Datasta voisi olla hyötyä, kun vesiyhtiö pyrkii tarjoamaan asiakkaille parempaa palvelua. Esimerkiksi arvojensa mukaisesti valistaa veden kuluttajia siitä, miten toimitaan vastuullisesti ja onko ohjeistuksesta ollut näkyvää hyötyä. Vesiyhtiö voi myös datan avulla paremmin arvioida ja ennustaa omia kustannuksia. Poikkeustilanteiden ennakoiminen olisi myös hyödyllistä, esimerkiksi laiterikkojen nopea tunnistaminen parantaisi asiakaskokemusta. Vesiyhtiö pyrkii olemaan ympäristöystävällisempi toiminnassaan ja datasta voisi löytyä jotain apua vaikka hukkaveden minimoimiseksi. Datan taustalla on veden myyminen, joten yhtiö luultavasti haluaa minimoida kustannukset ja tarjota toimivaa vedenjakelua. Muita tahoja, jotka hyötyvät saadusta datasta on esimerkiksi tutkimus.

* Mitä kaikkea datasta voidaan oppia?
* Mitä datasta voidaan nähdä?
* Mitä datasta voidaan tunnistaa?

Voisi toivoa, että datasta pystyttäisiin esimerkiksi ennustamaan vedenkulutusta. Data voisi auttaa käyttäjien luokittelussa eri käyttäjäprofiileihin vedenkulutuksen mukaan, esim. eri koko luokan kiinteistöjä. Vedenkulutuksen ennustaminen olisi tärkeää. Datasta voi myös löytää kuinka asiakkaat käyttävät vettä eri aikoina, esim. vuorokaudessa, viikossa, tai vuodenaikoihin nähden. Datasta voi poimia vedenkäytön trendejä. Jos datasta voidaan havaita jotain säännöllisesti tai säännöllisestä poikkeavaa, se voisi olla kallisarvoista. Esimerkiksi, jos verrataan putkien jäätymistä, kun pakkanen painuu tiettyyn lukemaan, osataan kuluttajia neuvoa ennakolta mitä kyseisisssä tilanteissa pitäisi tehdä.

* Voidaanko datasta havaita jotain poikkeavaa?

Datassa itsessään on jotain erikoisia lukemia, jotka ovat voineet jossain vaiheessa tarkoittaa jotain, minkä merkitys on nyt hukkunut matkalla. Esimerkiksi kohteet joiden tunnistenumerot ovat 872 ja 872.1 mahdollisesti jotenkin liittyvät toisiinsa, mutta datasta tämä yhteys ei selviä yksiselitteisesti. Muita erikoisuuksia voi löytyä, kun dataan tutustuu tarkemmin. Datasta voisi havaita esimerkiksi vesimittarin vaihdon tai vesivahinkoja.

* Tarvitaanko tämän lisäksi jotakin muuta lisätietoa?

Datan lisäksi vesiyhtiö teetti asiakaskyselyn. Tämän kyselyn tuloksia voisi myös hyödyntää vedenkäyttödatan ymmärtämisessä, vaikkakin datan anonymisoinnin takia suora liittäminen ei ole mahdollista, koska asiakaskysely on tehty vuonna 2019. On syytä miettiä onko verrattava tieto luotettavaa kyselyn eriaikaisuuden vuoksi. Datan yhdistäminen loma-aikoihin tai säätietoihin voisi myös tuottaa lisäarvoa.


--------------------
# Tehtävä 2: Datan kuvaaminen (Data Understanding)

* Millaisia muuttujia on datassa?
* Mitä arvoa on käytetty täytearvona?
* Millaisia korrelaatioita datasta löytyy?
* Tarkistelee dataa tietyillä aikaväleillä (esim. viikko, kuukausi tai vuosi).
* Havaintojen tueksi voi liittää visualisoitua dataa
* Mieti mitä tällä datalla voidaan mahdollisesti tehdä?

Palautetaan vastaus repositoryyn annettuun palautuspäivämäärään mennessä:
* palautus tehdään MarkDown-formaatissa (tarkenne .md), jolloin kuvat linkitetään dokumenttiin

Datan käsittely:
* Katso julkaistu [Yorkshire Water Jupyter Notebook -dokumentti](jupyter_data/YorkshireWater_data_analysointi.ipynb) 
* Tätä voitte käyttää apuna datan ymmärtämisessä
* Sitä voi myös täydentää lisähavaintojen ja -analyysin tekemiseen (voi itse ohjelmoida lisää)

**Lähteitä:**
* Video - **05 CRISP-DM Loppuosa**

Kannattaa myös katsoa seuraavat videot:
* **18: Data ja sen laatu**
* **19: Huono Data**
* **20: Laadun arviointi ja formaatit**

## Tehtävä 2: Vastaus 

Datasta löytyvät muuttujat:
* vedenkulutus per kohde kuutiometreinä per päivä
* päivämäärät jolloin mittauksia on tehty (year/month/day/week/weekday)
* mittareiden kohdenumerot

Vedenkulutuksen täytearvona on käytetty arvoa -1. Vettä on mitattu yhteensä 2,085 eri kohteesta ja mittauspäiviä on yhteensä 1,460.
Kyselyssä vuodelta 2019 on 13,748 vastaajaa jolta jokaiselta on kerätty 98 tietuetta.

* Millaisia korrelaatioita datasta löytyy?

Tässä vaiheessa on vaikea tunnistaa datasta korrelaatioita. Yleisinä loma-aikoina kiinteistöjen vedenkulutus voi muuttua. Olisi mielenkiintoista nähdä onko vuodenajoilla jotain korrelaatiota veden käytölle, kuten voisi olettaa. Tunnistamalla kiinteistöjä, joilla on keskenään korrelaatiota vedenkäytössä, voitaisiin luokitella kiinteistöjä eri kategorioihin. Yleisesti suurempi vedenkulutus viittaisi suurempaan kiinteistöön ja kaikkein suurimmat vedenkuluttajat luultavasti eivät ole yksityistalouksia.

* Tarkistelee dataa tietyillä aikaväleillä (esim. viikko, kuukausi tai vuosi).

Yksittäisen kohteen vedenkulutus vaihtelee näennäisen arvaamattomasti. Vuoden aikana saattaa olla yksittäisiä piikkejä veden kulutuksessa tai peräkkäisiä päiviä jolloin vettä ei kulu ollenkaan. Joillakin kohteilla on tasaisesti keskiarvoa korkeampi kulutus. Useimmista kohteista ei ole koko tarkasteluajalta mittausdataa eli alusta ja lopusta löytyy vain täytearvoa.

* Havaintojen tueksi voi liittää visualisoitua dataa

![Vuoden ajalta vedenkulutus eräässä kiinteistössä](img/MT_oao_20230206_vuosivedenkayttoa.png)

Tässä kuvassa näkyy yhden kiinteistön vedenkulutus vuodelta 2013. Vedenkuluts on mitattu päivittäin. Kuvaajasta näkee kuinka vedenkulutuksessa on selkeitä trendejä. Kun kuvaaja on ihan nollassa muutaman peräkkäisen päivän, niin silloin kiinteistössä ei ole ollut yhtään vedenkulutusta. Yleisimmin vedenkulutus on ollut välillä 0.02-0.04 kuutiometriä päivässä, mutta säännöllisesti kuvaajassa on yhden päivän piikkejä, jolloin kulutus on ollut huomattavasti suurempaa. Nämä piikit myös esiintyvät selvästi kahden kokoisina, noin reilun 0.1 kuutiometrin kulutuksena ja noin 0.2 kuutiometrin kulutuksena. Samalla tavalla datasta voidaan tutkia jokaista kiinteistöä. Ilman lisälaskemista kuvaaja ei kuitenkaan kerro kiinteistön keskimääräistä kulutusta.

![Vertailu neljän kiinteistön vedenkulutuksesta](img/MT_oao_20230202_neljäkiinteistöä.png)

Tässä kuvassa näkyy kohteiden 1 (sininen), 55 (vihreä), 873 (oranssi), 1000 (punainen) kumulatiivinen veden käyttö ajalta 1.1.2012 - 11.12.2015. Koska kaikissa kiinteistöissä veden kulutus päättyy vuoden 2015 alussa, voisimme arvata datan keräyksen päättyneen näihin aikoihin vaikka aikajakso datarakenteessa jatkuu vuoden loppuun.
Oranssissa kiinteistössä on tasaisesti käytetty vettä tarkasteluajalla, kun kumulatiivinen käyrä nousee tasaisesti koko kulutuksen ajanjaksolta. Punaisesta kiinteistöstä voisi sanoa samaa, mutta kulutuksen määrä on ollut noin puolet oranssin kiinteistön kulutuksesta. Sinisessä ja vihreässä kiinteistössä vettä alettiin kuluttaa vasta elokuussa 2013, mahdollisesti koska mittareita ei ollut asennettu ennen tätä tai muita reaalimaailman olosuhteista johtuen, joista datassa ei ole viitteitä. (Tästä kaaviosta ei näe muuttuuko data 0 vai -1 arvoiseksi, mutta tarkistamalla itse datasta nähdään, että mittaukset saavat arvon -1.) Näistä neljästä kiinteistöstä vihreässä kiinteistössä veden päiväkulutus on suurinta koska käyrä nousee jyrkimmin, kun taas sinisessä kiinteistössä vettä käytettiin tasaisesti mutta huomattavasti vähiten.

* Mieti mitä tällä datalla voidaan mahdollisesti tehdä?

Data mittaa kiinteistöjen vedenkulutusta, joten siitä voi seurata esimerkiksi mahdollisia kausittaisia vaihteluja tai kiinteistöjen tavanomaista vedenkulutusta. Datassa oleville poikkeuksille voi olla monia syitä, joita voi spekuloida, esim. vesivahinkoja, lomajaksoja, remontteja tai mittarinvaihdoksia. Datasta voisi myös yrittää irrottaa jokin tietty alue ja visualisoida se. Kaaviot voisi sitten näyttää veden kuluttajille, jos esim. veden kulutus on noussut edelliseen vuoteen verrattuna ja on ympäristöä kuormittavaa. Dataa voisi kenties käyttää myös kaupallisiin tarkoituksiin, esim. tarjoamalla asiakkaille sovellusta, mistä he voisivat seurata omaa vedenkulutustaan. Ja koska palvelu paranee, olisi se perusteltu syy hieman nostaa maksuja.

Datan käsittely:
* Katso julkaistu [Yorkshire Water Jupyter Notebook -dokumentti](jupyter_data/YorkshireWater_data_analysointi.ipynb) 
* Tätä voitte käyttää apuna datan ymmärtämisessä
* Sitä voi myös täydentää lisähavaintojen ja -analyysin tekemiseen (voi itse ohjelmoida lisää)

--------------------------

# Tehtävä 3: Datan valmistelu (esikäsittely, Data Preparation)

* Miten valmistelet datan?
* Mitä piirteitä tai muuttujia erotat datasta jatkokäsittelyä varten?
* Voidaanko jotakin jättää datasta pois?
* Millainen rakenne datassa on?
* Millainen dataformaatti on kyseessä?
* Kannattaako data pilkkoa osiin?
* Joudutaanko dataa mahdollisesti muuttamaan ennen sen jatkojalostusta?
* Mieti tilastotietojen hyötykäyttöä?
* Havaintojen tueksi voi liittää kuvia datasta.


**Lähteitä:**
* Video - **06 CRISP-DM Keskiosa** (Datan valmistelun kuvaus)

Myös kannattaa katsoa seuraavat videot:
* **16: Aineisto**
* **17: Validointi**

Katso julkaistu [Yorkshire Water Jupyter Notebook -dokumentti](jupyter_data/YorkshireWater_data_analysointi.ipynb)



## Tehtävä 3: Vastaus 

* Miten valmistelet datan?

Data luetaan csv-tiedostosta ja muunnetaan DataFrame muotoon. Datasta voisi myös laskea tilastollisia tunnuslukuja ja sen pilkkomista osiin voi harkita. Mittausdatan ja kyselytutkimuksen yhdistäminen on hankalaa jo sen takia, kun ne koskevat eriäviä ajanjaksoja.

* Mitä piirteitä tai muuttujia erotat datasta jatkokäsittelyä varten?

Datasta löytyy päivämäärät ja vedenkulutus ja kiinteistönumerot. Kulutusta voi myös tarkastella vuosikohtaisesti tai keskimääräisesti tai kokonaiskulutuksen osalta. Kyselystä voisi erottaa erilaisten vedenkäyttötarkotuksen mukaan kulutusta ja tarkastella näiden välisiä mahdollisia riippuvuuksia.

* Voidaanko jotakin jättää datasta pois?

Täytearvot voidaan jättää pois. Jokaisella kiinteistöllä on tarkasteluajan alku- ja loppupäässä täytearvoja.

* Millainen rakenne datassa on?
* Millainen dataformaatti on kyseessä?

Data on kaksiulotteinen taulukko. Jokainen rivi on yksittäinen päivämäärä ja sarakkeista löytyy eri kiinteistöjen vedenkulutus. 
Dataformaatti on .csv. Data luetaan DataFrame -muotoon ennen käsittelyä.

* Kannattaako data pilkkoa osiin?

Data ei kokonsa puolesta ole niin massiivinen, että sitä tarvitsisi pilkkoa osiin käsittelyä varten. Kun datasta tehdään koneoppimismallia, niin silloin datan voi jakaa osiin koulutusta, validointia ja testausta varten. Data voidaan myös pilkkoa erilaisiin kategorioihin esim. ajan mukaan tai kiinteistöjen mukaan. Visualisoiden näistä saa paremman kuvan ja erilaisten kiinteistöjen kokonaiskäyttöä voidaan tällöin verrata keskenään.

* Joudutaanko dataa mahdollisesti muuttamaan ennen sen jatkojalostusta?

Datasta voidaan poistaa täytearvoja tai jos osataan tunnistaa vääristävät virhetiedot.

* Mieti tilastotietojen hyötykäyttöä?

Pystytään ennakoimaan veden kokonaiskulutusta, mahdollisia putkirikkoja ja huoltojen ajoituksia. Keskimääräinen vedenkulutus on mielenkiintoinen. Samoin onko kiinteistöillä erilainen kulutus esim. viikolla tai viikonloppuna tai kesällä/talvella. Tässä vaiheessa voisi laskea tunnusarvoja kuten kulutuksen keskiarvo. 

![Koontia kyselyyn vastanneiden ilmoittamista vedenkulutus varustelusta](img/MT_oao_20230207_kyselystä_barchart.png)

Tästä kuvasta näkee, että vaikka kyselyyn vastasi vain vajaa 14,000 niin suihkuja ja WC:itä esiintyi yhteensä enemmän, kun taas kylpyammeita ei ole ihan kaikissa kiinteistöissä. Tätä kyselyn dataa voidaan seuloa vaikka kylpyammeen perusteella ja tutkia onko vedenkulutus näissä kiinteistöissä poikkeavaa muihin verrattuna. Kysely sisältää myös tiedon vastanneiden asuinalueesta, joiden perusteella datan jako osiin voisi olla mielekästä. Datan valmistelussa voisi valmistaa datasta myös summatun version eri osioille sekä laskea tilastollisia tunnuslukuja, kuten keskimääräistä kustannusta tai kulutusta vuodessa.

----------

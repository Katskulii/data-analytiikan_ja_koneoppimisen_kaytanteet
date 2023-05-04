## Tehtävä: Opiskelijaryhmän tiedot
* **Kaikkien ryhmään** kuuluvien opiskelijoiden nimet ja JAMK:n opiskelijatunnukset
    * Kati Tuunainen (AC8409)
    * Miika Toukola (AC8450)
    * Mika Lipponen (AD7727)
    * Minna Kiviniemi (AC8433)

* Huom! Vain yksi vastaus tähän ryhmätehtävään per ryhmä. Kaikki vastaukset arvioidaan koko ryhmän jäsenille samalla tavalla.

#### Tehtävien pisteytys

* Opintojakson opettaja laskee pisteet palautuksen jälkeen
* Alla kootusti tehtävien maksimipistemäärät

| Teht. 4 | Teht. 5 | Yhteensä |
|---------|---------|----------|
| 5p      | 5p      | max. 10p |

--------------------

# Tehtävä 4: Datan mallintaminen (Modeling)

Tehtävä on varmasti hieman hankala, mutta mm. näistä valinnoista sitten riippuu paljon
se lopputulos eli kuinka paljon asiakas hyötyy tehdystä data-analyysistä sekä koneoppimismallista.
* Miten mallintaisit datan?
* Millä tavalla päästään haluamaasi lopputavoitteeseen? 
* Regressio?
* Ennustaminen?
* Luokittelu?
* Ryhmittely?
* Ryhmien tunnistaminen datasta?
* Kuvaile Mitä tämän jälkeen tapahtuu CRISP-DM -mallin mukaan (pääpiirteissään)
* Havaintojen tueksi voi liittää kuvia/koodia datasta

Palautetaan vastaus repositoryyn annettuun palautuspäivämäärään mennessä:
* Palautus MarkDown-formaatissa (tarkenne .md), jolloin kuvat linkitetään dokumenttiin

**Lähteitä:**
* Video - **05 CRISP-DM Keskiosa**

Myös kannattaa katsoa:
* **09: KDD-prosessi**
* **11: Tietokone**
* **12: Matematiikka**
* **13: Työkalut**
* **14: Suurteholaskenta**

## Tehtävä 4: Vastaus 

### Datan mallintaminen

Datan mallintamiseen on monia vaihtoehtoja, mm. regression, clustering, classification, dimensionality reduction, model selection, preprocessing. Se mitä mallinnusta käytetään riippuu minkälaista dataa mallinnetaan. Yorkshire Water yrityksen mittausdata on suhteellisen pieni määrältään, mutta alueita on kaksi ja mittauspaikkoja yli 2000. Alueisiin kuuluu niin kotitalouksia kuin maatiloja, kouluja, liikehuoneistoja jne. Mielestämme datan mallintaminen kannattaisi tehdä clustering ja regression malleilla. Clustering mallilla saataisiin samoin vettä kuluttavat kohteet luokiteltua automaattisesti samaan nippuun ja regressiomallilla saisimme ennustettua veden kulutusta esimerkiksi vuodenajan tai kuukauden mukaan.



### Vesiyhtiön tavoitteita analyysin hyödyntämiseksi

    * kiinteistöjen luokittelu käyttäjäryhmiin (mitä hyötyä tästä on firmalle?)
    * uusille asiakkaille kustannusten arviointi (luokittelu auttaa tässä?)
    * vedenkulutuksen ennakoiminen (voisko tässä hyödyntää tuota luokittelua?)
    * tunnistetaan ajantasaisesti putki- tai laiterikot. Tällä tavoin säästetään luonnonvaroja ja rahaa.

Kiinteistöjen luokittelua varten voidaan kokeilla useampaakin luokittelumallia ja testailla kuinka moneen luokkaan kiinteistöt luonnollisesti jakautuvat. Uusille asiakkaille voidaan esittää arviota tulevasta kulutuksesta ja kustannuksista varmaan jo muutamalla kysymyksellä. Näiden kysymysten laatimiseen voidaan käyttää 2019 vuoden kyselyn tietoja. Regressiomallinnuksella kiinteistöittäin ja alueittain voidaan ennakoida kokonaiskulutusta vuositasolla.

Jonkinlainen sovellus tai tekstiviesti muistutus, johon asiakas voisi asettaa itse vedenkäytön rajat. Raja-arvon ylittyessä hän saisi ilmoituksen.

* Millä tavalla päästään haluamaasi lopputavoitteeseen? 


### Koneoppiminen datan luokittelussa ja ryhmittelyssä

  Käyttämällä klusterointia ja/tai päätöspuu mallinnusta voidaan data jakaa luokkiin. Koneoppimismallin ajamalla, kiinteistöt saadaan luokiteltua. Luokkien määrää pitäisi tutkia ja selvittää kuinka moneen data on hyödyllistä jakaa.

  Eräs lähestymistapa olisi ensiksi laskea joka kiinteistölle keskimääräinen kulutus kuukaudessa niiltä kalenterikuukausilta joille on mitattua dataa koko kuukaudelta kyseisessä kiinteistössä. Näin saadaan joka kiinteistölle tasaisempia lukuja käsiteltäväksi.
  Testaamalla klusterointia saataisiin jotain kuvaa siitä, jakautuvatko kiinteistöt vaikkapa neljään eri lokeroon: minimaalinen kulutus, pienkulutus, keskiluokan kulutus ja suurkulutus. Tällaisessa luokittelussa keskitytään kulutuksen määrään, ei niinkään kulutuksen rytmiin tai jaksollisuuteen (aikaan sidonnaisuuden aspekti). Regressio mallia käyttämällä voisi laskea kiinteistökohtaisen ennustuksen veden kulutuksesta olettaen, että tottumukset pysyvät samoina ja sitä kautta esimerkiksi osattaisiin kertoa asiakkaalle mahdollinen seuraavan kuukauden laskun arvioitu summa.
  Kyselytutkimuksen vastaajia voidaan myös luokitella näin kulutuksen määrän mukaan, jolloin laadittujen luokkien samaistaminen kulutukseen perustuvien luokkien kanssa voisi toimia mielekkäämmin kuin yksittäisten kiinteistöjen kanssa (jos osataan tunnistaa kotitalouksia kulutusluokista, koska kyselytutukimus koski vain näitä). Kyselytutkimuksen vastaajat voitaisiin luokitella kiinteistöön kuuluvien vettä kuluttavien kalusteiden mukaan. Esimerkiksi onko kiinteistössä 1 vai kolme wc pönttöä, 1 tai useampi suihku, ulkohana jne. Veden kulutuksen ennakointiin taas voidaan käyttää regressiomallinnusta.

* Luokittelu?
* Ryhmittely?
* Ryhmien tunnistaminen datasta?

(Pari ajatusta jota ei vielä ehkä muualle kirjattu kunnolla....
 Mitä tapahtuu jos ryhmitys tapahtuisikin viikottain, tai esim alkuviikosta enemmän käyttävät kiinteistöt verrattuna sellaisiin jotka käyttävät enemmän vettä viikon loppupuolella; vai ehkä datan voisi muokata tällaiseen muotoon, että miten eri viikonpäivinä kiinteistössä kulutus vaihtelee (verrattuna sen kiinteistön keskimääräiseen kulutukseen.))

* Regressio?
* Ennustaminen?

    - katsotaan scilearn joku regressiomalli käytettäväksi; linear regressio? yksinkertaisin mutta harvemmin paras
    - ainakin tässä vaiheessa kumulatiivinen versio datasta voisi olla selkeämpi vertaillessa kiinteistöjä
    - ope mainitsi nämä (luokittelumenetelmät): nearest neighbor, random forest (vois olla hyvä), puumenetelmä
    - suositteli myös katsomaan tehtävää 6 jos siellä tutustuu johonkin tähän soveltuvaan malliin

### Koonti ennen arviointia

* Kuvaile pääpiirteittäin mitä **tämän jälkeen** tapahtuu CRISP-DM -mallin mukaan.

 Arviointi.

* Havaintojen tueksi voi liittää kuvia/koodia datasta. !!!

   - scatter plot kyselyn sijainnista, värinä vaikka vedenkustannus
   - piirakkakaavio luokittelun tuloksista
   - ennustetta kokonaiskulutuksesta (linear progression regressio?)
   - bar chart? 


### Mitä muuta me vielä tehdään tähän tehtävään...

!! Kiinnostava huomio tehty dataa esikäsiteltäessä: kahdessa kiinteistössä veden kulutus on noin kuukauden ajalta huomattavasti suurempi kuin ennen ja jälkeen ajanjakson. Kyseessä on kiinteistöt 163 (ajanjakso osuu syys- ja lokakuun aikaan 2013) sekä 113 (ajanjakso osuu joulu- tammikuun vaihteeseen 2014-2015). Kyseessä on oltava virhetilanne.

Voidaanko vielä hyödyntää Yorkshire Waterin omista raporteista jotain, eli saisko sieltä vaikka tälle meidän tutkimukselle jotain suuntaa tutkittavaksi tai ilmiötä kommentoitavaksi?


* Millaisia mallinnusvaihtoehtoja on tarjolla - ks: https://scikit-learn.org/stable/index.html

* Voiko kyselydatan perusteella koneoppia jotakin?

* Mallinnuksessa ovat erikseen opetusaineisto ja testiaineisto, jolla rakennetun mallin toimivuutta testataan

* Onko ennusteet sidottu johonkin ajanjaksoon tai kenties eri jakelualueisiin?

* erilaiset vedenjakelualueet

* CRISP-DM lopputoimet prosessimallin mukaan (mukaan lukien seuraava tehtävä)

-kirjoitusten tuunaaminen
-kk kulutus laskeminen kiinteistöittäin, kumulatiivinen vois toimia kans
-k-clustering ajaminen tolle datalle (saataisko sieltä jotain kuviakin)
-CRISP-DM kysymykseen vastaaminen
-pitäiskö testiaineiston käyttämistä kommentoida jotenkin

 Videolla mainitsi tällaisia:
-tehtävän tuoksi koodia datasta
-scikit learn kirjastosta apua
-määrittele haluttu lopputulos
-vedenkulutus ryhmittelyä
-regressiomalli voi olla hyvin ennustava
-kuvia jupistä



----------
# Tehtävä 5: Tulosten arviointi (Evaluation / Deployment)

Tehtävässä arvioidaan kaksi osaa:

### 5.1: Projektin tulosten arviointi

* Esitellään tiivistetysti projektin keskeiset tulokset
Saimme laskettua vedenkulutusta kiinteistökohtaisesti sekä ennusteet ja löysimme erilaisia alueita. Löysimme datasta outlier tuloksia, jotka ovat todennäköisesti virheellisiä lukemia.

* Millaiseksi arvioitte projektin tulokset tässä vaiheessa?
Olemme päässeet hyvään vauhtiin projektin kanssa. Vielä olisi kuitenkin paljon pohdittavaa ja tutkittavaa, jotta voisimme rajata tuloksia tarkemmin ja mallintaa juuri oikealla tavalla. Löydöksemme ovat hyödyllisiä jo tässä vaiheessa ajatellen yrityksen liiketoimintaa, koska jo nyt pystyttäisiin asiakkaille esittämään arvio heidän tulevasta vedenkulutuksestaan.

* Kuinka helppoa tästä on jatkaa kohti toteutusta?
Projektia pitää vielä iteroida, jotta jatkaminen käyttöönottovaiheeseen voisi toteutua.

* Ketkä saatuja tuloksia arvioivat, jos halutaan, että projektille saataisiin rahoitus?
Jotta saataisiin rahoitusta asiakas Yorkshire Waters yrityksen johtokunta on toki ensisijainen taho, jolle tulokset esitellään. Voisi olla hyvä esitellä asia paikalliselle ely keskukselle ja kenties kunnanisille ja -äideille. Myös jokin tutkimuslaitos saattaisi olla kiinnostunut tutkimaan asiaa tarkemmin ja lähteä rahoittamaan hanketta.

* Miten osoittaisit projektin hyödyn liiketoiminnalle?


* Mitä toimenpiteitä suosittelisitte konsultin roolissa asiakasyritykselle?

Käyttöönoton vaiheet: 

* Millaiset työkalut tarvitaan tuotetun järjestelmän käyttöönottoon
* Miten järjestelmä otettaisiin käyttöön?
* Miten järjestelmän ylläpito järjestetään?
* Kuinka mahdolliset virheet ja ongelmatilanteet korjataan?

### 5.2: Jupyter Notebook päivitykset
* Jupyter Notebook - päivitykset, joita ryhmänne teki tämä projektin aikana
Lisäsimme ja vaihtelimme kiinteistöjä kuvaajaan 4.4 kokeillaksemme ja ymmärtääksemme mitä kuviossa tapahtuu. Kyseessä on kumulatiivisen kulutuksen kuvaaja. Lisäarvoa siitä saimme, kun opimme ymmärtämään mitä tapahtuu. Jatkossa pystyisimme käyttämään tietoa tietyn kiinteistön kulutuksen ennustamisessa ja arvioinnissa. 

Kyselydatasta suodatimme tietoa yleisimmistä kodinkoneista ja vettä kuluttavista kalusteista. Joita olivat suihkujen, vessojen ja kylpyammeiden määrät. 

* Jupyter Notebook -muutosten antama lisäarvo ajatellen projektin mahdollista jatkoa

---------------------
## Tehtävät 1-5 - esitys
### Videoesitys 

Tehdään **Videoesitys** (n. 10 min) projektista ja sen tuloksista.
Videolla voi kertoa tiivistetysti teidän koko "prosessista" eli tehtävistä 1-5.

* Tavoitteena on selventää projektin tuloksien pohdintaa arvioijalle (ts. opettajalle).
* Esityksessä tiivistetään tärkeimmät opit ja löydökset teidän ryhmän kannalta
* Esityksen muoto on vapaa ja ryhmän päätettävissä 
  * "käsikirjoitus", mitä aikoo esittää, kannattaa tehdä ennen esittämistä


### Esitys ei pakollinen 
 Videota ei tällä kurssilla erikseen arvioida, mutta silti toivon, että ryhmät tekevät sen.
ts. Sen tekeminen ei ainakaan laske arvosanaa. Esitys ei kuitenkaan ole pakollinen syksyllä 2022.



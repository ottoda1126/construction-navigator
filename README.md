# Construction Navigator Simulator

Selaimessa toimiva testisimulaattori. Sillä mitataan, nopeuttaako ja parantaako tekoälyn tuottama tilannekuva ja toimintaehdotus työnjohtajan päätöksiä runkovaiheen häiriöissä.

Testaaja ratkaisee ontelolaattojen toimitukseen ja asennukseen liittyviä häiriöitä, osan ilman tekoälyä ja osan tekoälyavustajan kanssa. Jokaisessa häiriössä hän päättää ensin seuraavan toimenpiteen ja kirjoittaa sitten viestin jokaiselle, jota päätös koskee. Simulaattori mittaa ajat, päätösten laadun, tiedottamisen ja päätösten kustannusvaikutuksen.

Toteutus: Metropolia Ammattikorkeakoulu, Minno 26 -innovaatioprojekti 2026, Trimble Finland Oy:n toimeksiannosta. Häiriöt perustuvat rakennusliikkeen projekti-insinöörin haastatteluun (marraskuu 2026).

---

## Sisällys

1. [Tiedostot](#1-tiedostot)
2. [Julkaiseminen](#2-julkaiseminen)
3. [Testin kulku](#3-testin-kulku)
4. [Tulosten keruu ja käsittely](#4-tulosten-keruu-ja-käsittely)
5. [Asetukset](#5-asetukset)
6. [Häiriöiden muokkaaminen](#6-häiriöiden-muokkaaminen)
7. [Mittarit ja pisteytys](#7-mittarit-ja-pisteytys)
8. [Rajoitteet](#8-rajoitteet)

---

## 1. Tiedostot

| Tiedosto | Sisältö |
|---|---|
| `index.html` | Koko simulaattori yhdessä tiedostossa: testi, tulosnäkymä, häiriöt ja asetukset. Ei ulkoisia riippuvuuksia lukuun ottamatta Google Fonts -kirjasimia, joiden puuttuessa käytetään järjestelmän kirjasimia. |
| `README.md` | Tämä ohje. |

Simulaattori ei tarvitse palvelinta, tietokantaa tai kirjautumista.

## 2. Julkaiseminen

Valitse jokin seuraavista:

**GitHub Pages (suositus).**
1. Luo GitHubissa uusi julkinen repository, esimerkiksi `construction-navigator`.
2. Lataa `index.html` ja `README.md` kohdasta *Add file → Upload files*.
3. Valitse *Settings → Pages*, aseta *Source: Deploy from a branch* ja *Branch: main / (root)*, ja tallenna.
4. Simulaattori on hetken kuluttua osoitteessa `https://<käyttäjä tai organisaatio>.github.io/construction-navigator/`.

Repositoryn omistajuuden voi siirtää toiselle käyttäjälle tai organisaatiolle kohdasta *Settings → Transfer ownership*.

**Oma verkkosivu.** Lataa `index.html` mille tahansa verkkopalvelimelle. Erityisasetuksia ei tarvita.

**Sähköpostiliite.** Tiedoston voi lähettää myös suoraan testaajalle, joka avaa sen selaimessa. Tämä sopii yksittäisille testaajille, mutta linkki on helpompi.

Linkkien lisäosat:

| Osoite | Toiminto |
|---|---|
| `…/` | Testi testaajalle |
| `…/#a` tai `…/#b` | Testi, jossa tekoälyversio on määrätty (ks. kohta 3) |
| `…/#tulokset` | Tulosnäkymä testin järjestäjälle |

## 3. Testin kulku

Testi kestää noin 25–30 minuuttia. Sen voi keskeyttää ja jatkaa myöhemmin samalla selaimella.

1. **Aloitus:** lyhyt ohje, testaajan nimi, rooli ja työkokemus. Nimen avulla järjestäjä tunnistaa tulokset ja voi karsia asiattomat vastaukset.
2. **Harjoitus 1** ilman tekoälyä ja **harjoitus 2** tekoälyavustajan kanssa. Harjoituksia ei lasketa tuloksiin.
3. **Kuusi mitattavaa häiriötä.** Häiriöt ja niiden vaihtoehdot ovat kaikilla testaajilla samassa järjestyksessä. Tekoäly on käytössä kolmessa häiriössä. Versioita on kaksi (A ja B), ja ne ovat toistensa peilikuvat: häiriö, joka ratkaistaan versiossa A tekoälyn kanssa, ratkaistaan versiossa B ilman. Simulaattori arpoo version, tai sen voi määrätä linkillä. Jokaisen häiriön yläreunassa näkyy, onko avustaja käytössä.
4. **Loppukysely:** avustajan hyödyllisyys, luottamus, helppokäyttöisyys ja tilanteiden realistisuus asteikolla 1–5 sekä vapaa kommentti.
5. **Yhteenveto ja tulosten lähetys.** Testaaja näkee, mitä hänen päätöksensä maksoivat verrattuna parhaisiin ratkaisuihin.

Jokainen häiriö etenee kolmessa vaiheessa:

1. **Päätös.** Testaaja kokoaa tilannekuvan välilehdiltä (aikataulu, toimitukset, tietomalli, resurssit, suunnitelmat ja sopimukset, viestit) ja valitsee toimenpiteen 3–4 vaihtoehdosta.
2. **Tiedotus.** Testaaja valitsee vastaanottajat ja kirjoittaa jokaiselle oman viestin.
3. **Varmuus.** Testaaja arvioi, kuinka varma hän on päätöksestään (1–5).

Tiedotusvaiheessa testaaja voi vielä palata muuttamaan päätöstään. Päätösajaksi lasketaan aika lopulliseen päätökseen, ja tuloksiin kirjataan myös ensimmäinen valinta. Häiriöilmoituksen kello käy nopeutettuna (1 minuutti vastaa 10 minuuttia työmaalla).

**Miksi kaksi versiota?** Jos tekoäly olisi aina samoissa häiriöissä, tekoälyn vaikutusta ei voisi erottaa häiriöiden vaikeuseroista. Kun testaajia on parillinen määrä, lähetä puolelle linkki `…/#a` ja puolelle `…/#b`.

Tekoälytilanteissa avustaja näyttää tilannekuvan, vaikutusketjun ja 2–3 vaihtoehtoa kustannusvaikutuksineen sekä suosituksensa ja tiedot, joihin se perustuu. Päätöksen jälkeen avustaja valitsee vastaanottajat ja kirjoittaa viestiluonnokset, joita testaaja voi muokata. Päätös on aina testaajan.

## 4. Tulosten keruu ja käsittely

### Google-lomake (suositus)

Tulokset tallentuvat automaattisesti Google-taulukkoon, eikä testaajan tarvitse lähettää mitään.

1. Luo Google Formsissa lomake, jossa on yksi kysymys tyypiltään *Kappale*. Älä vaadi kirjautumista.
2. Valitse lomakkeen valikosta *Hae esitäytetty linkki*, kirjoita kenttään jotain ja kopioi linkki.
3. Liitä linkki `index.html`-tiedoston asetukseen `googleFormLink` (ks. kohta 5).
4. Avaa lomakkeen *Vastaukset*-välilehdeltä vastaustaulukko. Jokainen testaaja on yksi rivi.
5. Kun haluat analysoida tulokset, kopioi taulukon vastaussarake ja liitä se tulosnäkymän kohtaan **Tuo tulokset**. Jo tuodut ohitetaan automaattisesti.

Selain ei saa Googlelta vahvistusta lähetyksen onnistumisesta. Testaajalle näytetään siksi myös varakeino: tulosteksti, jonka hän voi tarvittaessa lähettää sähköpostilla. Tarkista vastaustaulukosta, että tulos tuli perille.

### Sähköposti (ilman asetuksia)

1. Testin lopussa testaaja painaa **Kopioi tulokset** ja liittää tekstin sähköpostiin. Vaihtoehtoisesti hän tallentaa tulokset tiedostoksi ja liittää sen viestiin.
2. Järjestäjä avaa osoitteen `…/#tulokset` ja liittää yhden tai useamman sähköpostin tekstin kohtaan **Tuo tulokset** tai valitsee vastaanotetut tiedostot. Simulaattori poimii tulokset tekstistä automaattisesti ja ohittaa jo tuodut.

Tulostekstissä on testaajan vastaukset, ajat ja kirjoittamat viestit pakattuna. Se alkaa `CNSIM3.` ja päättyy `.END`.

**Tärkeää:** tuodut tulokset tallentuvat sen selaimen muistiin, jossa ne tuodaan. Käsittele tuloksia aina samalla selaimella ja tallenna **Vie varmuuskopio** -painikkeella säännöllisesti varmuuskopio. Varmuuskopion voi palauttaa samalla Tuo tulokset -toiminnolla, myös toiseen selaimeen.

### Oma palvelu (valinnainen)

Jos asetuksiin annetaan `submitUrl`, simulaattori lähettää tulokset testin lopussa automaattisesti HTTP POST -pyyntönä:

```
POST <submitUrl>
Content-Type: application/json

{ "type": "cnsim3", "run": { …testaajan tulokset… } }
```

Vastaanottavan palvelun pitää sallia pyynnöt simulaattorin osoitteesta (CORS). Jos lähetys epäonnistuu, testaajalle näytetään tulosteksti kuten ilman palvelinta.

### Tulosnäkymä

- Ryhmäsuodatin: ammattilaiset ja opiskelijat (rooli "Opiskelija"). Omat kokeilut kannattaa poistaa tulosnäkymästä ennen analyysia.
- Vertailu ilman tekoälyä ja tekoälyn kanssa kaikilla mittareilla.
- Tulokset häiriöittäin ja avustajan käyttö.
- Loppukyselyn tulokset ja kommentit.
- Testaajakohtainen näkymä: jokainen ratkaisu, kustannuserittely, viestit ja avatut tietolähteet aikoineen.
- Kustannusoletukset ja säästölaskelma. Yksikköhintoja ja oletuksia voi muuttaa, ja tulokset lasketaan uudelleen.
- CSV-vienti kaikista tai yhden testaajan tuloksista (puolipiste-eroteltu, avautuu Excelissä).

## 5. Asetukset

Asetukset ovat `index.html`-tiedoston ensimmäisen `<script>`-lohkon alussa (`CONFIG`):

| Asetus | Tarkoitus |
|---|---|
| `project` | Teksti aloitussivun yläreunassa |
| `googleFormLink` | Google-lomakkeen esitäytetty linkki. Tulokset lähetetään lomakkeelle automaattisesti (ks. kohta 4). |
| `contactName`, `contactEmail` | Kenelle testaaja lähettää tulokset. Jos tyhjä, testaajaa pyydetään vastaamaan viestiin, jossa hän sai linkin. |
| `submitUrl` | Oman palvelun osoite Google-lomakkeen sijaan (ks. kohta 4) |
| `about` | Alatunnisteen teksti |

Samassa lohkossa ovat myös kustannusarviot (`DEFAULT_RATES`), vastaanottajat (`RECIP`), kaikissa häiriöissä näkyvät asiakirjat (`DOCS_COMMON`), häiriöt (`SC`) ja testin koostumus (`PRACTICE`, `MEASURED`, `AI_VERSIONS`). Tiedoston muuhun koodiin ei tarvitse koskea.

Tiedostoa voi muokata millä tahansa tekstieditorilla. Tallenna se UTF-8-muodossa.

## 6. Häiriöiden muokkaaminen

Häiriöt ovat `SC`-objektissa. Jokaisella häiriöllä on tunnus (esim. `S1`). Kenttien selitykset ovat koodissa häiriöiden yläpuolella. Tärkeimmät säännöt:

- Jokaisessa häiriössä on täsmälleen **yksi paras vaihtoehto** (laatu 2), ja sen pitää olla kustannuksiltaan halvin. Muut ovat hyväksyttäviä (1) tai huonoja (0).
- Vaihtoehdot näytetään aina siinä järjestyksessä, jossa ne on kirjoitettu. Pidä vaihtoehdot suunnilleen yhtä pitkinä, jottei paras erotu pituudellaan, ja tee vääristä vaihtoehdoista uskottavia: oikean valinnan pitäisi vaatia tietojen tarkistamista välilehdiltä.
- **Kustannuserät** annetaan muodossa `I(laji, määrä, selite)`. Laji on `asentaja`, `nosturi` tai `rekka` (tunteja), `paiva` (rungon viivästys työpäivinä) tai `eur` (euroja). Euromäärä lasketaan yksikköhinnoista, joten hintojen muutos päivittää kaikki häiriöt.
- **Vastaanottajat** (`to`) ovat ne, joiden pitää saada tieto päätöksestä. Jokaiselle niistä kirjoitetaan avustajan viestiluonnos (`m`).
- `miss` kertoo, mitä maksaa, jos tarvittava vastaanottaja jää ilman viestiä. `ok` on lista vastaanottajista, joille viesti on hyväksyttävä mutta ei pakollinen. Muut lasketaan turhiksi vastaanottajiksi.
- Avustajan suositus (`ai.rec`) on yleensä paras vaihtoehto. Asettamalla `flawed:true` ja jättämällä parhaan vaihtoehdon pois listasta `ai.show` voi tehdä tarkoituksella puutteellisen ehdotuksen. Häiriö S4 on tällainen.
- **Määräaika** (`dl`) tekee häiriöstä aikakriittisen. Simulaatiokello kulkee `SPEED`-kertaisesti (oletus 10). Häiriössä S2 katselmuspyynnön pitää lähteä tehtaalle noin kolmessa minuutissa.

Uuden häiriön voi lisätä kopioimalla olemassa olevan, vaihtamalla tunnuksen ja lisäämällä sen listaan `MEASURED` (häiriöiden järjestys testissä) sekä jompaankumpaan versioon listassa `AI_VERSIONS`. Pidä versiot yhtä suurina.

Häiriöiden muuttaminen kesken keruun tekee tuloksista vaikeasti vertailtavia. Tee muutokset ennen testejä tai kerää uudet tulokset erikseen.

## 7. Mittarit ja pisteytys

| Mittari | Määritelmä |
|---|---|
| Päätösaika | Häiriön avaamisesta päätöksen vahvistamiseen |
| Tiedotusaika | Päätöksestä siihen, että viestit on lähetetty |
| Kokonaisaika | Päätösaika ja tiedotusaika yhteensä |
| Päätöksen laatu | Valitun vaihtoehdon laatu (0–2) |
| Tavoitettu | Kuinka moni päätöksen vaatimista vastaanottajista sai viestin |
| Turhat vastaanottajat | Viestit, jotka eivät olleet tarpeen |
| Kustannus | Valitun vaihtoehdon kustannus, tiedotuspuutteiden kustannus ja myöhästyneen määräajan kustannus yhteensä |
| **Ylimääräinen kustannus** | Kustannus miinus parhaan vaihtoehdon kustannus. Paras mahdollinen tulos on 0 €. |
| Päätöstä muutettu | Palasiko testaaja tiedotusvaiheesta vaihtamaan päätöstään |
| Varmuus | Testaajan oma arvio (1–5) |
| Avatut tietolähteet | Mitkä välilehdet testaaja avasi ja milloin |
| Avustajan käyttö | Valitsiko testaaja suosituksen, ja kuinka suuri osa viestiluonnoksista lähti muokkaamatta |

Säästölaskelma kertoo ylimääräisen kustannuksen ja ajan erotuksen ilman tekoälyä ja tekoälyn kanssa häiriöiden vuosimäärällä. Häiriöiden määrä, työmaiden määrä ja työnjohtajan tuntihinta ovat oletuksia, joita voi muuttaa tulosnäkymässä.

## 8. Rajoitteet

- **Avustaja on käsikirjoitettu.** Ehdotukset ja viestiluonnokset on kirjoitettu etukäteen. Simulaattori testaa konseptia eli sitä, miten tekoälyn tuottama tilannekuva vaikuttaisi päätöksiin. Se ei ole oikea tekoälyjärjestelmä.
- **Kustannukset ovat arvioita.** Yksikköhinnat ja seuraukset kannattaa tarkistaa ja päivittää ennen tulosten julkaisemista.
- **Valmiit vaihtoehdot helpottavat tehtävää.** Molemmat ryhmät näkevät samat vaihtoehdot, joten vertailu on reilu, mutta todellisuudessa vaihtoehdot pitää keksiä itse.
- **Pieni otos.** Muutaman testaajan tulokset ovat suuntaa antavia, eivät tilastollisesti merkitseviä.
- **Tulokset selaimen muistissa.** Tulosnäkymään tuodut tulokset ovat sen selaimen muistissa, jossa ne tuodaan. Google-lomakkeen vastaustaulukko toimii pysyvänä tallenteena, muuten ota varmuuskopio.
- **Versiot.** Jos häiriöitä tai vaihtoehtoja muutetaan, aiemmin kerätyt tulokset eivät ole enää vertailukelpoisia.
- **Tietosuoja.** Testi kysyy testaajan nimen. Tulokset ja testaajan kirjoittamat viestit kannattaa käsitellä luottamuksellisina, eikä nimiä julkaista raportissa.

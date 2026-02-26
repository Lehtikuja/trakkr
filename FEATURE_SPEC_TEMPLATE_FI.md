# Tavoiteseurantasovelluksen määrittelypohja (Rust-hybridi)

Tämä pohja on tarkoitettu siihen, että voit kirjata ideasi niin, että ne ovat:
- helposti priorisoitavia (MVP / V2 / Later)
- teknisesti toteutettavia ilman isoa uudelleensuunnittelua
- riittävän tarkkoja kehityksen käynnistämiseen


## 1) Vision statement (5–10 lausetta)

**Vastaa lyhyesti näihin:**
- Kenelle sovellus on?
- Mikä on tärkein hyöty käyttäjälle?
- Mikä tekee tästä paremman kuin paperi/taulukko?
- Mikä on “onnistumisen mittari” 3 kuukauden kohdalla?

**Täytä tähän:**

Tämän projektin tarkoituksena on luoda itselleni ADHD:n kanssa selviämiseen optimoitu elämänhallinnan apuväline. Tärkeimpiä asioita ovat tehtävien hallinta ja rutiinien kehittäminen ("tavoitteen seuranta"). Kriittistä on että sovellus on helppo käyttää, jotta sen käyttö ei jää pois ylimääräisen kitkan takia. Paperille tehty seuranta on aina heti valmiina, joten mahdollisimman nopea oikean sisällön löytäminen on tärkeää, jotta sovellus voisi kilpailla helppokäyttöisyydessä paperin kanssa. Toisaalta etua paperiin halutaan muokattavuuden osalta. Muutosten tekeminen ja tavoitteiden seuranta paperilla vaatii usein paljon uudelleen kirjoittamista ja ylimääräistä säätöä. Toisaalta on tärkeää pitää mielessä, että tavoitteiden uudelleen kirjoittaminen ja päivittäminen kirjoittamalla saattavat auttaa niiden iskostumisessa muistiin. Onnistumisen mittari 3kk kohdalla on se, että jonkinlainen versio on päivittäisessä käytössä.

---

## 2) Käyttäjäprofiilit

Listaa 1–3 pääkäyttäjätyyppiä.

| Profiili | Kuvaus | Tärkein tarve |
|---|---|---|
| Minä (Vaikea saada asioita hoidettua) | Haluaa lisätä elämän suunnitelmallisuutta, jotta saa asioita hoidettua tehokkaammin | Selkeä rakenne ja tärkeimpien asioiden esille tuominen (päivä, viikko) |
| Minä (Huonot rutiinit) | Haluaa kehittää itselleen toimivia rutiineja mitkä tekisivät tasaisesta asioiden tekemisestä helpompaa | Todella helppokäyttöinen rutiinien muistuttaminen ja seuranta |
| Minä (Hajautunut keskittyminen)| Sata keskeneräistä projektia ja tavoitetta joita pitäisi saada edistettyä ADHD-sopivalla tavalla | Erilaisten projektien jaottelu tehtävälistoihin ja tehtävien asettelu aikatauluihin |

---

## 3) Ominaisuuslista (master backlog)

Listaa kaikki ideat ensin tähän. Priorisointi tehdään seuraavassa osiossa.

| ID | Ominaisuus | Lyhyt kuvaus |
|---|---|---|
| F-001 | Päivän ToDo | Päivän oma sivu, jossa näkyy yhdessä näkymässä mitä tänään pitää tehdä. Esim. top 3 tehtävät ja ei niin kriittinen muistilista sekä rutiinien kehitys. Tämä olisi etusivu mikä aukeaa aina ensin, jotta olellisimmat asiat on helppo löytää |
| F-002 | Seuraavan päivän ToDo | Voi jo ennakkoon suunnitella seuraavaa päivää, kun tulee ideioita päivän mittaan |
| F-003 | Viikon ToDo | Viikon sivu, josta poimitaan tehtäviä päivän sivulle |
| F-004 | Seuraavan viikon ToDo | Seuraavan viikon valmistelu. Ideana, että kun yksi viikko loppuu, voi seuraavalle viikolle jo olla jotain valmiina eikä tarvitse kerralla suunnitella koko viikkoa |
| F-005 | Kuukauden kalenteri | Korkeamman tason tehtävälista kalenterin muodossa. etukäteen suunnitellut asiat täällä |
| F-006 | Rutiinin muodostus | Voi luoda tavoitteen ja sitä varten päivittäiset tehtävät |
| F-007 | Kalenteri-integraatio | Integraatio kalenterin kanssa, ja mahdollisuus tuoda ja viedä kalenterimerkintöjä |
| F-008 | Henkilökohtaisten projektien hallinta | tavallaan sama kuin tavoitteiden seuranta, mutta yksittäisille projekteille, eikä toistuviin rutiineihin. Tarkoitus ei ole olla mikään massiivinen projektinhallintakokonaisuus, vaan henkilökohtaiseen seurantaan |
| F-009 | Projektisivu | kaikkien omien projektien hallinnointi ja seuranta |
| F-010 | Rutiinien ja tapojen analysointi | kerätään suoriutumisesta dataa ja tehdään raportti, joka ehdottaa sen pohjalta toimivia toimintamalleja tulevien tavoitteiden tehokkaamman onnistumisen avuksi |
| F-011 | Hyvien työskentelytapojen apu | pomodoroajastin yms. mahdollisia tehostustyökaluja rutiinien avuksi |
| F-012 | Liikuntatavoittet | spesifisti urheiluun liittyvien ja muidenkin tarkemmin rajattujen tavoiteryhmien omat tarkemmat kategoriat |
| F-013 | Valmiit pohjat tavoitteille| tavoitteiden seurannan ja projektien valmiit pohjat |
| F-014 | Tapahtumaoliot | ToDo listat koostuvat tapahtumaolioista joiden päivittäminen ja lisääminen päivittää tilannetta relevanteissa muissa listoissa |
| F-015 | Tavoiteohjelmat | tavoitteiden seurannan laajemmat kokonaisuudet muokattavuuden kanssa |
| F-016 | Mittarit | tavoitteiden seurantaan käytettävät mittarit ja niiden datan tallentaminen kehityksen seuraamiseksi |
| F-017 | Muokattavat pohjat ToDo sivuille| päivän ja viikon sivujen kustomointi |
| F-018 | ToDo sivu kaikille tuleville tehtäville | ADHD käyttäjälle pelkkään kalenteriin pohjautuva ratkaisu ei toimi. Erillinen sivu jossa voi hallinnoida epämääräisellä aikataululla tehtäviä asioita |
| F-019 | Ajastetut suunnittelusessiot | Ajastetut päivän ja viikon suunnittelut |
| F-020 | Valmiit suunnitteluprosessit | Päivän ja viikon suunnitteluun puoliautomaattiset helpottavat prosessit, joissa valitaan tehtäviä |
| F-021 | Top-3 ToDo siirtyy huomiselle | Tekemättömät tärkeät tehtävät siirtyvät huomiselle tai takaisin viikon listalle tai yleislistalle |
| F-022 | Alitehtävät | Tähtävien sijoittaminen toisen tehtävän alle |
| F-023 | Tehtävien luokittelu | Tähtävien luokittelu esim. värien avulla tyypin mukaan |
| F-024 | Rutiinien joukot | Käytännössä alitehtävät rutiineille |
| F-025 | Lyhyen tähtäimen tavoitteet | Esim. päivän tai viikon tavoite oman ajattelun kehittämiselle. Eli ei siis tehtävä vaan abstraktimpi tavoite. Voisi olla joku isompi ajatus taustalla -> mikä auttaisi ADHD:n kanssa |


---

## 4) Priorisointi

Merkitse jokainen ominaisuus yhteen luokkaan:
- **MVP** = pakollinen ensimmäiseen julkaisuun
- **V2** = tärkeä, mutta voi odottaa
- **Later** = hyvä idea myöhemmäksi

| ID | Prioriteetti (MVP/V2/Later) | Perustelu |
|---|---|---|
| F-001 | MVP | Tärkein ominaisuus |
| F-002 | MVP/V2 | Sulavan toiminnan kannalta melko tärkeä. Käytännössä voi olla kopio edellisestä|
| F-003 | MVP | Pisin pakollinen ajanjakso minkäänlaiseen järkevään elämän suunnitteluun |
| F-004 | MVP/V2 | Käytännössä sama kuin F-002 |
| F-005 | V2 | Toimii ilman omaa sisäistä kalenteria, mutta vähentäisi merkittävästi kitkaa, jos ei tarvitse käsin lisätä asioita toisesta kalenterista |
| F-006 | MVP | Simppelissä muodossa tärkeä. Käytännössä toistuva kalenterimerkintä. Hienommat ominaisuudet voi lisätä myöhemmin |
| F-007 | Later | Jos on oma kalenteri ei niin kriittinen, mutta helpottaa siirtymävaihetta. JOs tämä sovellus ei toimi täydellisesti kaikkeen, mahdollistaa silti käytön jatkamisen muiden sovellusten kanssa yhdessä. |
| F-008 | V2 | Henkilökohtaisesti tärkeä, ja uskon että toimisi osittain samalla pohjalla kuin tavoitteiden seuranta |
| F-009 | Later | Erilaiset dashboardid voivat olla käteviä, mutta pitää miettiä erittäin tarkkaan ettei aiheuteta infoähkyä |
| F-010 | Later | Ei edes välttämättä tärkeä ollenkaan, sekä varmasti vaikea toteuttaa |
| F-011 | Later | Ei välttämättä hyödyllinen samassa paketissa. Jos myöhemmin nähdään hyvä tapa integroida niin voidaan tehdä |
| F-012 | Later | lisäominaisuus. Ehkä voisi olla myös samalla pohjalla toimiva rinnakkainen sovellus ja sen integrointi. |
| F-013 | V2 | Ainakin vakiopohjat ja järkevät tavat seurata pitää rakentaa sisään. Vaihtoehtoiset erilaiset pohjat voidaan tehdä jos koetaan hyödyllisiksi |
| F-014 | V2 | Helpottaa käyttöä merkittävästi, jos toimii hyvin |
| F-013 | V2 | Ainakin vakiopohjat ja järkevät tavat seurata pitää rakentaa sisään. Vaihtoehtoiset erilaiset pohjat voidaan tehdä jos koetaan hyödyllisiksi |
| F-014 | MVP | mahdollistaa tehtävien siirtelyn tehokkaasti |
| F-015 | Later | Mahdollistaisi monimutkaisempien tavoitteiden seuraamisen. ei kriittistä |
| F-016 | Later | Monimutkaisemmille tavoitteille välttämätön, mutta rutiineille ei |
| F-017 | Later | koska kehitän alkuun itselle, ei tärkeää |
| F-018 | MVP | Hyvinkin tärkeä, että tehtävät pysyy järjestyksessä vaikkei niille olisi ennalta ajankohtaa |
| F-019 | V2 | helpottaa muistamista |
| F-020 | Later | Jos helpottaa oikeasti niin toteutetaan |
| F-021 | V2 | Jonkinlainen automaattinen tehtävien siirtely vähentää itse tehtävän kirjoittamisen tarvetta |
| F-022 | V2 | Mahdollistaa isompien tehtävien jaottelun |
| F-023 | Later | Helpottaisi hahmottamista |
| F-024 | V2 | Selkeyttäisi rutiineja |
| F-025 | Later | Erilaisia ajattelutapoja lisää eikä vain keskittymistä koviin tavoitteisiin |

---

## 5) Ominaisuuskohtainen speksi (täytä per ominaisuus)

Kopioi tämä lohko jokaiselle tärkeälle ominaisuudelle (ainakin MVP-ominaisuuksille).

### [ID: F-014] [Tapahtumaoliot]

**Käyttäjätarina**  
Haluan että tapahtumat ovat oma joukkonsa, jotta voin merkitä niille statuksen ja tärkeyden.

**Hyväksymiskriteerit**
- [ ] Tehtävällä on kriittisimmät muuttujansa, jotta niitä voi merkitä tehdyksi ja siirtää eri sivuille
- [ ] aikataulua voi muuttaa ja tehtävä siirtyy toiselle sivulle
- [ ] tehtävä poistuu päivän/viikon lopussa kun se on suoritettu

**Tarvittava data**
- Entiteetit: `task`
- Kentät: `id`, `category`, `scheduled_at`, `status`, `note`
- Validoinnit:

**API-tarve (alustava)**
- Endpoint: 
- Metodi:
- Pyyntö:
- Vastaus:

**Riippuvuudet**
- Riippuu ominaisuuksista:
- Estää ominaisuuksia:

**Prioriteetti**
- MVP

---

### [ID: F-006] [Rutiinin muodostus]

**Käyttäjätarina**  
Haluan että rutiiniksi tahtomani toiminta lisätään todo-listalle, jotta muistan tehdä ne tarvittavalla toistuvuudella.

**Hyväksymiskriteerit**
- [ ] Rutiinitavoitteen mukaiset tehtävät lisätään automaattisesti tehtävälistoille
- [ ] Rutiini "lisää" vain oikean määrän tehtäviä oikeaan paikkaan
- [ ] Halutun rutiinin voi lisätä tai poistaa

**Tarvittava data**
- Entiteetit: `routine_task`
- Kentät: `id`, `category`, `frequency`, `note`
- Validoinnit: 

**API-tarve (alustava)**
- Endpoint:
- Metodi:
- Pyyntö:
- Vastaus:

**Riippuvuudet**
- Riippuu ominaisuuksista:
- Estää ominaisuuksia:

**Prioriteetti**
- MVP

### [ID: F-001] [Päivän ToDo]

**Käyttäjätarina**  
Haluan nähdä päivän tavoitteet, jotta ainakin pari tärkeintä asiaa tulisi hoidettua.

**Hyväksymiskriteerit**
- [ ] Checkboxeja sisältävä pohja johon voi täyttää päivän tehtävät ja merkitä niitä tehdyksi
- [ ] Kaikki näkyy yhdessä näkymässä ilman ylimääräisiä UI elementtejä
- [ ] automaattisesti rutiininseuranta

**Tarvittava data**
- Entiteetit:
- Kentät: 
- Validoinnit: 

**API-tarve (alustava)**
- Endpoint:
- Metodi:
- Pyyntö:
- Vastaus:

**Riippuvuudet**
- Riippuu ominaisuuksista:
- Estää ominaisuuksia:

**Prioriteetti**
- MVP

### [ID: F-003] [Viikon ToDo]

**Käyttäjätarina**  
Haluan nähdä viikon tavoitteet, jotta pystyn suunnittelemaan elmääni sopivaksi ajaksi eteenpäin.

**Hyväksymiskriteerit**
- [ ] Checkboxeja sisältävä pohja johon voi täyttää päivän tehtävät ja merkitä niitä tehdyksi
- [ ] Näkymä voi olla monimutkaisempi kuin päivänäkymä, mutta pitäisi olla aikataulutetuille tehtäville oma kohtansa ja isommat tavoitteet viikolle
- [ ] helppo siirtäminen tälle päivälle tai huomiselle

**Tarvittava data**
- Entiteetit:
- Kentät: 
- Validoinnit: 

**API-tarve (alustava)**
- Endpoint:
- Metodi:
- Pyyntö:
- Vastaus:

**Riippuvuudet**
- Riippuu ominaisuuksista:
- Estää ominaisuuksia:

**Prioriteetti**
- MVP


## 6) Domain-malli (ensimmäinen versio)

Kirjaa ydinkäsitteet ja niiden suhteet.

**Ydinkäsitteet (esimerkki):**
- Routine (rutiini)
- Task (tehtävämerkintä)
- Frequency (toistuvuus)
- Category (tehtävän luokka: esim. raskas/mukava, nopea/hidas)

**Suhteet:**
- Task kuuluu johonkin Categoryyn.
- Rutiinilla on yksi Frequency.

---

## 7) Aika- ja kalenterisäännöt (erittäin tärkeä)

- Käyttäjän aikavyöhyke: Helsinki
- Tallennusmuoto tietokannassa (suositus: UTC):
- Milloin päivä vaihtuu: 00:00
- Viikon ensimmäinen päivä (ma/su): ma
- Miten streak lasketaan: 
- Miten toimitaan kesä-/talviajan vaihdossa:

---

## 8) Tekninen suunta (Rust-hybridi)

**Frontend**
- Next.js + TypeScript

**Backend**
- Rust + Axum?

**Tietokanta**
- PostgreSQL

**Infra (myöhemmin tarkennetaan)**
- Docker Compose dev-ympäristölle
- Mahdollinen deploy: Fly.io / Railway / Render / VPS

---

## 9) Ei-toiminnalliset vaatimukset

- Suorituskykytavoite (esim. kalenterin lataus < 500 ms)
- Luotettavuus (varmuuskopiointi, migraatiot)
- Tietoturva (autentikointi, tietojen eristys)
- Käytettävyys (mobiili/desktop)

---

## 10) MVP-rajauksen lukitus

Valitse tähän **vain 3–5 ominaisuutta**, jotka tehdään ensin.

| MVP-ominaisuus | Miksi pakollinen? | Mitä EI tehdä vielä |
|---|---|---|
| Tehtäväolio | kaiken perusta | Ei vielä lapsiolioita tai hienompia logiikoita |
| Näkymät | Päivän ja viikon tehtävien hahmotus | Automaatiota siirtoon tai muokattavia näkymiä |
| Rutiinit | Olisi tärkeää kehittää paremman toimintakyvyn saamiseksi | Suunnitelmia joissa eri rutiineja tai ryhmiä tai ajastusta |

---

## 11) Sprintti 0 (valmistelu)

- [ ] Repo ja kansiorakenne
- [ ] Backend skeleton (Axum)
- [ ] Frontend skeleton (Next.js)
- [ ] DB + migraatiot
- [ ] Ensimmäinen pystyslice (luo tavoite + näytä listassa)

---

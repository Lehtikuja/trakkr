# Tavoiteseurantasovelluksen määrittelypohja (Rust-hybridi)

Tämä pohja on tarkoitettu siihen, että voit kirjata ideasi niin, että ne ovat:
- helposti priorisoitavia (MVP / V2 / Later)
- teknisesti toteutettavia ilman isoa uudelleensuunnittelua
- riittävän tarkkoja kehityksen käynnistämiseen

---

## Miten muokkaan tätä tiedostoa?

Et tarvitse tähän mitään erikoista työkalua. Alla 3 helppoa tapaa:

1. **VS Code / Cursor / muu editori**
   - Avaa projekti.
   - Avaa tiedosto `FEATURE_SPEC_TEMPLATE_FI.md`.
   - Kirjoita kohdat suoraan paikoilleen (esim. Vision statement, ominaisuudet).
   - Tallenna (`Ctrl+S` / `Cmd+S`).

2. **GitHubin web-editorissa**
   - Avaa tiedosto repossa.
   - Paina kynä-kuvaketta (**Edit this file**).
   - Tee muutokset ja commitoi.

3. **Terminaalissa (nano)**
   - Aja komento: `nano FEATURE_SPEC_TEMPLATE_FI.md`
   - Muokkaa tekstiä.
   - Tallenna: `Ctrl+O`, Enter
   - Poistu: `Ctrl+X`

Vinkki: täytä ensin vain kohdat **1, 3, 4 ja 10**. Niillä pääset nopeasti liikkeelle, ja tarkennat loput myöhemmin.

---


## Miten saan tämän näkyviin GitHubissa?

Lyhyesti: **kyllä**, tiedosto pitää olla gitissä (commit) ja commit pitää myös **puskea** GitHubiin.

Peruspolku komentorivillä:

1. Tarkista tila
   - `git status`
2. Lisää tiedosto commitiin
   - `git add FEATURE_SPEC_TEMPLATE_FI.md`
3. Tee commit
   - `git commit -m "Päivitä määrittelypohjaa"`
4. Tarkista mille haaralle olet
   - `git branch --show-current`
5. Puske GitHubiin
   - `git push -u origin <haaran-nimi>` (ensimmäisellä kerralla)
   - seuraavilla kerroilla yleensä riittää `git push`

Jos `git status` näyttää **"nothing to commit, working tree clean"**, kaikki paikalliset muutokset on jo commitoitu. Jos et silti näe GitHubissa mitään, yleisin syy on että committeja ei ole vielä pusketty (`git push`).

Pikadiagnoosi, jos GitHub ei päivity:
- `git remote -v` → varmista että `origin` osoittaa oikeaan GitHub-repoon
- `git log --oneline -n 5` → varmista että oma commit on olemassa
- `git push` → lähetä commitit etärepoon


## 1) Vision statement (5–10 lausetta)

**Vastaa lyhyesti näihin:**
- Kenelle sovellus on?
- Mikä on tärkein hyöty käyttäjälle?
- Mikä tekee tästä paremman kuin paperi/taulukko?
- Mikä on “onnistumisen mittari” 3 kuukauden kohdalla?

**Täytä tähän:**

```
[Kirjoita vision statement tähän]
```

---

## 2) Käyttäjäprofiilit

Listaa 1–3 pääkäyttäjätyyppiä.

| Profiili | Kuvaus | Tärkein tarve |
|---|---|---|
| Profiili 1 |  |  |
| Profiili 2 |  |  |
| Profiili 3 |  |  |

---

## 3) Ominaisuuslista (master backlog)

Listaa kaikki ideat ensin tähän. Priorisointi tehdään seuraavassa osiossa.

| ID | Ominaisuus | Lyhyt kuvaus |
|---|---|---|
| F-001 |  |  |
| F-002 |  |  |
| F-003 |  |  |

---

## 4) Priorisointi

Merkitse jokainen ominaisuus yhteen luokkaan:
- **MVP** = pakollinen ensimmäiseen julkaisuun
- **V2** = tärkeä, mutta voi odottaa
- **Later** = hyvä idea myöhemmäksi

| ID | Prioriteetti (MVP/V2/Later) | Perustelu |
|---|---|---|
| F-001 |  |  |
| F-002 |  |  |
| F-003 |  |  |

---

## 5) Ominaisuuskohtainen speksi (täytä per ominaisuus)

Kopioi tämä lohko jokaiselle tärkeälle ominaisuudelle (ainakin MVP-ominaisuuksille).

### [ID: F-XXX] [Ominaisuuden nimi]

**Käyttäjätarina**  
Haluan [toiminto], jotta [hyöty].

**Hyväksymiskriteerit**
- [ ]
- [ ]
- [ ]

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
- MVP / V2 / Later

---

## 6) Domain-malli (ensimmäinen versio)

Kirjaa ydinkäsitteet ja niiden suhteet.

**Ydinkäsitteet (esimerkki):**
- Goal (tavoite)
- GoalEntry (päiväkohtainen merkintä)
- ScheduleRule (toistuvuus)
- Reminder (muistutus)

**Suhteet:**
- Yhdellä Goalilla on monta GoalEntryä.
- Goalilla voi olla yksi tai useampi ScheduleRule.

---

## 7) Aika- ja kalenterisäännöt (erittäin tärkeä)

Täytä nämä eksplisiittisesti:

- Käyttäjän aikavyöhyke:
- Tallennusmuoto tietokannassa (suositus: UTC):
- Milloin päivä vaihtuu:
- Viikon ensimmäinen päivä (ma/su):
- Miten streak lasketaan:
- Miten toimitaan kesä-/talviajan vaihdossa:

---

## 8) Tekninen suunta (Rust-hybridi)

**Frontend**
- Next.js + TypeScript

**Backend**
- Rust + Axum

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
| 1. |  |  |
| 2. |  |  |
| 3. |  |  |
| 4. |  |  |
| 5. |  |  |

---

## 11) Sprintti 0 (valmistelu)

- [ ] Repo ja kansiorakenne
- [ ] Backend skeleton (Axum)
- [ ] Frontend skeleton (Next.js)
- [ ] DB + migraatiot
- [ ] Ensimmäinen pystyslice (luo tavoite + näytä listassa)

---

# Esimerkkikuvaus: miten pohja täytetään

Alla yksi tiivis esimerkki samasta rungosta.

## 1) Vision statement (esimerkki)

Rakennan henkilökohtaisen tavoiteseurantasovelluksen, jossa päivittäinen käyttö on nopeampaa kuin paperivihossa. Haluan nähdä kalenterista yhdellä silmäyksellä, miten hyvin olen toteuttanut viikko- ja päivätavoitteeni. Sovelluksen pitää tukea joustavia tavoitteita (esim. 3 kertaa viikossa), ei vain “joka päivä” -mallia. Tärkein hyöty on jatkuvuus: onnistun pitämään rutiinit käynnissä ilman monimutkaista kirjaamista. 3 kuukauden onnistumismittari on, että kirjaan merkinnät vähintään 5 päivänä viikossa ja käytän samaa sovellusta kaikkien päätavoitteideni seurantaan.

## 2) Käyttäjäprofiilit (esimerkki)

| Profiili | Kuvaus | Tärkein tarve |
|---|---|---|
| Minä (aktiivinen suunnittelija) | Haluaa suunnitella viikon tavoitteet etukäteen | Nopea kalenterimerkintä |
| Minä (kiireinen arki) | Ei jaksa käyttää monimutkaista UI:ta | 10 sekunnin kirjaus |

## 3–4) Ominaisuudet + priorisointi (esimerkki)

| ID | Ominaisuus | Prioriteetti | Perustelu |
|---|---|---|---|
| F-001 | Tavoitteen luonti | MVP | Ilman tätä ei ole seurattavaa |
| F-002 | Päiväkohtainen done/skip-merkintä | MVP | Ydintoiminto |
| F-003 | Kuukausikalenterin näkymä | MVP | Antaa näkyvyyden etenemiseen |
| F-004 | Viikkoraportti | V2 | Hyödyllinen mutta ei pakollinen aloitukseen |
| F-005 | Push-muistutukset | Later | Vaatii lisäinfraa |

## 5) Ominaisuusspeksi (esimerkki yhdestä)

### [ID: F-002] Päiväkohtainen done/skip-merkintä

**Käyttäjätarina**  
Haluan merkitä päivän tavoitteen tehdyksi tai ohitetuksi, jotta näen toteuman kalenterissa.

**Hyväksymiskriteerit**
- [ ] Käyttäjä voi valita päivän ja asettaa tilan `done` tai `skip`.
- [ ] Sama päivä päivittyy, eikä synny duplikaattimerkintää.
- [ ] Kalenterin päiväsolun väri muuttuu tilan mukaan.

**Tarvittava data**
- Entiteetit: `goal_entries`
- Kentät: `id`, `goal_id`, `entry_date`, `status`, `note`, `updated_at`
- Validoinnit: vain yksi merkintä per (goal_id, entry_date)

**API-tarve (alustava)**
- Endpoint: `/api/v1/goals/{goalId}/entries`
- Metodi: `PUT`
- Pyyntö: `{ "entryDate": "2026-02-26", "status": "done", "note": "Kevyt lenkki" }`
- Vastaus: päivitetty entry-objekti

**Riippuvuudet**
- Riippuu ominaisuuksista: F-001
- Estää ominaisuuksia: ei estä, mutta mahdollistaa F-003 ja F-004

**Prioriteetti**
- MVP

## 7) Aika- ja kalenterisäännöt (esimerkki)

- Käyttäjän aikavyöhyke: `Europe/Helsinki`
- Tallennusmuoto tietokannassa: UTC
- Päivä vaihtuu: käyttäjän paikallisen ajan mukaan klo 00:00
- Viikon ensimmäinen päivä: maanantai
- Streak-logiikka: done kasvattaa streakia, skip nollaa streakin
- DST-vaihto: päivät lasketaan paikallisen päivämäärän perusteella

## 10) MVP-rajauksen lukitus (esimerkki)

| MVP-ominaisuus | Miksi pakollinen? | Mitä EI tehdä vielä |
|---|---|---|
| Tavoitteen luonti | Luo seurannan perustan | Ei vielä tavoitemalleja |
| Päivämerkinnät | Mahdollistaa todellisen käytön | Ei vielä kommenttihistoriaa |
| Kuukausikalenteri | Tekee etenemisen näkyväksi | Ei vielä viikkonäkymää |
| Peruslistaus tavoitteista | Navigointi | Ei vielä kategorioita/tägejä |

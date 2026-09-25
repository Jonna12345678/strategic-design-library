# Metadata-skeema

Jokainen skilli/käytäntö on oma `.md`-tiedosto `methods/`-kansiossa. Tiedoston alussa on YAML-frontmatter, jonka avulla sekä Claude Skill että web-UI voivat hakea ja suodattaa sisältöä. Frontmatterin jälkeen tulee vapaamuotoinen kuvaus.

## Kentät

| Kenttä | Pakollinen | Kuvaus |
|---|---|---|
| `id` | kyllä | Uniikki kebab-case-tunniste, sama kuin tiedostonimi ilman päätettä |
| `nimi` | kyllä | Ihmisluettava nimi |
| `kategoria` | kyllä | Ylätason projektityyppi. Alkuvaiheessa kaksi arvoa:<br>`visio-ja-strategia`<br>`konseptointi-ja-tuotekehitys` |
| `tiivistelma` | kyllä | 1–2 lausetta: mikä tämä on |
| `tilanteet` | kyllä | Lista tilanne-/ongelmatunnisteita, joissa tätä kannattaa ehdottaa. Näiden perusteella Claude/UI löytää oikean skillin. Konkreettisia, ei yleisluontoisia (esim. "suunta on hukassa uuden liiketoiminta-alueen käynnistyessä", ei "strategiatyö") |
| `ei_sovi_kun` | kyllä | Milloin TÄTÄ EI pidä ehdottaa. Yhtä tärkeä kuin `tilanteet` — estää väärät osumat |
| `lahtotiedot` | kyllä | Mitä pitää olla käytettävissä ennen kuin menetelmää voi soveltaa (data, osallistujat, aiempi työ) |
| `kesto` | ei | Karkea aika-arvio (esim. "puolen päivän työpaja", "2–3 viikon prosessi") |
| `prosessi` | kyllä | Vaiheet järjestyksessä (kirjoitetaan leipätekstinä frontmatterin jälkeen, ei listakenttänä — pidempi sisältö) |
| `output` | kyllä | Mitä prosessin lopputuloksena syntyy konkreettisesti |
| `liittyvat` | ei | Muiden `id`-arvojen lista: vaihtoehtoiset tai täydentävät menetelmät |
| `lahde` | kyllä | `oma` (oma kehittämä/muokkaama käytäntö) tai ulkoisen lähteen nimi, jos menetelmä pohjautuu tunnettuun frameworkiin |
| `paivitetty` | kyllä | YYYY-MM-DD |

## Uuden skillin lisääminen

1. Kopioi olemassa oleva `.md`-tiedosto `methods/`-kansiosta pohjaksi
2. Täytä kentät yllä olevan taulukon mukaan — älä jätä `tilanteet`- tai `ei_sovi_kun`-kenttiä tyhjiksi, ne ovat hakukyvyn ydin
3. Lisää rivi `index.json`-tiedostoon (voi generoida uudelleen kaikista `methods/`-tiedostoista)
4. Commit ja push — Claude Skill ja julkaistu web-UI synkataan tästä

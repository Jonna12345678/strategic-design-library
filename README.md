# Strategic Design Library

Henkilökohtainen kirjasto skilleistä ja parhaista käytännöistä strategiseen suunnitteluun. Tarkoitus: auttaa löytämään oikea menetelmä, framework tai workflow tiettyyn strategiseen tilanteeseen — sekä itselle että myöhemmin muille.

## Rakenne

```
strategic-design-library/
├── README.md
├── index.json              ← koneluettava hakuindeksi, generoitu methods/-kansiosta
├── schema/
│   └── method-schema.md    ← metadata-kenttien dokumentaatio
└── methods/
    ├── north-star-visiotyopaja.md
    └── tarvelahtoinen-yhteissuunnittelu.md
```

## Kategoriat (laajenee ajan myötä)

- **Visio- ja strategiatyö** (`visio-ja-strategia`)
- **Palvelun konseptointi ja tuotekehitys** (`konseptointi-ja-tuotekehitys`)

## Uuden skillin lisääminen

Katso [`schema/method-schema.md`](schema/method-schema.md).

## Käyttö

- **Claude Skill**: lukee tämän repon sisällön ja poimii tilannekuvauksen perusteella oikean menetelmän
- **Julkaistu web-UI**: selattava versio kirjastosta, generoidaan tämän repon datasta

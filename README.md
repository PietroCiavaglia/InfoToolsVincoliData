# InfoToolsVincoliData

Repository pubblico dei dataset mensili dei **Vincoli Logistici** usati da InfoToolsDesktop.

## Scopo

Questo repository contiene esclusivamente dati derivati da fonti pubbliche/istituzionali e artifact di distribuzione. Non contiene:

- codice applicativo;
- credenziali;
- token;
- dati LOCAL o CENTRAL;
- dati personali aziendali;
- istruzioni SQL o di apply.

Il contratto autorevole di generazione resta nel repository privato `PietroCiavaglia/InfoToolsDesktop`.

## Flusso operativo

```text
ChatGPT task mensile
        ↓
ricerca Web / fonti istituzionali
        ↓
InfoToolsVincoliData
        ↓ HTTPS anonimo
InfoToolsDesktop
        ↓
validazione schema/hash
        ↓
confronto e piano
        ↓
apply governato
```

## Layout

```text
latest.json
schemas/
    LATEST_SCHEMA_V1.json
YYYY-MM/
    dataset.json
    manifest.json
    report.md
```

`latest.json` viene creato/aggiornato solo quando esiste un pacchetto mensile strutturalmente valido e coerente con il manifest.

## Regole principali

- Perimetro ordinario: 317 Comuni di Umbria e Marche.
- Profilo: veicoli MERCI con massa massima <= 3.500 kg.
- Fonti prioritarie: istituzionali.
- Nessuna assenza equivale automaticamente a cessazione.
- I casi non dimostrati restano `DA_VERIFICARE`.
- Dataset parziali sono ammessi e devono proteggere i Comuni incompleti da mutazioni/disattivazioni.
- Nessun vincolo manuale viene modificato automaticamente.
- La generazione non accede a LOCAL/CENTRAL e non effettua apply.
- InfoToolsDesktop usa lo stesso dataset e lo stesso SHA per LOCAL e CENTRAL.

## Contratti autorevoli

Nel repository `PietroCiavaglia/InfoToolsDesktop`, branch `main`:

- `docs/prompts/vincoli-logistici/MASTER_PROMPT_VINCOLI_V1.md`
- `docs/prompts/vincoli-logistici/DATASET_SCHEMA_V1.json`
- `docs/prompts/vincoli-logistici/MANIFEST_SCHEMA_V1.json`
- `docs/ITD-0034-01_SPECIFICA_DATASET_CANONICO_V1.md`

Hash V1:

- MASTER PROMPT: `2BAD853D815F98BDC526710DF821EB2BB303FB5796C4B7D1E92D679EB10B0F15`
- DATASET SCHEMA: `9BB53C8440123989CD838525B4580FA3B1CD7CD49F448AA39322F647F4904A15`
- MANIFEST SCHEMA: `1FDA1B25AC44B5B68F6858FEF78D87003ADDD95761FC97321462D52C1D6C179E`

## Stato

Canale dati operativo pubblico per InfoToolsDesktop.

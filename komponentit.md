---
title: "Komponentit – Suomen Palikkaharrastajat ry"
description: "Käyttöliittymäkomponenttien esittely ja käyttöesimerkit."
slug: komponentit
published: true
nav: true
navTitle: "Komponentit"
order: 2
---

# Komponentit

Kaikki komponentit ovat käytettävissä Markdown-sisällössä HTML-tageina. Komponentit on toteutettu Elm-moduuleina hakemistossa `src/Component/`.

---

## Ilmoitukset (Alert)

Käytä `<callout>` -tagia huomioilmoituksiin. `type`-attribuutti voi olla `info`, `success`, `warning` tai `error`.

<callout type="info">

**Informaatio** — Tämä on tiedote. Käytä sitä hyödylliseen taustatietoon tai vinkkeihin.

</callout>

<callout type="success">

**Onnistui** — Toiminto suoritettiin onnistuneesti.

</callout>

<callout type="warning">

**Varoitus** — Tarkista syöte ennen jatkamista.

</callout>

<callout type="error">

**Virhe** — Jotain meni pieleen. Yritä uudelleen.

</callout>

---

## Hero-osio

Sivun pääosio, jossa on otsikko, alaotsikko ja toimintopainikkeet.

<hero title="Rakenna kauniita sivustoja" subtitle="Elm-pages-pohjainen staattinen sivugeneraattori suunnittelutokeneilla.">

<button-link href="#" variant="primary">Pääpainike</button-link>
<button-link href="#" variant="secondary">Toissijainen</button-link>
<button-link href="#" variant="ghost">Ghost</button-link>

</hero>

---

## Kortit (Card)

Käytä `<card>` -tagia sisältökortteihin.

<card title="Otsikollinen kortti">

Tämä on kortin sisältö. Kortit sopivat yksittäisten kokonaisuuksien esittämiseen, kuten artikkelien, palveluiden tai tuotteiden tiivistelmiin.

</card>

<card>

Kortti ilman otsikkoa. Käytä kun sisältö puhuu puolestaan.

</card>

---

## Haitari (Accordion)

Käytä `<accordion>` ja `<accordion-item>` -tageja laajennettaviin osioihin.

<accordion>

<accordion-item summary="Mikä on elm-pages?">

elm-pages on staattinen sivugeneraattori, joka käyttää Elm-ohjelmointikieltä. Jokainen sivu tyyppitarkastetaan käännösaikana.

</accordion-item>

<accordion-item summary="Miten komponentteja käytetään Markdownissa?">

Lisää HTML-tagi omalle rivilleen tyhjien rivien ympäröimänä. Esimerkiksi: `<callout type="info">Sisältö</callout>`.

</accordion-item>

<accordion-item summary="Voiko komponentteja laajentaa?">

Kyllä. Lisää uusi tagi `src/MarkdownRenderer.elm` -tiedostoon ja toteuta vastaava komponentti `src/Component/` -hakemistoon.

</accordion-item>

</accordion>

---

## Tilastot (Stats)

Avainluvut ruudukossa.

<stat-grid>

<stat label="Jäseniä" value="250+" change="+15 %"></stat>

<stat label="Tapahtumia" value="12" change="+3"></stat>

<stat label="Komponentteja" value="33"></stat>

<stat label="Suunnittelutokeneja" value="80+"></stat>

</stat-grid>

---

## Aikajana (Timeline)

Tapahtumakulku päivämäärien ja kuvausten kanssa.

<timeline>

<timeline-item date="2024-01" title="Projektin aloitus" icon="zap">

Suunnittelujärjestelmän kehitys alkoi.

</timeline-item>

<timeline-item date="2024-06" title="Ensimmäinen julkaisu" icon="check-circle">

Brändivärit, typografia ja peruskomponentit valmistuivat.

</timeline-item>

<timeline-item date="2025-01" title="Komponenttikirjasto" icon="star">

33 komponenttia toteutettuna ja dokumentoituna.

</timeline-item>

<timeline-item date="2025-10" title="Design Tokens 2025.10" icon="flag">

W3C Design Tokens -standardin mukainen tokenijärjestelmä.

</timeline-item>

</timeline>

---

## Ominaisuusruudukko (Feature Grid)

<feature-grid columns="3">

<feature title="Tyyppiturvallinen" icon="✓">

Jokainen reitti, sivu ja komponentti tarkastetaan käännösaikana. Ei ajonaikaisia yllätyksiä.

</feature>

<feature title="Markdown + komponentit" icon="◆">

Kirjoita Markdownia ja upota rikkaita käyttöliittymäkomponentteja yksinkertaisilla HTML-tageilla.

</feature>

<feature title="Suunnittelutokenit" icon="●">

Värit, typografia ja välistys määritelty keskitetysti TOML-tiedostoissa ja generoitu tyypitettyinä Elm-moduuleina.

</feature>

</feature-grid>

---

## Merkit (Badge)

Pienet tilamerkinnät tekstin sisällä: <badge color="blue">Uusi</badge> <badge color="green">Valmis</badge> <badge color="yellow">Keskeneräinen</badge> <badge color="red">Virhe</badge> <badge color="gray">Oletusarvo</badge>

---

## Painikkeet (Button)

Kolme painikkeen varianttia:

<button-link href="#" variant="primary">Primary</button-link>
<button-link href="#" variant="secondary">Secondary</button-link>
<button-link href="#" variant="ghost">Ghost</button-link>

---

## Hinnoittelutaulukko (Pricing)

<pricing-table>

<pricing-tier name="Perus" price="0 €" period="vuosi">

- Julkiset tapahtumat
- Discord-yhteisö
- Uutiskirje

</pricing-tier>

<pricing-tier name="Jäsen" price="10 €" period="vuosi">

- Kaikki perusedut
- Jäsenkortti ja -alennukset
- Äänioikeus yhdistyskokouksissa
- Pääsy jäsenfoorumille

</pricing-tier>

<pricing-tier name="Kannatusjäsen" price="25 €" period="vuosi">

- Kaikki jäsenedut
- Tuki yhdistyksen toiminnalle
- Nimi kiitossivulla

</pricing-tier>

</pricing-table>

---

## Osionotsikko (SectionHeader)

Käytä `<section-header>` ja `<section-subheader>` -tageja rakenteellisiin väliotsikkoihin. `description`-attribuutti on valinnainen.

<section-header title="Pääosion otsikko" description="Lyhyt kuvaus osiosta lukijalle."/>

<section-subheader title="Alaotsikko" description="Lisätietoa tästä kohdasta."/>

---

## Latauskehä (Spinner)

Käytä `<spinner>` -tagia lataustiloissa. `size`-attribuutti voi olla `small`, `medium` (oletus) tai `large`. `label`-attribuutti on ruudunlukijoille tarkoitettu teksti.

<spinner size="small" label="Ladataan..."/>

<spinner size="medium" label="Odota hetki"/>

<spinner size="large" label="Valmistellaan sisältöä"/>

---

## Edistymispalkki (Progress)

Käytä `<progress-bar>` -tagia edistymisen tai täyttöasteen esittämiseen. `value` ja `max` ovat kokonaislukuja. `label` ja `color` ovat valinnaisia. `color`-attribuutti voi olla `brand` (oletus), `success`, `warning`, `danger` tai `info`.

<progress-bar value="75" max="100" label="Rekisteröityminen" color="brand"/>

<progress-bar value="40" max="100" color="success"/>

<progress-bar value="90" max="100" label="Levytila käytetty" color="danger"/>

---

## Ilmoituspopup (Toast)

Käytä `<toast>` -tagia lyhyisiin tilapäisiin ilmoituksiin. `variant`-attribuutti voi olla `default` (oletus), `success`, `warning` tai `danger`. `title` on pakollinen, `body` valinnainen.

<toast variant="success" title="Tallennettu" body="Muutokset tallennettu onnistuneesti."/>

<toast variant="warning" title="Huomio" body="Muista tallentaa muutokset ennen sulkemista."/>

<toast variant="danger" title="Virhe" body="Toimintoa ei voitu suorittaa. Yritä uudelleen."/>

<toast title="Uusi viesti" body="Sinulle on saapunut yksi uusi viesti."/>

---

## Tunniste (Tag)

Käytä `<tag>` -tagia kategoria- tai tilatunnisteille. `label`-attribuutti on pakollinen.

<tag label="Elm"/> <tag label="Tailwind CSS"/> <tag label="Design Tokens"/>

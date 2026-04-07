---
title: "Komponentit"
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

Käytä `<callout type="…">` -tagia huomioilmoituksiin. `type`-attribuutti voi olla `info`, `success`, `warning` tai `error`.

<tab-group name="callout-fi">

<preview>

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

</preview>

<example>

```html
&lt;callout type="info"&gt;Tiedoteviesti tähän.&lt;/callout&gt;

&lt;callout type="success"&gt;Onnistumisviesti tähän.&lt;/callout&gt;

&lt;callout type="warning"&gt;Varoitusviesti tähän.&lt;/callout&gt;

&lt;callout type="error"&gt;Virheviesti tähän.&lt;/callout&gt;
```

</example>

</tab-group>

---

## Hero-osio

Käytä `<hero title="…" subtitle="…">` -tagia suuren pääosion luomiseen. Sijoita `<button-link href="…" variant="…" label="…"/>` -tagit sisälle toimintopainikkeiden paikaksi.

<tab-group name="hero-fi">

<preview>

<hero title="Rakenna kauniita sivustoja" subtitle="Elm-pages-pohjainen staattinen sivugeneraattori suunnittelutokeneilla.">

<button-link href="#" variant="primary" label="Pääpainike"/>
<button-link href="#" variant="secondary" label="Toissijainen"/>
<button-link href="#" variant="ghost" label="Ghost"/>

</hero>

</preview>

<example>

```html
&lt;hero title="Otsikko tähän" subtitle="Alaotsikko tähän."&gt;

&lt;button-link href="/aloita" variant="primary" label="Aloita"/&gt;
&lt;button-link href="/lisatietoa" variant="secondary" label="Lue lisää"/&gt;

&lt;/hero&gt;
```

</example>

</tab-group>

---

## Painikkeet (Button Link)

Käytä `<button-link href="…" variant="…" label="…"/>` -tagia tyyliteltyihin linkkipainikkeisiin. `variant`-attribuutti voi olla `primary`, `secondary` tai `ghost`.

<tab-group name="button-link-fi">

<preview>

<button-link href="#" variant="primary" label="Primary"/>
<button-link href="#" variant="secondary" label="Secondary"/>
<button-link href="#" variant="ghost" label="Ghost"/>

</preview>

<example>

```html
&lt;button-link href="/polku" variant="primary" label="Primary"/&gt;
&lt;button-link href="/polku" variant="secondary" label="Secondary"/&gt;
&lt;button-link href="/polku" variant="ghost" label="Ghost"/&gt;
```

</example>

</tab-group>

---

## Kortit (Card)

Käytä `<card title="…">` -tagia sisältökortteihin. `title`-attribuutti on valinnainen.

<tab-group name="card-fi">

<preview>

<card title="Otsikollinen kortti">

Tämä on kortin sisältö. Kortit sopivat yksittäisten kokonaisuuksien esittämiseen, kuten artikkelien, palveluiden tai tuotteiden tiivistelmiin.

</card>

<card>

Kortti ilman otsikkoa. Käytä kun sisältö puhuu puolestaan.

</card>

</preview>

<example>

```html
&lt;card title="Otsikko"&gt;
Kortin sisältö tähän.
&lt;/card&gt;

&lt;card&gt;
Kortti ilman otsikkoa.
&lt;/card&gt;
```

</example>

</tab-group>

---

## Haitari (Accordion)

Käytä `<accordion>` ja `<accordion-item summary="…">` -tageja laajennettaviin osioihin. Käyttää selaimen natiivia `<details>`-elementtiä — ei JavaScriptia.

<tab-group name="accordion-fi">

<preview>

<accordion>

<accordion-item summary="Mikä on elm-pages?">

elm-pages on staattinen sivugeneraattori, joka käyttää Elm-ohjelmointikieltä. Jokainen sivu tyyppitarkastetaan käännösaikana.

</accordion-item>

<accordion-item summary="Miten komponentteja käytetään Markdownissa?">

Lisää HTML-tagi omalle rivilleen tyhjien rivien ympäröimänä. Esimerkiksi: `&lt;callout type="info"&gt;Sisältö&lt;/callout&gt;`.

</accordion-item>

<accordion-item summary="Voiko komponentteja laajentaa?">

Kyllä. Lisää uusi tagi `src/MarkdownRenderer.elm` -tiedostoon ja toteuta vastaava komponentti `src/Component/` -hakemistoon.

</accordion-item>

</accordion>

</preview>

<example>

```html
&lt;accordion&gt;

&lt;accordion-item summary="Kysymys tähän?"&gt;
Vastaus tähän.
&lt;/accordion-item&gt;

&lt;accordion-item summary="Toinen kysymys?"&gt;
Toinen vastaus.
&lt;/accordion-item&gt;

&lt;/accordion&gt;
```

</example>

</tab-group>

---

## Tilastot (Stat Grid)

Käytä `<stat-grid>` -tagia `<stat>`-elementtien ryhmittelyyn. Jokainen `<stat>` vaatii `label`- ja `value`-attribuutit. `change` on valinnainen.

<tab-group name="stat-grid-fi">

<preview>

<stat-grid>

<stat label="Jäseniä" value="250+" change="+15 %"></stat>

<stat label="Tapahtumia" value="12" change="+3"></stat>

<stat label="Komponentteja" value="33"></stat>

<stat label="Suunnittelutokeneja" value="80+"></stat>

</stat-grid>

</preview>

<example>

```html
&lt;stat-grid&gt;

&lt;stat label="Jäseniä" value="250+" change="+15 %"&gt;&lt;/stat&gt;
&lt;stat label="Tapahtumia" value="12"&gt;&lt;/stat&gt;

&lt;/stat-grid&gt;
```

</example>

</tab-group>

---

## Aikajana (Timeline)

Käytä `<timeline>` -tagia `<timeline-item date="…" title="…">` -elementtien ryhmittelyyn. Valinnainen `icon`-attribuutti hyväksyy Feather-ikonin nimen (`calendar`, `check`, `clock`, `flag`, `star`, `zap` jne.).

<tab-group name="timeline-fi">

<preview>

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

</preview>

<example>

```html
&lt;timeline&gt;

&lt;timeline-item date="Maaliskuu 2026" title="Välietappi" icon="check"&gt;
Kuvaus tapahtumasta.
&lt;/timeline-item&gt;

&lt;timeline-item date="Tammikuu 2026" title="Aiempi vaihe"&gt;
Toinen kuvaus.
&lt;/timeline-item&gt;

&lt;/timeline&gt;
```

</example>

</tab-group>

---

## Ominaisuusruudukko (Feature Grid)

Käytä `<feature-grid columns="2|3|4">` -tagia `<feature>`-elementtien ryhmittelyyn. `icon`-attribuutti hyväksyy Feather-ikonin nimen (`zap`, `check`, `globe`, `edit`, `layers`, `git-branch`, `rss`, `calendar`, `shield`, `lock`, `code`, `cpu`, `package`, `trending-up` jne.). Valinnainen `href`-attribuutti tekee kortista linkin.

<tab-group name="feature-grid-fi">

<preview>

<feature-grid columns="3">

<feature title="Tyyppiturvallinen" icon="check" href="/komponentit">

Jokainen reitti, sivu ja komponentti tarkastetaan käännösaikana. Ei ajonaikaisia yllätyksiä.

</feature>

<feature title="Markdown + komponentit" icon="edit">

Kirjoita Markdownia ja upota rikkaita käyttöliittymäkomponentteja yksinkertaisilla HTML-tageilla.

</feature>

<feature title="Suunnittelutokenit" icon="layers">

Värit, typografia ja välistys määritelty keskitetysti TOML-tiedostoissa ja generoitu tyypitettyinä Elm-moduuleina.

</feature>

</feature-grid>

</preview>

<example>

```html
&lt;feature-grid columns="3"&gt;

&lt;feature title="Nopea" icon="zap" href="/docs/nopeus"&gt;
Kuvaus ominaisuudesta tähän.
&lt;/feature&gt;

&lt;feature title="Turvallinen" icon="shield"&gt;
Toinen ominaisuus ilman linkkiä.
&lt;/feature&gt;

&lt;/feature-grid&gt;
```

</example>

</tab-group>

---

## Merkit (Badge)

Käytä `<badge color="…" label="…"/>` -tagia tekstin sisäisiin tilamerkintöihin. `color`-attribuutti voi olla `gray`, `blue`, `green`, `yellow`, `red`, `purple` tai `indigo`.

<tab-group name="badge-fi">

<preview>

<badge color="indigo" label="Uusi"/> <badge color="green" label="Valmis"/> <badge color="yellow" label="Beta"/> <badge color="red" label="Poistunut"/> <badge color="gray" label="Luonnos"/>

</preview>

<example>

```html
&lt;badge color="indigo" label="Uusi"/&gt;
&lt;badge color="green" label="Valmis"/&gt;
&lt;badge color="yellow" label="Beta"/&gt;
&lt;badge color="red" label="Poistunut"/&gt;
&lt;badge color="gray" label="Luonnos"/&gt;
```

</example>

</tab-group>

---

## Hinnoittelutaulukko (Pricing)

Käytä `<pricing-table>` -tagia `<pricing-tier name="…" price="…">` -korttien ryhmittelyyn. `period`-attribuutti on valinnainen.

<tab-group name="pricing-fi">

<preview>

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

</preview>

<example>

```html
&lt;pricing-table&gt;

&lt;pricing-tier name="Perus" price="0 €" period="vuosi"&gt;
- Etu yksi
- Etu kaksi
&lt;/pricing-tier&gt;

&lt;pricing-tier name="Pro" price="10 €" period="vuosi"&gt;
- Kaikki perusedut
- Lisäominaisuus
&lt;/pricing-tier&gt;

&lt;/pricing-table&gt;
```

</example>

</tab-group>

---

## Osionotsikko (Section Header)

Käytä `<section-header title="…">` -tagia näyttäviin keskitettyihin väliotsikkoihin ja `<section-subheader title="…">` -tagia pienempiin alaotsikkoihin. Molemmat hyväksyvät valinnaisen `description`-attribuutin.

<tab-group name="section-header-fi">

<preview>

<section-header title="Komponenttimme" description="Valikoima käyttöliittymän rakennuspalikoita, jotka voi upottaa mihin tahansa Markdown-sivuun."/>

<section-subheader title="Aloitusohje" description="Kaikki tarvittava on jo valmiina — aloita vain tagien kirjoittaminen."/>

</preview>

<example>

```html
&lt;section-header title="Osion otsikko" description="Valinnainen kuvaus."/&gt;

&lt;section-subheader title="Alaotsikko" description="Valinnainen kuvaus."/&gt;
```

</example>

</tab-group>

---

## Latauskehä (Spinner)

Käytä `<spinner/>` -tagia lataustiloissa. `size`-attribuutti voi olla `small`, `medium` (oletus) tai `large`. `label`-attribuutti on ruudunlukijoille tarkoitettu teksti.

<tab-group name="spinner-fi">

<preview>

Pieni

<spinner size="small" label="Ladataan..."/>

Keskikokoinen

<spinner size="medium" label="Odota hetki"/>

Suuri

<spinner size="large" label="Valmistellaan sisältöä"/>

</preview>

<example>

```html
&lt;spinner size="small" label="Ladataan..."/&gt;
&lt;spinner size="medium" label="Odota hetki"/&gt;
&lt;spinner size="large" label="Valmistellaan sisältöä"/&gt;
```

</example>

</tab-group>

---

## Edistymispalkki (Progress Bar)

Käytä `<progress-bar value="…" max="…">` -tagia edistymisen esittämiseen. `value` ja `max` ovat kokonaislukuja. `label` ja `color` ovat valinnaisia. `color`-attribuutti voi olla `brand` (oletus), `success`, `warning`, `danger` tai `info`.

<tab-group name="progress-bar-fi">

<preview>

<progress-bar value="75" max="100" label="Rekisteröityminen" color="brand"/>

<progress-bar value="40" max="100" label="Tallennustila" color="success"/>

<progress-bar value="90" max="100" label="Levytila käytetty" color="danger"/>

</preview>

<example>

```html
&lt;progress-bar value="75" max="100" label="Lataus" color="brand"/&gt;
&lt;progress-bar value="80" max="100" label="Tallennustila" color="success"/&gt;
&lt;progress-bar value="60" max="100" label="Jonon pituus" color="warning"/&gt;
```

</example>

</tab-group>

---

## Ilmoituspopup (Toast)

Käytä `<toast title="…">` -tagia lyhyisiin tilapäisiin ilmoituksiin. `variant`-attribuutti voi olla `default` (oletus), `success`, `warning` tai `danger`. `body` on valinnainen lisäteksti.

<tab-group name="toast-fi">

<preview>

<toast title="Uusi viesti" body="Sinulle on saapunut yksi uusi viesti." variant="default"/>

<toast variant="success" title="Tallennettu" body="Muutokset tallennettu onnistuneesti."/>

<toast variant="warning" title="Huomio" body="Muista tallentaa muutokset ennen sulkemista."/>

<toast variant="danger" title="Virhe" body="Toimintoa ei voitu suorittaa. Yritä uudelleen."/>

</preview>

<example>

```html
&lt;toast title="Tallennettu" body="Lisäteksti tähän." variant="default"/&gt;
&lt;toast title="Onnistui" body="Toiminto valmis." variant="success"/&gt;
&lt;toast title="Varoitus" body="Tarkista syöte." variant="warning"/&gt;
&lt;toast title="Virhe" body="Jokin meni pieleen." variant="danger"/&gt;
```

</example>

</tab-group>

---

## Tunniste (Tag)

Käytä `<tag label="…"/>` -tagia kategoria- tai tilatunnisteille.

<tab-group name="tag-fi">

<preview>

Tunnisteet: <tag label="Elm"/> <tag label="Tailwind CSS"/> <tag label="Design Tokens"/> <tag label="Avoin lähdekoodi"/>

</preview>

<example>

```html
&lt;tag label="Elm"/&gt;
&lt;tag label="Tailwind CSS"/&gt;
&lt;tag label="Avoin lähdekoodi"/&gt;
```

</example>

</tab-group>

---

## Tietopaneeli (Info Panel)

Käytä `<info-panel>` -tagia kontekstuaalisiin huomioruutuihin. `color`-attribuutti voi olla `amber` (oletus), `blue`, `green` tai `red`. Valinnainen `title` näytetään lihavoituna otsikkona.

<tab-group name="info-panel-fi">

<preview>

<info-panel color="amber" title="Ennen kuin aloitat">

Varmista, että olet tallentanut kaikki muutokset ennen julkaisua.

</info-panel>

<info-panel color="blue" title="Tiesitkö?">

Voit käyttää kaikkia Markdown-muotoiluja — **lihavointi**, `koodikatkelma` ja listat toimivat paneelin sisällä.

</info-panel>

<info-panel color="green" title="Kaikki kunnossa">

Buildausputki toimii normaalisti. Julkaisut valmistuvat alle kymmenessä sekunnissa.

</info-panel>

<info-panel color="red" title="Toimenpide vaaditaan">

API-avaimesi vanhenee kolmen päivän kuluttua. Uusi se asetuksissa.

</info-panel>

</preview>

<example>

```html
&lt;info-panel color="amber" title="Ennen kuin aloitat"&gt;
Tärkeä huomio lukijalle.
&lt;/info-panel&gt;

&lt;info-panel color="blue"&gt;
Huomio ilman otsikkoa.
&lt;/info-panel&gt;
```

</example>

</tab-group>

---

## Kuva ja teksti (Image + Text)

Käytä `<with-image src="…">` -tagia kuvan ja tekstisisällön rinnakkaisasetteluun. `side`-attribuutti määrittää kuvan puolen: `right` (oletus) tai `left`. `alt`-attribuutti on saavutettavuusselite.

<tab-group name="with-image-fi">

<preview>

<with-image src="/logo-blue.svg" alt="Logo vaalealla taustalla" side="right">

### Kuva oikealla

Yhdistä kuva ja teksti kaksisarakkeiseen asetteluun ilman CSS-koodia. Ruudukko tiivistyy yksisarakkeiseksi pienillä näytöillä.

</with-image>

<with-image src="/logo-blue.svg" alt="Logo vaalealla taustalla" side="left">

### Kuva vasemmalla

Vaihda kuvan puoli `side="left"` -attribuutilla. Vuorottelemalla puolia saat sivulle visuaalista rytmiä.

</with-image>

</preview>

<example>

```html
&lt;with-image src="/kuvat/kuvakaappaus.png" alt="Kuvakaappaus" side="right"&gt;

### Otsikko

Kuvausteksti tähän.

&lt;/with-image&gt;
```

</example>

</tab-group>

---

## Resurssigalleria (Asset Gallery)

Käytä `<asset-gallery source="…">` -tagia logovarojen gallerianäkymään. `source`-attribuutti voi olla `logos-square`, `logos-square-full` tai `logos-horizontal`. Valinnaiset `title` ja `description` näytetään ruudukon yläpuolella.

<tab-group name="asset-gallery-fi">

<preview>

<asset-gallery source="logos-square" title="Neliölogot" description="Kompaktit neliöversiot avatareille, faviconeille ja sovelluskuvakkeille."/>

</preview>

<example>

```html
&lt;asset-gallery source="logos-square" title="Neliölogot" description="Valinnainen kuvaus."/&gt;

&lt;asset-gallery source="logos-square-full"/&gt;

&lt;asset-gallery source="logos-horizontal" title="Vaakalogot"/&gt;
```

</example>

</tab-group>

---

## Väriruudukko (Color Grid)

Käytä `<color-grid source="…">` -tagia väripalettien esittämiseen. `source`-attribuutti voi olla `brand`, `skin-tones` tai `rainbow`. Valinnaiset `title` ja `description` näytetään ruudukon yläpuolella.

<tab-group name="color-grid-fi">

<preview>

<color-grid source="brand" title="Brändivärit" description="Ensisijainen väripaletti, jota käytetään kaikissa logovarianteissa ja käyttöliittymäkomponenteissa."/>

</preview>

<example>

```html
&lt;color-grid source="brand" title="Brändivärit" description="Valinnainen kuvaus."/&gt;

&lt;color-grid source="skin-tones" title="Ihonsävyt"/&gt;

&lt;color-grid source="rainbow" title="Sateenkaarivärjäys"/&gt;
```

</example>

</tab-group>

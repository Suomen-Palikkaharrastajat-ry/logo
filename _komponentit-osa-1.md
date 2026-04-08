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


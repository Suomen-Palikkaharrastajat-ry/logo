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


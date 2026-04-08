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

Käytä `<with-image src="…">` -tagia kuvan ja tekstisisällön rinnakkaisasetteluun. `side`-attribuutti määrittää kuvan puolen: `right` (oletus) tai `left`. `alt`-attribuutti on saavutettavuusselite. Valinnainen `caption`-attribuutti lisää kuvatekstin kuvan alle. Valinnainen `maxwidth`-attribuutti rajoittaa komponentin leveyttä — hyväksyy arvot `lg`, `2xl`, `3xl` tai `4xl`.

<tab-group name="with-image-fi">

<preview>

<with-image src="/logo-blue.svg" alt="Logo vaalealla taustalla" side="right">

### Kuva oikealla

Yhdistä kuva ja teksti kaksisarakkeiseen asetteluun ilman CSS-koodia. Ruudukko tiivistyy yksisarakkeiseksi pienillä näytöillä.

</with-image>

<with-image src="/logo-blue.svg" alt="Logo vaalealla taustalla" side="left" caption="Logo vaalealla taustalla." maxwidth="3xl">

### Kuva vasemmalla, kuvatekstillä ja leveysrajoituksella

Käytä `caption`-attribuuttia lisätäksesi selitteen kuvan alle. Käytä `maxwidth`-attribuuttia, kun haluat estää asettelua venymästä täyteen leveyteen — hyödyllinen pystykuville tai tiiviimpiin sommitelmiin.

</with-image>

</preview>

<example>

```html
&lt;with-image src="/kuvat/kuvakaappaus.png" alt="Kuvakaappaus" side="right"&gt;

### Otsikko

Kuvausteksti tähän.

&lt;/with-image&gt;

&lt;with-image src="/kuvat/valokuva.jpg" alt="Valokuva" side="left"
  caption="Valinnainen kuvateksti kuvan alla."
  maxwidth="3xl"&gt;

### Leveysrajoitettu

Sisältö tähän.

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

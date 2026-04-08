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

Käytä `<info-panel>` -tagia kontekstuaalisiin huomioruutuihin. `color`-attribuutti voi olla `amber` (oletus), `blue`, `green` tai `red`. Valinnainen `title` näytetään lihavoituna otsikkona. Valinnainen `icon`-attribuutti hyväksyy Feather-ikonin nimen ja näyttää sen otsikon vieressä.

<tab-group name="info-panel-fi">

<preview>

<info-panel color="amber" title="Ennen kuin aloitat" icon="alert-triangle">

Varmista, että olet tallentanut kaikki muutokset ennen julkaisua.

</info-panel>

<info-panel color="blue" title="Tiesitkö?" icon="info">

Voit käyttää kaikkia Markdown-muotoiluja — **lihavointi**, `koodikatkelma` ja listat toimivat paneelin sisällä.

</info-panel>

<info-panel color="green" title="Kaikki kunnossa" icon="check-circle">

Buildausputki toimii normaalisti. Julkaisut valmistuvat alle kymmenessä sekunnissa.

</info-panel>

<info-panel color="red" title="Toimenpide vaaditaan" icon="x-circle">

API-avaimesi vanhenee kolmen päivän kuluttua. Uusi se asetuksissa.

</info-panel>

</preview>

<example>

```html
&lt;info-panel color="amber" title="Ennen kuin aloitat" icon="alert-triangle"&gt;
Tärkeä huomio lukijalle.
&lt;/info-panel&gt;

&lt;info-panel color="blue" title="Tiesitkö?" icon="info"&gt;
Huomio ikonilla ja otsikolla.
&lt;/info-panel&gt;

&lt;info-panel color="green"&gt;
Paneeli ilman otsikkoa tai ikonia.
&lt;/info-panel&gt;
```

</example>

</tab-group>

---

## Kuva ja teksti (Image + Text)

Käytä `<with-image src="…">` -tagia kuvan ja tekstisisällön rinnakkaisasetteluun. `side`-attribuutti määrittää kuvan puolen: `right` (oletus) tai `left`. `alt`-attribuutti on saavutettavuusselite. Valinnainen `caption`-attribuutti lisää kuvatekstin kuvan alle. Valinnainen `maxwidth`-attribuutti rajoittaa komponentin leveyttä — hyväksyy arvot `lg`, `2xl`, `3xl` tai `4xl`.

<tab-group name="with-image-fi">

<preview>

<with-image src="/logo/square/svg/square-smile.svg" alt="Neliölogo" side="right">

### Kuva oikealla

Yhdistä kuva ja teksti kaksisarakkeiseen asetteluun ilman CSS-koodia. Ruudukko tiivistyy yksisarakkeiseksi pienillä näytöillä.

</with-image>

<with-image src="/logo/square/svg/square-smile.svg" alt="Neliölogo" side="left" caption="Neliölogon variantti." maxwidth="3xl">

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

## Galleria

Käytä `<gallery>`-containeria ja sen sisällä `<gallery-item>`-elementtejä. Näin jokainen kortti määritellään eksplisiittisesti ilman `source`-taikamerkkijonoja.

<tab-group name="gallery-fi">

<preview>

<gallery title="Neliölogot" description="Kompaktit neliöversiot avatareille, faviconeille ja sovelluskuvakkeille." columns="4">
  <gallery-item id="square-smile" description="Hymyilevä ilme" highlight="true" svg="/logo/square/svg/square-smile.svg" png="/logo/square/png/square-smile.png" webp="/logo/square/png/square-smile.webp"/>
  <gallery-item id="square-animated" description="Animoitu logo" animated="true" webp="/logo/square/png/square-animated.webp" gif="/logo/square/png/square-animated.gif"/>
</gallery>

<gallery title="Vaakalogot" description="Leveät versiot otsikoihin ja bannereihin." columns="2-wide">
  <gallery-item id="horizontal-full" description="Logo yhdistyksen nimellä, vaalea teema" with-text="true" svg="/logo/horizontal/svg/horizontal-full.svg" png="/logo/horizontal/png/horizontal-full.png" webp="/logo/horizontal/png/horizontal-full.webp"/>
  <gallery-item id="horizontal-full-dark" description="Logo nimitekstillä, tumma teema" theme="dark" with-text="true" svg="/logo/horizontal/svg/horizontal-full-dark.svg" png="/logo/horizontal/png/horizontal-full-dark.png" webp="/logo/horizontal/png/horizontal-full-dark.webp"/>
</gallery>

</preview>

<example>

```html
&lt;gallery title="Neliölogot" description="Valinnainen kuvaus." columns="4"&gt;
  &lt;gallery-item
    id="square-smile"
    description="Hymyilevä ilme"
    highlight="true"
    svg="/logo/square/svg/square-smile.svg"
    png="/logo/square/png/square-smile.png"
    webp="/logo/square/png/square-smile.webp"/&gt;
&lt;/gallery&gt;

&lt;gallery title="Vaakalogot" columns="2-wide"&gt;
  &lt;gallery-item
    id="horizontal-full-dark"
    description="Logo nimitekstillä, tumma teema"
    theme="dark"
    with-text="true"
    svg="/logo/horizontal/svg/horizontal-full-dark.svg"
    png="/logo/horizontal/png/horizontal-full-dark.png"
    webp="/logo/horizontal/png/horizontal-full-dark.webp"/&gt;
&lt;/gallery&gt;
```

</example>

</tab-group>

---

## Väriruudukko (Color Grid)

Käytä `<color-grid>`-containeria ja sen sisällä `<color-grid-item>`-elementtejä. Valinnaiset `description` ja `usage`-tagit rikastavat yksittäistä värikorttia.

<tab-group name="color-grid-fi">

<preview>

<color-grid title="Brändivärit" description="Ensisijainen väripaletti, jota käytetään kaikissa logovarianteissa ja käyttöliittymäkomponenteissa." columns="4">
  <color-grid-item name="Yellow" hex="#FAC80A" description="Pääaksenttiväri painikkeisiin." usage="primary brand,accent"/>
  <color-grid-item name="Black" hex="#05131D" description="Otsikot, leipäteksti ja tumma tausta." usage="text,dark background"/>
</color-grid>

<color-grid title="Ihonsävyt" description="Inklusiivinen ihonsäväpaletti kuvitetuille hahmoille." columns="4">
  <color-grid-item name="Light Nougat" hex="#F6D7B3" description="Vaalea ihonsävy."/>
  <color-grid-item name="Dark Nougat" hex="#AD6140" description="Tumma ihonsävy."/>
</color-grid>

</preview>

<example>

```html
&lt;color-grid title="Brändivärit" description="Valinnainen kuvaus." columns="4"&gt;
  &lt;color-grid-item
    name="Yellow"
    hex="#FAC80A"
    description="Pääaksenttiväri painikkeisiin."
    usage="primary brand,accent"/&gt;
&lt;/color-grid&gt;

&lt;color-grid title="Ihonsävyt" columns="4"&gt;
  &lt;color-grid-item name="Light Nougat" hex="#F6D7B3"/&gt;
  &lt;color-grid-item name="Dark Nougat" hex="#AD6140"/&gt;
&lt;/color-grid&gt;
```

</example>

</tab-group>

---
title: "Saavutettavuus – Suomen Palikkaharrastajat ry"
description: "WCAG 2.1 AA -ohjeet: kontrastisuhteet, värisokeustuki, fokusindikaattorit ja ARIA-nimeäminen."
slug: saavutettavuus
published: true
nav: true
navTitle: "Saavutettavuus"
order: 4
---

# Saavutettavuus

<callout type="info">

Suunnittelujärjestelmän tavoitetaso on **WCAG 2.1 AA**. Kaikki komponentit, värit ja typografia on suunniteltu täyttämään tämä vaatimus.

</callout>

---

## Ohita-navigaatio-linkki

Jokaisella sivulla on piilotettu "Siirry pääsisältöön" -linkki, joka tulee näkyviin Tab-näppäimellä. Se ohjaa fokuksen suoraan `<main id="main-content">`-elementtiin.

```html
<a href="#main-content" class="sr-only focus:not-sr-only ...">
  Siirry pääsisältöön
</a>
```

---

## Kontrastisuhteet

| Väri | Koodi | Suhde valkoisella | Suhde mustalla | Huomio |
|---|---|---|---|---|
| LEGO Black | `#05131D` | 17.3:1 ★ | — | AAA |
| White | `#FFFFFF` | — | 17.3:1 ★ | AAA |
| Red | `#C91A09` | 5.4:1 | 3.2:1 | AA (ei pienelle tekstille mustalla) |
| Yellow | `#FAC80A` | 1.5:1 | 11.5:1 | Vain tummalla taustalla |
| Light Nougat | `#F6D7B3` | 1.4:1 | 12.2:1 | Vain tummalla taustalla |
| Medium Nougat | `#D09168` | 2.6:1 | 6.6:1 | Isoille elementeille |
| Dark Nougat | `#AD6140` | 4.2:1 | 4.1:1 | AA raja-arvo |

★ = Ylittää AAA-tason (7:1)

---

## Semanttiset kontrastiparit

| Teksti | Tausta | Suhde | Taso | Käyttö |
|---|---|---|---|---|
| `text-primary` | `bg-page` | 17.3:1 | AAA | Otsikot ja leipäteksti |
| `text-primary` | `bg-subtle` | 16.8:1 | AAA | Kortit ja korostukset |
| `text-muted` | `bg-page` | 4.6:1 | AA | Toissijainen teksti |
| `text-muted` | `bg-subtle` | 4.5:1 | AA | Korttien kuvaukset |
| `text-subtle` | `bg-page` | 3.0:1 | — | Vain isot elementit |
| `brand-red` | `bg-page` | 5.4:1 | AA | Virheviestit |
| `brand` (black) | `bg-accent` (yellow) | 11.5:1 | AAA | CTA-napit |

---

## Tumman pinnan parit

| Teksti | Koodi | Suhde | Taso | Huomio |
|---|---|---|---|---|
| `text-on-dark` (white) | `#FFFFFF` | 17.3:1 | AAA | Kaikki teksti tummalla pinnalla |
| `brand-yellow` | `#FAC80A` | 11.5:1 | AAA | Korostukset, linkit, CTA |
| `brand-red` | `#C91A09` | 4.2:1 | AA | Varoitukset (ei pienelle tekstille) |
| gray-400 | `#9CA3AF` | 3.9:1 | — | Vain isoille elementeille |
| gray-500 / `text-muted` | `#6B7280` | 2.8:1 | — | **EI sallittu** tummalla pinnalla |

<callout type="error">

Älä koskaan käytä `text-muted` tai `text-subtle` tummalla taustalla — kontrasti ei riitä.

</callout>

---

## Värisokeustuki

<callout type="warning">

**Älä luota pelkkään väriin** — käytä aina myös tekstiä, kuvaketta tai kuviota värin lisäksi ilmaisemaan merkitystä.

</callout>

- **Deuteranopia** (punavihersokeus): Salmon ja Medium Green voivat sekoittua — käytä aina tekstimerkkiä värin ohella
- **Turvallinen pari**: Musta + keltainen (`#05131D` + `#FAC80A`) erottuu kaikissa värisokeustyypeissä

---

## Liike ja animaatiot

- `prefers-reduced-motion` on **pakollinen** kaikille animaatioille (toteutettu `style.css`-tiedostossa)
- Animoitu logo: käytä GIF-muotoa vain kun `prefers-reduced-motion: no-preference`
- Kestotokenit: `fast` 150 ms (hover), `base` 300 ms (avaukset), `slow` 500 ms (sivusiirtymät)

---

## Logon vaihtoehtoteksti

| Käyttötilanne | `alt`-teksti | Esimerkki |
|---|---|---|
| Päälogo navigaatiossa | Organisaation nimi | `alt="Suomen Palikkaharrastajat ry"` |
| Kuvituskäyttö | Kuvaileva teksti | `alt="Hymyilevä minifiguuri — logo"` |
| Koristeellinen | Tyhjä + piilotettu | `alt="" aria-hidden="true"` |

```html
<!-- Koristeellinen logo -->
<img src="/logo/square/svg/square-smile-full-dark-bold.svg"
     alt=""
     aria-hidden="true">
```

---

## Kohdistusindikaattorit (Focus)

<callout type="info">

**Käytä aina `focus-visible`**, ei `focus`:
- `focus-visible:ring-2 focus-visible:ring-brand` — näppäimistöfokus
- Ei näy hiirellä klikattaessa
- Fokusrenkaan kontrasti taustan kanssa vähintään **3:1**

</callout>

Älä koskaan poista `outline` ilman vaihtoehtoista fokusindikaattoria.

---

## Saavutettava nimeäminen (ARIA)

### aria-label

`CloseButton` ja `Spinner` vaativat `label : String` -parametrin (ei `Html msg`), jotta `aria-label` on aina läsnä ruudunlukijoille.

```elm
CloseButton.view { onClick = DismissAlert, label = "Sulje ilmoitus" }
Spinner.view { size = Spinner.Medium, label = "Ladataan sisältöä" }
```

### aria-haspopup + aria-expanded

`Dropdown`-komponentti hallitsee automaattisesti `aria-haspopup` ja `aria-expanded` -attribuutit `isOpen`-tilan perusteella. Escape-näppäin sulkee valikon.

### aria-controls + aria-labelledby

`Tabs`-komponentti generoi automaattiset ID:t (`tab-0`, `panel-0`, jne.) ja hallitsee `aria-controls` + `aria-labelledby` -yhteydet. Nuolinäppäimet navigoivat välilehtien välillä.

<callout type="warning">

**Miksi `String`-nimiöt eikä `Html msg`?** Ruudunlukijat eivät pysty lukemaan `Html msg` -sisältöä `aria-label`-attribuutista. `String` takaa, että saavutettava nimi on aina olemassa.

</callout>

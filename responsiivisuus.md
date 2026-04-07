---
title: "Responsiivisuus – Suomen Palikkaharrastajat ry"
description: "Mobiililähtöinen suunnittelu, murtopisteet, ruudukkomallit ja asetteluperiaatteet."
slug: responsiivisuus
published: true
nav: true
navTitle: "Responsiivisuus"
order: 3
---

# Responsiivisuus

Kaikki suunnittelu on **mobiililähtöistä**: perustyyli kirjoitetaan mobiilille, ja suuremmille näytöille lisätään `sm:` / `md:` / `lg:` / `xl:` -muuttujia.

---

## Mobiililähtöinen suunnittelu

<callout type="info">

**Neljä perussääntöä:**
1. Älä käytä kiinteitä leveyksiä — käytä `max-w-*`, `w-full`, `flex` ja `grid`
2. Jätä tilaa kosketukselle: vähimmäiskosketusalue **44 × 44 px**
3. Älä luota pelkkään hover-tilaan — kaikki toiminnot myös napautuksella
4. Taulukot tarvitsevat vaakasuuntaisen vierityksen pienillä näytöillä

</callout>

---

## Murtopisteet

| Etuliite | Leveys | Laite | Tyypillinen käyttö |
|---|---|---|---|
| *(oletus)* | 0 px | Puhelin | `grid-cols-1` |
| `sm:` | 640 px | Suuri puhelin / pieni tabletti | `sm:grid-cols-2` |
| `md:` | 768 px | Tabletti | `md:flex-row` |
| `lg:` | 1024 px | Kannettava / työpöytä | `lg:grid-cols-3` |
| `xl:` | 1280 px | Suuri näyttö | `xl:grid-cols-4` |

---

## Säilö ja täytteet

Sisältöalueen perusmalline:

```html
<div class="max-w-5xl mx-auto px-4">
  <!-- Sisältö tähän -->
</div>
```

| Luokka | Arvo | Tarkoitus |
|---|---|---|
| `max-w-5xl` | 1024 px | Sisällön enimmäisleveys |
| `mx-auto` | auto | Keskittää vaakatasossa |
| `px-4` | 16 px | Vaakasuuntainen täyte kaikilla näytöillä |

---

## Ruudukkomallit

### 1. Väripaletti / logokortit

Kolme saraketta suurilla näytöillä:

```
Mobiili:  1 sarake
sm:       2 saraketta
lg:       3 saraketta
```

Tailwind: `grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6`

### 2. Komponenttiesittelyt

Kaksi saraketta tabletti-koosta ylöspäin:

```
Mobiili:  1 sarake
md:       2 saraketta
```

Tailwind: `grid grid-cols-1 md:grid-cols-2 gap-8`

### 3. Tilastot / avainluvut

Neljä saraketta suurilla näytöillä:

```
Mobiili:  1 sarake
sm:       2 saraketta
lg:       4 saraketta
```

Tailwind: `grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6`

---

## Yleiset asettelumallit

| Malli | Mobiili | Murto | Tailwind-luokat |
|---|---|---|---|
| Artikkeli | 1 sarake | — | `max-w-prose mx-auto` |
| Teksti + kuva | Pinottu | md (768 px) | `grid grid-cols-1 md:grid-cols-2 gap-8` |
| Sivupalkki | Pinottu | lg (1024 px) | `grid grid-cols-1 lg:grid-cols-[1fr_300px] gap-8` |
| Galleriaruudukko | 2 saraketta | lg (1024 px) | `grid grid-cols-2 lg:grid-cols-4 gap-4` |
| Korttilista | 1 sarake | sm (640 px) | `grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6` |
| Lomake | 1 sarake | — | `max-w-md mx-auto` |

---

## Responsiivinen typografia

<callout type="warning">

**Kolme typografiasääntöä:**
1. `type-display` (48 px) vain `md`-koosta ylöspäin — käytä `type-h1` mobiililla
2. Leipätekstin minimikoko on **16 px** (`type-body`), kuvatekstien **14 px** (`type-caption`)
3. Rivien enimmäispituus **75 merkkiä** — käytä `max-w-prose` tai `max-w-xl`

</callout>

---

## Kosketuskohteet

Kaikkien interaktiivisten elementtien vähimmäiskoko on **44 × 44 px**.

<callout type="success">

**Hyvä:** `py-3 px-4` — riittävä kosketusalue

</callout>

<callout type="error">

**Vältä:** `py-1 px-2` — liian pieni kosketusalue

</callout>

---

## Liike ja prefers-reduced-motion

Kaikki animaatiot on kääritty `prefers-reduced-motion` -tuen sisään (määritelty `style.css`-tiedostossa).

| Token | Arvo | Käyttö |
|---|---|---|
| `duration-fast` | 150 ms | Hover-tilat, fokusrenkaat |
| `duration-base` | 300 ms | Kortit, valikot, haitarit |
| `duration-slow` | 500 ms | Sivusiirtymät |

# Cross-Product Brand Alignment

## Changes needed across all product sites

### 1. Decode38 Footer — Add Axiom 38 parent link

In decode38/index.html, find the footer-col with "Decode38" title and add after the copyright line:

```html
<p style="margin-top:.6rem"><a href="https://axiom38.com" style="color:var(--gold-light);text-decoration:underline;text-underline-offset:2px;font-size:.72rem">An Axiom 38 company</a> · Disabled Veteran-Owned</p>
```

### 2. Principia Landing Footer — Add Axiom 38 parent link

In principia-landing/index.html, find the `.footer-brand` div and add after the description paragraph:

```html
<p style="font-size:12px;color:var(--text4);margin-top:8px"><a href="https://axiom38.com" style="color:var(--text3);text-decoration:underline;text-underline-offset:2px">An Axiom 38 company</a> · Disabled Veteran-Owned</p>
```

### 3. Decode38 — Add "Disabled Veteran-Owned" to header badge

Already present in the hero section. Consider also adding to the header-badge line:

```html
<!-- Current -->
<div class="header-badge">By vets, for vets · Free forever · ...

<!-- Updated -->
<div class="header-badge">Disabled Veteran-Owned · Free forever · ...
```

### 4. Principia Landing — Add veteran-owned signal

In the hero or footer, add a subtle note. Example for the hero-note line:

```html
<!-- Current -->
<p class="hero-note">Free forever for Tiers 1–2 · No account required to start</p>

<!-- Updated -->
<p class="hero-note">Free forever for Tiers 1–2 · No account required · Veteran-Owned</p>
```

## Why this matters

- Trust signal: "Disabled Veteran-Owned" builds credibility, especially with the VA/military audience that overlaps Decode38 and Principia
- Brand coherence: Users who find one product can discover the others through axiom38.com
- SEO: Cross-linking between domains strengthens all three sites

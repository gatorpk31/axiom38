# Principia Landing Page — App Store Button Fix

All app store buttons on getprincipia.com currently point to `href="#"`.
There are **5 broken links** total.

## iOS App Store URL
https://apps.apple.com/us/app/getprincipia/id6761139348

## Find & Replace in principia-landing/index.html

### Fix 1: Hero iOS button (line ~311)
```html
<!-- OLD -->
<a href="#" class="btn-primary" id="ios-btn">

<!-- NEW -->
<a href="https://apps.apple.com/us/app/getprincipia/id6761139348" class="btn-primary" id="ios-btn">
```

### Fix 2: Hero Android button (line ~315)
```html
<!-- OLD -->
<a href="#" class="btn-secondary" id="android-btn">

<!-- NEW — points to iOS until Android is live -->
<a href="https://apps.apple.com/us/app/getprincipia/id6761139348" class="btn-secondary" id="android-btn">
```

### Fix 3: Pricing "Download Free" button (line ~483)
```html
<!-- OLD -->
<a href="#" class="price-btn outline">Download Free</a>

<!-- NEW -->
<a href="https://apps.apple.com/us/app/getprincipia/id6761139348" class="price-btn outline">Download Free</a>
```

### Fix 4 & 5: Footer App Store links (lines ~538, ~542)
Both `<a href="#">` elements in the footer `.hero-actions` div need the same URL.

## Quick sed commands:

```bash
sed -i 's|<a href="#" class="btn-primary" id="ios-btn">|<a href="https://apps.apple.com/us/app/getprincipia/id6761139348" class="btn-primary" id="ios-btn">|g' index.html
sed -i 's|<a href="#" class="btn-secondary" id="android-btn">|<a href="https://apps.apple.com/us/app/getprincipia/id6761139348" class="btn-secondary" id="android-btn">|g' index.html
sed -i 's|<a href="#" class="price-btn outline">Download Free</a>|<a href="https://apps.apple.com/us/app/getprincipia/id6761139348" class="price-btn outline">Download Free</a>|g' index.html
```

The 2 footer links use inline styles — find all `<a href="#"` in the footer `.hero-actions` div and replace `href="#"` with `href="https://apps.apple.com/us/app/getprincipia/id6761139348"`.

Note: Android button also links to iOS App Store until a Play Store listing exists.

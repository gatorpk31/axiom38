# Principia Landing Page — App Store Button Fix

All app store buttons on getprincipia.com currently point to `href="#"`.
There are **5 broken links** total that need your real App Store URL.

## Step 1: Get Your App Store URLs

Find your iOS app URL in App Store Connect:
- Go to https://appstoreconnect.apple.com
- Your app → App Information → View on App Store
- URL format: `https://apps.apple.com/app/principia/id<YOUR_APP_ID>`

For Google Play (if published):
- URL format: `https://play.google.com/store/apps/details?id=<YOUR_BUNDLE_ID>`
- Bundle ID is in your `app.json` under `expo.android.package`

If Android isn't live yet, link to the iOS store for both buttons or hide the Google Play button.

## Step 2: Find & Replace in principia-landing/index.html

### Fix 1: Hero iOS button (line ~311)
```html
<!-- OLD -->
<a href="#" class="btn-primary" id="ios-btn">

<!-- NEW -->
<a href="https://apps.apple.com/app/principia/idYOUR_APP_ID" class="btn-primary" id="ios-btn">
```

### Fix 2: Hero Android button (line ~315)
```html
<!-- OLD -->
<a href="#" class="btn-secondary" id="android-btn">

<!-- NEW -->
<a href="https://play.google.com/store/apps/details?id=YOUR_BUNDLE_ID" class="btn-secondary" id="android-btn">
```

### Fix 3: Pricing "Download Free" button (line ~483)
```html
<!-- OLD -->
<a href="#" class="price-btn outline">Download Free</a>

<!-- NEW -->
<a href="https://apps.apple.com/app/principia/idYOUR_APP_ID" class="price-btn outline">Download Free</a>
```

### Fix 4 & 5: Footer App Store links (lines ~538, ~542)
Both `<a href="#">` elements in the footer `.hero-actions` div need the same real URLs.

## Quick sed command (replace YOUR_APP_ID first):

```bash
# After setting your real app ID:
sed -i 's|<a href="#" class="btn-primary" id="ios-btn">|<a href="https://apps.apple.com/app/principia/idYOUR_APP_ID" class="btn-primary" id="ios-btn">|g' index.html
sed -i 's|<a href="#" class="btn-secondary" id="android-btn">|<a href="https://play.google.com/store/apps/details?id=YOUR_BUNDLE_ID" class="btn-secondary" id="android-btn">|g' index.html
sed -i 's|<a href="#" class="price-btn outline">Download Free</a>|<a href="https://apps.apple.com/app/principia/idYOUR_APP_ID" class="price-btn outline">Download Free</a>|g' index.html
```

The footer links use inline styles instead of classes, so those need manual replacement.

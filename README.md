# Awyne bio page (Firebase Hosting, free)

A single page for your bio link. It sends people to **https://awyne.nastu.net** and has room for your channels later.
No backend, no database, nothing to pay for beyond Firebase's free plan.

## Put it online (about 5 minutes)
1. Go to https://console.firebase.google.com and click **Add project** (name it e.g. `awyne`; turn Google Analytics off).
2. On your computer install Node.js, then in a terminal:
   ```
   npm install -g firebase-tools
   firebase login
   ```
3. Open a terminal in this folder (the one with `firebase.json`) and link it to your project:
   ```
   firebase use --add
   ```
   Pick your project and give it the alias `default`.
4. Deploy:
   ```
   firebase deploy --only hosting
   ```
5. Firebase prints your address, like `https://awyne.web.app`. Put that link in your bio.

## Change things later (edit `public/index.html`, the block marked "EDIT THIS PART ONLY")
- **Change the domain of the movie site:** change `SITE_URL`, then run `firebase deploy --only hosting`.
- **Add channels:** fill in a `url` for a link and delete `soon: true`. Add or remove lines as you like.
- **Send people straight to the movie site:** set `AUTO_REDIRECT_SECONDS` to `3` (0 keeps them on this page).
- **Your own domain later:** Firebase console > Hosting > Add custom domain.

## Seeing bio visitors in your admin panel
The Watch button adds `?ref=bio`, and the browser also reports where the visitor came from, so
traffic from this page shows up under Traffic sources in your Mawira panel.

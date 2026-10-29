# EditDeck site

The marketing, support and privacy pages for EditDeck, served by GitHub
Pages from `main` at https://mgit-26c0d3.github.io/EditDeckiOS/.

This folder is a git clone of `Mgit-26C0d3/EditDeckiOS`. Edit here, commit,
then `git push`; Pages republishes in a minute or two. (The old
`EditDeck-Site 2` folder beside it is the August version and is no longer
the source.)

## Files

- `index.html`: the homepage.
- `support.html`: help and FAQ.
- `privacy-policy.html`: linked from the app's paywall and from App Store
  Connect. **Keep the filename.**
- `site.css`: shared by all three pages.
- `images/`: phone screens (880 × 1912; AVIF, with a JPEG fallback), the
  icon and favicon, and `og.jpg` (the 1200 × 630 link preview).
- `apple-touch-icon.png`: the 180 px home-screen icon.

## At launch

EditDeck isn't on the App Store yet, so every download button reads
"Coming soon" and links to the pricing section. Search the pages for
`APP-STORE-LINK`: it marks each button, three in `index.html` plus the
nav's "Get EditDeck". At launch, for each one:

1. Set `href` to the App Store URL.
2. In the badge, change `Coming soon on the` to `Download on the`, and the
   `aria-label` to "Download EditDeck on the App Store".

Apple's guidelines ask for the official badge artwork. The badge here is
drawn in its shape. Swap in Apple's SVG from
https://developer.apple.com/app-store/marketing/guidelines/ when you link
it.

## Screens

The screens come from `../Screenshots/2026-10-29 App Store/Raw - iPhone 18
Pro Max/`, all on invented sample data. To replace one (the dimensions must
be even, or the AVIF decodes as a blank frame):

    sips -z 1912 880 -s format avif  in.png --out images/name.avif
    sips -z 1912 880 -s format jpeg -s formatOptions 70 in.png --out images/name.jpg

## Copy that has to track the app

- **The privacy policy.** It must change whenever the app starts storing,
  syncing or requesting something new. Re-read it against the code before
  each release.
- **Feature claims.** Each one was checked against the code on 29 Oct 2026:
  - on-device transcription;
  - receipt reading by on-device text recognition;
  - Avid XML import and export;
  - the accountant pack (a summary PDF, CSVs and receipts);
  - Home and Lock Screen widgets, and Live Activities for recordings and
    events;
  - the weekly iCloud Drive backup, keeping the latest four;
  - the 7-day trial;
  - Family Sharing is off, so it isn't mentioned.
- **Requirements.** "iOS 26.2 or later" follows the deployment target.

## Preview

    python3 -m http.server 8899

then open http://127.0.0.1:8899

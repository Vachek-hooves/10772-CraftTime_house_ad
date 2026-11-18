# 10772-CraftTime_house_ad

House-ads config for `com.craft.time` (Coin Strike), served via GitHub Pages at
`https://vachek-hooves.github.io/10772-CraftTime_house_ad/config.json`.

`engine_enabled` is currently `false` and `creatives` is empty -- this is a
placeholder so the app's config fetch succeeds (200 + valid JSON) instead of
404ing, not a real ad setup yet.

## To actually turn house ads on

1. Pick which other app(s) in the portfolio to cross-promote here.
2. Drop their creative images into `media/` (banner + a few interstitial/
   rewarded slides + an icon), matching the pattern other house-ad repos use,
   e.g. `media/banner_1.jpg`, `media/screen_1.jpg`, `media/icon.png`.
3. Add entries to `creatives` in `config.json`, one per image, e.g.:

```json
{
  "id": "<other-app>_banner_1",
  "format": "image",
  "placements": ["banner"],
  "image_url": "https://vachek-hooves.github.io/10772-CraftTime_house_ad/media/banner_1.jpg",
  "icon_url": "https://vachek-hooves.github.io/10772-CraftTime_house_ad/media/icon.png",
  "title": "",
  "body": "",
  "cta_text": "PLAY",
  "bundle_id": "<the other app's applicationId>",
  "store_url": "https://play.google.com/store/apps/details?id=<the other app's applicationId>",
  "weight": 1
}
```

`placements` is one or more of `banner`, `interstitial`, `rewarded`.

4. Flip `engine_enabled` back to `true`.
5. Commit and push -- GitHub Pages serves whatever is on `main` directly, no
   build step, so changes go live within a minute or two.

# Wipe: release checklist

Stan na 17.10.2026. Strona gotowa (bashubb.com/wipe/), privacy i support w nowym stylu, karta podglądu linku zrobiona.

## Do potwierdzenia z aplikacją
- [ ] Cennik na stronie: 3 darmowe czyszczenia, potem jednorazowy zakup **Wipe Pro**, bez subskrypcji. Zgadza się z wersją wysyłaną do review?
- [ ] JSON-LD ma dziś `"price": "0"`: ustawić prawdziwą wartość albo usunąć `offers`.
- [ ] Privacy „Last updated: October 6, 2026”: czy treść (RevenueCat, Share Extension, brak uploadu) dalej odpowiada aplikacji.
- [ ] FAQ i support: obsługiwane iOS (strona mówi „iOS 18 or later”), Live Photos, gdzie lądują kopie.
- [ ] W `index.html` (linia ~11) jest gotowy komentarz z `apple-itunes-app`: odkomentować i wpisać id.

## Na stronie (wszystko w `docs/`)
- [ ] Link do App Store: podmień `https://apps.apple.com/us/search?term=…` na adres aplikacji (`…/app/idXXXXXXXXXX`) we wszystkich `data-store-link` (index, privacy, support).
- [ ] `<html data-store="soon">` → `"live"` w `index.html`. Jednym ruchem zamienia „Coming soon” na odznakę App Store w pasku, hero, stopce.
- [ ] Baner Safari: `<meta name="apple-itunes-app" content="app-id=XXXXXXXXXX">` w `<head>` strony głównej.
- [ ] JSON-LD `SoftwareApplication`: dodać/poprawić `offers` (cena lub usunąć) i link do App Store.
- [ ] Podbić `?v=` przy zmienionym CSS/JS, wypchnąć, sprawdzić na żywo: desktop, telefon pionowo, telefon poziomo.
- [ ] Odpalić `fit-audit.js` (desktop) i `phone-audit.js` (telefony) ze skilla `bashubb-app-sites` → „ALL … FIT”.

## bashubb.com (repo `Bashubb`)
- [ ] Przenieść kartę Wipe z sekcji **Coming soon** do **Available now**, dodać odznakę App Store z linkiem.
- [ ] Dodać Wipe do JSON-LD (`@graph`, jak Shrink) i do `sitemap.xml`.

## App Store Connect
- [ ] Privacy Policy URL: `https://bashubb.com/wipe/privacy/`
- [ ] Support URL: `https://bashubb.com/wipe/support/`
- [ ] Marketing URL: `https://bashubb.com/wipe/`

# Wipe: release checklist

Stan na 4.11.2026. Strona przebudowana pod aplikację w stylu Ink & Marker (motyw, zrzuty, film, karta podglądu, ikony, treść, privacy i support); audyty `fit-audit` i `phone-audit` przechodzą.

## Do potwierdzenia z aplikacją
- [ ] Cennik na stronie: 3 darmowe czyszczenia po maks. 5 elementów, potem jednorazowy zakup **Wipe Pro** (bez limitów i z czyszczeniem z Share Sheet), bez subskrypcji. Zgadza się z wersją wysyłaną do review?
- [ ] Share Sheet: limit 20 elementów, Live Photo i filmy wymagające nowej kopii idą do aplikacji (7 dni); strona tak mówi. Sprawdzić na telefonie, że Wipe pokazuje się w Share Sheet także przy Live Photo (reguła aktywacji bez plików ogólnych).
- [ ] JSON-LD ma dziś `"price": "0"`: ustawić prawdziwą wartość albo usunąć `offers`.
- [ ] Privacy „Last updated: November 4, 2026”: dopisane Share Sheet (folder roboczy kasowany po zamknięciu, wybór czeka do 7 dni) i „Show on map” (Apple Maps po tapnięciu); sprawdzić z etykietą prywatności w App Store Connect.
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

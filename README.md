# Djuk Collection — Bold Edition

Drugi, niezależny wariant demonstracyjnego sklepu: kobalt, ogromna pochylona typografia, okrągłe akcenty i fotografia kampanijna.

- Wersja Bold: https://maciejsobolewski3-web.github.io/djuk-collection-bold/
- Pierwsza wersja: https://maciejsobolewski3-web.github.io/djuk-collection/

Koszyk, ulubione i intro mają osobne klucze pamięci `djuk.bold.*`, dzięki czemu oba projekty można porównywać w tej samej przeglądarce.

## Zawartość

- Strona główna, katalog oraz trzy kategorie.
- Cztery strony produktów, warianty kolorystyczne, wybór rozmiaru, powiększenie zdjęć i zbliżenie.
- Wyszukiwanie, sortowanie cen i ulubione.
- Koszyk z obsługą wariantów, ilości i zapisem w localStorage.
- Podsumowanie koszyka, strony marki i kontaktu.
- Responsywna nawigacja, obsługa klawiatury i ograniczonych animacji.
- Białe intro z animowaną nazwą marki, raz na sesję, z możliwością pominięcia.
- Nagłówki pisane litera po literze i subtelne pojawianie się sekcji przy przewijaniu.
- Dodatkowe wygenerowane ujęcie każdego produktu, zmiana zdjęcia przy najechaniu i pełna galeria z powiększeniem.
- Rozbudowane opisy kategorii, detali produktów i propozycje stylizacji.

To **wersja pokazowa**. Modele, rozmiary i ceny są przykładowe. Zdjęcia wygenerowano przy użyciu wbudowanego image_gen. Strona nie przetwarza płatności, nie przyjmuje zamówień i nie zbiera danych klienta. Funkcje ulubionych oraz koszyka korzystają wyłącznie z pamięci przeglądarki. Fonty Manrope i DM Sans są pobierane z Google Fonts, z systemową czcionką zastępczą.

## Uruchomienie

```sh
npm start
```

Strona będzie dostępna pod adresem http://localhost:4174. Wymagany Python 3; aplikacja nie wymaga instalacji paczek ani etapu budowania.

```sh
npm run check
```

Sprawdzenie składni wymaga Node.js. Pliki `index.html`, `style.css`, `bold.css`, `app.js`, `motion.js` oraz `assets/` można hostować bezpośrednio jako stronę statyczną. Routing po fragmencie URL (`#/produkt/rhythm-black`) pozwala otwierać i odświeżać podstrony na GitHub Pages bez konfiguracji przekierowań serwera.

## Edycja

Dane produktów i treść podstron: `app.js`. Style bazowe: `style.css`; styl wariantu i punkty przełamania: `bold.css`. Nawigacja, metadane i stopka: `index.html`. Obrazy WebP: `assets/`. Plik `.nojekyll` wyłącza przetwarzanie przez Jekyll.

Przed uruchomieniem sprzedaży należy zastąpić dane przykładowe rzeczywistym katalogiem, dodać backend zamówień, płatności, dostawy oraz zatwierdzone informacje sklepu. Indeksowanie wyszukiwarek jest wyłączone dla tej wersji demonstracyjnej.

## Weryfikacja

Przetestowano w Chromium na desktopie i telefonie: nawigację, kategorie, sortowanie, walidację rozmiaru, ilości i sumy koszyka, zapis po odświeżeniu, wyszukiwanie, ulubione, galerie, okna dialogowe oraz brak poziomego przewijania na telefonie. Bez błędów JavaScript i brakujących zasobów.

## Animacje i nowe zdjęcia

`motion.js` obsługuje intro, efekt pisania i animacje przy przewijaniu. Intro jest zapamiętywane w `sessionStorage`, można je pominąć, a przy `prefers-reduced-motion` efekty są wyłączone. Ekran wejściowy czeka na fonty i główne zdjęcie z limitem czasu, więc wolne połączenie nie blokuje strony. Litery zajmują miejsce od początku, dzięki czemu nagłówki nie przesuwają układu.

Nowe zdjęcia znajdują się w `assets/*-alternate.webp`. Pełne prompty użyte z wbudowanym image_gen: [alternate-image-prompts.json](assets/alternate-image-prompts.json).

Nowe zdjęcie kampanijne: `assets/campaign.webp`. Prompt generowania: [campaign-prompt.txt](assets/campaign-prompt.txt). Sprawdzono układy od 320 do 1440 px, niezależny zapis obu wersji, animowane intro oraz tryb ograniczonego ruchu.

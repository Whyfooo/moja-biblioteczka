# Moja Biblioteczka

Wizualizacja kolekcji mangi i light novelek hostowana na GitHub Pages z bazą danych Firebase.

## Struktura plików

```
index.html       – główna strona z wizualizacją półek
admin.html       – panel zarządzania kolekcją (wymaga logowania)
firestore.rules  – reguły bezpieczeństwa Firestore (wgraj przez konsolę Firebase)
covers/          – okładki tomów (dodawaj samodzielnie, format: seriesId_vol.jpg)
```

## Dodawanie okładek

Wrzuć plik JPG/PNG do folderu `covers/` w repozytorium.
Nazwa pliku dowolna — URL wpisz przy dodawaniu tomu w panelu admina, np.:
```
https://whyfooo.github.io/moja-biblioteczka/covers/frieren_1.jpg
```

## Reguły Firestore

Wejdź w Firebase Console → Firestore → Rules i wklej zawartość pliku `firestore.rules`.

## Schemat danych

**Kolekcja `series`:**
- `name` – pełna nazwa serii
- `shortName` – skrót na grzbiet
- `type` – manga / light novel / manhwa / special
- `lang` – PL / EN
- `publisher` – wydawnictwo
- `order` – kolejność na półce (liczba)
- `spineColor` – kolor grzbietu (hex)
- `spineTextColor` – kolor tekstu grzbietu (hex)

**Kolekcja `volumes`:**
- `seriesId` – ID dokumentu z kolekcji `series`
- `volNumber` – numer tomu
- `width` – szerokość grzbietu w mm
- `read` – true / false
- `coverUrl` – URL okładki (opcjonalnie)

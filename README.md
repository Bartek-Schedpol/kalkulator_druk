# Kalkulator kosztów druku — Schedpol

Szybki szacunek kosztów materiałów drukowanych z uwzględnieniem rabatu Schedpol.
Aplikacja statyczna hostowana na GitHub Pages, ceny aktualizowane codziennie przez GitHub Actions.

## Uruchomienie (5 minut)

### 1. Utwórz repozytorium GitHub
- Wejdź na github.com → New repository
- Nazwa np. `druk-kalkulator`
- Ustaw jako **Private** (jeśli chcesz ograniczyć dostęp) lub **Public**

### 2. Wgraj pliki
Wgraj wszystkie pliki z tego pakietu do repozytorium:
```
index.html
prices.json
scraper.js
.github/workflows/update-prices.yml
README.md
```

### 3. Włącz GitHub Pages
- Settings → Pages → Source: **Deploy from a branch**
- Branch: `main`, folder: `/ (root)`
- Zapisz — po chwili aplikacja będzie dostępna pod adresem:
  `https://TWOJA-NAZWA.github.io/druk-kalkulator/`

### 4. Sprawdź GitHub Actions
- Zakładka Actions → powinien pojawić się workflow "Aktualizuj ceny druku"
- Uruchom ręcznie (Run workflow) żeby przetestować
- Domyślnie odpala się codziennie o 07:00 CET

## Aktualizacja cen ręcznie

Edytuj `prices.json` bezpośrednio na GitHubie lub lokalnie i commituj.
Kluczowe pola do aktualizacji: wartości w sekcji `"base"` — cena za sztukę dla poszczególnych formatów.

## Struktura plików

```
├── index.html          # Aplikacja kalkulatora (HTML + CSS + JS, bez zależności)
├── prices.json         # Dane cenowe — aktualizowane przez Actions lub ręcznie
├── scraper.js          # Skrypt Node.js pobierający/weryfikujący ceny
├── .github/
│   └── workflows/
│       └── update-prices.yml  # GitHub Actions cron job
└── README.md
```

## Dostosowanie rabatu

Zmień wartość `"discount_schedpol"` w `prices.json` — kalkulator pobierze ją automatycznie.
Użytkownik może też zmienić rabat ręcznie w aplikacji (pole jest edytowalne).

## Wymagania

- Konto GitHub (darmowe)
- Brak serwera, brak bazy danych, brak logowania
- Aplikacja działa w każdej przeglądarce

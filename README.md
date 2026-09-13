# Travio

Uniwersalna aplikacja do planowania wycieczek — działa z dowolnym miastem, obsługuje wiele wycieczek naraz i pracuje offline. Statyczna aplikacja jednoplikowa (bez backendu i bez builda) opakowana jako instalowalny PWA.

## Uruchomienie GitHub Pages

1. **Settings → Pages** w tym repozytorium.
2. "Build and deployment" → **Source: Deploy from a branch**.
3. Branch: `main`, folder: **/ (root)** → zapisz.
4. Po chwili aplikacja będzie dostępna pod `https://<twoj-login>.github.io/travio/`.

Wszystko jest już przygotowane pod hosting w katalogu głównym — nie trzeba nic dodatkowo budować ani konfigurować.

## Instalacja na telefonie

Po wejściu na `https://<twoj-login>.github.io/travio/`:

- **Android (Chrome):** menu (⋮) → **"Zainstaluj aplikację"** / **"Dodaj do ekranu głównego"**. Dzięki service workerowi aplikacja po pierwszym wejściu online działa też całkowicie offline (np. w podróży bez zasięgu).
- **iPhone/iPad (Safari):** przycisk udostępniania (□↑) → **"Dodaj do ekranu początkowego"**.

Dane wycieczek (postęp, notatki, zdjęcia z dziennika) zapisują się lokalnie na urządzeniu (localStorage) — na razie nie synchronizują się między urządzeniami ani kontami.

## Struktura plików

- `index.html` — cała aplikacja.
- `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — wymagane, żeby PWA dało się zainstalować i działało offline. Muszą zostać w tym samym katalogu co `index.html`.

## Plany rozwoju

Kolejny etap: synchronizacja danych przez Firebase (Firestore + Auth), żeby:
- założyć konto i zalogować się na kilku urządzeniach z tymi samymi wycieczkami,
- zaprosić inne osoby do wspólnej wycieczki, żeby widziały ten sam plan i wspólnie go edytowały.

Ponieważ Travio to statyczna aplikacja hostowana na GitHub Pages, doda się to czysto po stronie klienta (Firebase JS SDK) — bez zmiany sposobu hostowania.

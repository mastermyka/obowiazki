# Deploy — GitHub Pages

1. Utwórz publiczne repozytorium **organizer** (może być dowolna nazwa).
2. Wgraj całą zawartość folderu `deploy/` do **roota** repo (czyli `index.html`, `sw.js`, `manifest.webmanifest`, folder `icons/`, `firebase-config.js`).
3. Włącz GitHub Pages: **Settings → Pages → Build and deployment → Source: Deploy from a branch** i wybierz gałąź `main` i folder `/ (root)`.
4. Otwórz stronę: `https://<twoj-user>.github.io/<nazwa-repo>/`.
5. Jeśli widzisz 404, najczęstsze przyczyny:
   - brak `index.html` w katalogu root (musi być w root lub w `docs/` jeśli tak ustawisz w Pages),
   - repo jest prywatne (Pages wymaga publicznego lub planu Pro),
   - literówka w adresie (`user.github.io/repo` zamiast `user.github.io` lub odwrotnie),
   - `sw.js` i `manifest.webmanifest` muszą być w tym samym katalogu co `index.html` lub ścieżki w `<link rel="manifest">` są błędne.
6. Firebase (opcjonalnie): w pliku `firebase-config.js` wstaw swój obiekt konfiguracyjny:
   ```js
   window.firebaseConfig = {
     apiKey: "...",
     authDomain: "...",
     projectId: "...",
     storageBucket: "...",
     messagingSenderId: "...",
     appId: "..."
   };
   ```
   Jeśli nie uzupełnisz — aplikacja po prostu pominie sync.

# Szkoła Reacta - Projekty

Ogólny zarys projektu - w raz z pojawiającymi się materiałami będziemy tworzyli projekt wyświetlający ulubione pliki wideo :)
Na start możemy wykorzystać filmiki z YouTube albo Vimeo.

Prawdopodobnie z każdym nowym tygodniem, po nowych lekcjach będziesz chciał/chciała refaktorować swój projekt. Nie krępuj się - nawet jest to wskazane :)

Założenia podstawowe - dane, czyli listę filmów będziemy trzymali w lokalnym pliku `database.json`. Później zamienimy to na komunikację z bazą danych poprzez REST API.

## Część 1

* Stwórz nowy projekt za pomocą `create-react-app`
* Pomyśl nad strukturą plików i katalogów - na razie luźno, potem będziemy ją zmieniać
* Stwórz plik `database.json`, który będzie zawierał listę obiektów:

```json
[
  {
    "title": "Mój ulubiony filmik 1",
    "description": "Opis mojego ulubionego filmiku",
    "video_url": "Adres URL do filmu np.: https://youtu.be/Bey4XXJAqS8"
  },
  {
    "title": "Mój ulubiony filmik 2",
    "description": "Opis mojego ulubionego filmiku 2",
    "video_url": "https://youtu.be/Bey4XXJAqS8"
  }
]

```

* Stwórz komponent do wyświetlania pojedyńczego filmu np. `Video`
* Stwórz komponent, który będzie wyświetlał listę wideo i korzystał z komponentów `Video` np. może być to komponent `VideoList`.
* Osadź komponent `VideoList` w głównej aplikacji czyli w `App`
* W komponencie `Video` możesz skorzystać z narzędzia do generowania adresu URL do miniaturek: np.: http://www.get-youtube-thumbnail.com/
* Do wyświetlania wideo wykorzystaj albo player HTML5 lub inną bibliotekę (np. [Video.js](https://videojs.com/), [Plyr.io](https://plyr.io/))

Powodzenia :)
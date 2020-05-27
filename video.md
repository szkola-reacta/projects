# Serwis Video

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

# Część 2
Zmodyfikuj zawartość pliku `database.json`, aby zawierał unikalne identyfikatory do każdego z filmu. Np.:


```json
[
  {
  	"id": 1,
    "title": "Mój ulubiony filmik 1",
    "description": "Opis mojego ulubionego filmiku",
    "video_url": "Adres URL do filmu np.: https://youtu.be/Bey4XXJAqS8"
  },
  {
    "id": 2,
    "title": "Mój ulubiony filmik 2",
    "description": "Opis mojego ulubionego filmiku 2",
    "video_url": "https://youtu.be/Bey4XXJAqS8"
  }
]

```

1. Dodamy Routing do aplikacji. Zmodyfikuj kod z części pierwszej w taki sposób, aby komponent `VideoList` wyświetlał się zaraz po otworzeniu aplikacji.

1. Dodaj ścieżkę url `/about` gdzie będą prezentowane informacje o aplikacji.

1. Dodaj ścieżkę url `/video/:id` pod którą będzie prezentowane wideo o określonym id. Tzn. jeśli mamy `/video/1` powinniśmy wyświetlić obiekt z id 1 z pliku `database.json`. Wykorzystaj do tego komponent `Video`. Jeśli wprowadzimy identyfikator, którego nie ma w `database.json`, wtedy należy wyświetlić komunikat: "Nie znaleziono filmu".

1. Stwórz komponent `Page404` i wyświetlaj go zawsze, gdy ktoś wprowadzi adres url, który nie istnieje w Twojej aplikacji np. `/tosienieuda`.


1. Stwórz komponent `VideoCreateForm`, który będzie dostępny pod adresem url `/video/create`. Komponent powinien zawierać formularz z polami do tworzenia nowego obiektu, czyli posiadać pola: `title`, `description`, `video_url`. Po wysłaniu formularza dane powinny być dostępne w stanie komponentu.

1. Stwórz komponent `VideoUpdateForm`, który będzie dostępny pod adresem url `/video/:id/update`. Komponent powinien odczytać parametr `id` z adresu URL, pobrać odpowiedni obiekt z pliku `database.json`, a następnie wstawić dane tego obiektu do formularza. Formularz może być podobny do tego, który stworzyliśmy w `VideoCreateForm` - możesz nawet wykorzystać ten sam komponent. Chodzi o wypełnienie formularza odpowiednimi danymi. Formularz powinien przechowywać aktualne dany w stanie komponentu.

Powodzenia :)

## Część 3
Zaczniemy działać z API. informacje wkrótce :)
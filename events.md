# Serwis z wydarzeniami

Ogólny zarys projektu - w raz z pojawiającymi się materiałami będziemy tworzyli projekt wyświetlający wydarzenia (koncerty, seanse, spektakle) :)

Prawdopodobnie z każdym nowym tygodniem, po nowych lekcjach będziesz chciał/chciała refaktorować swój projekt. Nie krępuj się - nawet jest to wskazane :)

Założenia podstawowe - dane, czyli listę wydarzeń będziemy trzymali w lokalnym pliku `database.json`. Później zamienimy to na komunikację z bazą danych poprzez REST API.

Tips: można wykorzystać: https://source.unsplash.com/ do wygenerowania danych

## Część 1

* Stwórz nowy projekt za pomocą `create-react-app`
* Pomyśl nad strukturą plików i katalogów - na razie luźno, potem będziemy ją zmieniać
* Stwórz plik `database.json`, który będzie zawierał listę obiektów:

```json
[
  {
    "title": "Nazwa wydarzenia np. Koncert Fasolek",
    "description": "Opis wydarzenia",
    "cover_url": "Adres URL do cover foto wydarzenia",
    "price": "Cena za bilet",
    "city": "Miasto",
    "category": "concert",
    "address": "Adres",
    "date": "Data wydarzenia",
    "hour": "Godzina wydarzenia",
  },
  {
    "title": "Carlos Santana feat Fasolki",
    "description": "Lorem ipsum sit dolor",
    "cover_url": "https://static.billboard.com/files/media/santana-june-20-2019-billboard-1548-1024x677.jpg",
    "price": "130",
    "city": "Mexico",
    "address": "El Gato 12",
    "date": "28.05.2021",
    "category": "concert",
    "hour": "18:00",
  },
  {
    "title": "Spotkanie meet.js",
    "description": "Lorem ipsum sit dolor",
    "cover_url": "https://secure.meetupstatic.com/photos/event/8/a/6/2/600_472835426.jpeg",
    "price": "0",
    "city": "Katowice",
    "address": "Górnicza 8",
    "date": "20.06.2021",
    "category": "event",
    "hour": "17:00",
  }
]

```

* Stwórz komponent do wyświetlania pojedyńczego wydarzenia np. `Event`. Powinien zawierać wszystkie informacje z pliku `database.json`
* Stwórz komponent, który będzie wyświetlał listę wydarzeń i korzystał z komponentów `Event` np. może być to komponent `EventList`.
* Osadź komponent `EventList` w głównej aplikacji czyli w `App`
* Na stronie głównej w kolejnych etapach przygotujemy filtry do wyszukiwania wydarzeń, więc warto umieścić już pole tekstowe z możliwością wprowadzenia nazwy wydarzenia
* Pierwszy filtr umożliwi filtrowanie po kategoriach. Dostępne kategorie na start to: "concert" (Koncerty), "movie" (Filmy/spektakle), "event" (Wydarzenia stacjonarne)

Powodzenia :)

## Część 2
Zmodyfikuj zawartość pliku `database.json`, aby zawierał unikalne identyfikatory do każdego z wydarzeń. Np.:


```json
[
  {
    "id": 1,
    "title": "Nazwa wydarzenia np. Koncert Fasolek",
    "description": "Opis wydarzenia",
    "cover_url": "Adres URL do cover foto wydarzenia",
    "price": "Cena za bilet",
    "city": "Miasto",
    "category": "concert",
    "address": "Adres",
    "date": "Data wydarzenia",
    "hour": "Godzina wydarzenia",
  },
  {
    "id": 2,
    "title": "Carlos Santana feat Fasolki",
    "description": "Lorem ipsum sit dolor",
    "cover_url": "https://static.billboard.com/files/media/santana-june-20-2019-billboard-1548-1024x677.jpg",
    "price": "130",
    "city": "Mexico",
    "address": "El Gato 12",
    "date": "28.05.2021",
    "category": "concert",
    "hour": "18:00",
  }
]
```

1. Dodamy Routing do aplikacji. Skorzystaj z [React Router](https://reacttraining.com/react-router/web/guides/quick-start). Zmodyfikuj kod z części pierwszej w taki sposób, aby komponent `EventList` wyświetlał się zaraz po otworzeniu aplikacji.

1. Dodaj ścieżkę url `/about` gdzie będą prezentowane informacje o aplikacji.

1. Dodaj ścieżkę url `/event/:id` pod którą będzie prezentowane miejsce o określonym id. Tzn. jeśli mamy `/event/1` powinniśmy wyświetlić obiekt z id 1 z pliku `database.json`. Wykorzystaj do tego komponent `Event`. Jeśli wprowadzimy identyfikator, którego nie ma w `database.json`, wtedy należy wyświetlić komunikat: "Nie znaleziono wydarzenia".

1. Stwórz komponent `Page404` i wyświetlaj go zawsze, gdy ktoś wprowadzi adres url, który nie istnieje w Twojej aplikacji np. `/tosienieuda`.

1. Stwórz komponent `EventCreateForm`, który będzie dostępny pod adresem url `/event/create`. Komponent powinien zawierać formularz z polami do tworzenia nowego obiektu, czyli posiadać pola: `title`, `description`, `cover_url`, `price`, `city`, `category`, `address`, `date`, `hour`. Po wysłaniu formularza dane powinny być dostępne w stanie komponentu.

1. Stwórz komponent `EventUpdateForm`, który będzie dostępny pod adresem url `/event/:id/update`. Komponent powinien odczytać parametr `id` z adresu URL, pobrać odpowiedni obiekt z pliku `database.json`, a następnie wstawić dane tego obiektu do formularza. Formularz może być podobny do tego, który stworzyliśmy w `EventCreateForm` - możesz nawet wykorzystać ten sam komponent. Chodzi o wypełnienie formularza odpowiednimi danymi. Formularz powinien przechowywać aktualne dany w stanie komponentu.


Powodzenia :)

## Część 3
Zaczniemy działać z API. informacje wkrótce :)
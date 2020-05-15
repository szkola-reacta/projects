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
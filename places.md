# Serwis z atrakcjami turystycznymi

Ogólny zarys projektu - w raz z pojawiającymi się materiałami będziemy tworzyli projekt wyświetlający miejsca warte odwiedzenia :)

Prawdopodobnie z każdym nowym tygodniem, po nowych lekcjach będziesz chciał/chciała refaktorować swój projekt. Nie krępuj się - nawet jest to wskazane :)

Założenia podstawowe - dane, czyli listę miejsc będziemy trzymali w lokalnym pliku `database.json`. Później zamienimy to na komunikację z bazą danych poprzez REST API.


## Część 1

* Stwórz nowy projekt za pomocą `create-react-app`
* Pomyśl nad strukturą plików i katalogów - na razie luźno, potem będziemy ją zmieniać
* Stwórz plik `database.json`, który będzie zawierał listę obiektów:

```json
[
  {
    "title": "Nazwa miejsca",
    "description": "Opis miejsca",
    "foto_url": "Adres URL do zdjęcia",
    "price": "Cena za wstęp",
    "city": "Miasto",
    "category": "monument",
    "address": "Adres"
  },
  {
    "title": "Zamek Lubelski w Lublinie",
    "description": "Super zamczysko",
    "foto_url": "https://lublin4u.pl/media/images/m/zamek-lubelski-plac-zamkowy-donzon.jpg",
    "price": "15",
    "city": "Lublin",
    "address": "Plac Zamkowy 1",
    "category": "monument"
  },
  {
    "title": "Brama Krakowska",
    "description": "Brama jakich mało",
    "foto_url": "https://lublin4u.pl/media/images/m/brama-krakowska-lublin.jpg",
    "price": "0",
    "city": "Lublin",
    "address": "Plac Łokietka 1",
    "category": "monument"
  }
]

```

* Stwórz komponent do wyświetlania pojedyńczego miejsca np. `Place`. Powinien zawierać wszystkie informacje z pliku `database.json`
* Stwórz komponent, który będzie wyświetlał listę miejsc i korzystał z komponentów `Place` np. może być to komponent `PlaceList`.
* Osadź komponent `PlaceList` w głównej aplikacji czyli w `App`
* Na stronie głównej w kolejnych etapach przygotujemy filtry do wyszukiwania miejsce, więc warto umieścić już pole tekstowe z możliwością wprowadzenia nazwy miasta
* Pierwszy filtr umożliwi filtrowanie po miastach. Następnie wprowadzimy możliwość filtrowania po cenach

Powodzenia :)

## Część 2
Zmodyfikuj zawartość pliku `database.json`, aby zawierał unikalne identyfikatory do każdego z miejsc. Np.:


```json
[
  {
    "id": 1,
    "title": "Nazwa miejsca",
    "description": "Opis miejsca",
    "foto_url": "Adres URL do zdjęcia",
    "price": "Cena za wstęp",
    "city": "Miasto",
    "category": "monument",
    "address": "Adres"
  },
  {
    "id": 2,
    "title": "Zamek Lubelski w Lublinie",
    "description": "Super zamczysko",
    "foto_url": "https://lublin4u.pl/media/images/m/zamek-lubelski-plac-zamkowy-donzon.jpg",
    "price": "15",
    "city": "Lublin",
    "address": "Plac Zamkowy 1",
    "category": "monument"
  }
]
```

1. Dodamy Routing do aplikacji. Zmodyfikuj kod z części pierwszej w taki sposób, aby komponent `PlaceList` wyświetlał się zaraz po otworzeniu aplikacji.

1. Dodaj ścieżkę url `/about` gdzie będą prezentowane informacje o aplikacji.

1. Dodaj ścieżkę url `/place/:id` pod którą będzie prezentowane miejsce o określonym id. Tzn. jeśli mamy `/place/1` powinniśmy wyświetlić obiekt z id 1 z pliku `database.json`. Wykorzystaj do tego komponent `Place`. Jeśli wprowadzimy identyfikator, którego nie ma w `database.json`, wtedy należy wyświetlić komunikat: "Nie znaleziono miejsca".

1. Stwórz komponent `Page404` i wyświetlaj go zawsze, gdy ktoś wprowadzi adres url, który nie istnieje w Twojej aplikacji np. `/tosienieuda`.

1. Stwórz komponent `PlaceCreateForm`, który będzie dostępny pod adresem url `/place/create`. Komponent powinien zawierać formularz z polami do tworzenia nowego obiektu, czyli posiadać pola: `title`, `description`, `foto_url`, `price`, `city`, `address`, `category`. Po wysłaniu formularza dane powinny być dostępne w stanie komponentu.

1. Stwórz komponent `PlaceUpdateForm`, który będzie dostępny pod adresem url `/placevent/:id/update`. Komponent powinien odczytać parametr `id` z adresu URL, pobrać odpowiedni obiekt z pliku `database.json`, a następnie wstawić dane tego obiektu do formularza. Formularz może być podobny do tego, który stworzyliśmy w `PlaceCreateForm` - możesz nawet wykorzystać ten sam komponent. Chodzi o wypełnienie formularza odpowiednimi danymi. Formularz powinien przechowywać aktualne dany w stanie komponentu.


Powodzenia :)

## Część 3
Zaczniemy działać z API. informacje wkrótce :)
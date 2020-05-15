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
# Lab 5-6: Listy, krotki, zbiory, słowniki i operacje CRUD

**Uwaga:** Zakładamy, że środowisko wirtualne zostało już przygotowane (ćwiczenie 0 z Lab_1-2).

## Ćwiczenie 1: Podstawowe operacje na listach (łatwe)

Stwórz listę zawierającą liczby od 1 do 10. Następnie:
- Dodaj liczbę 11 na koniec listy
- Wstaw liczbę 0 na początek listy
- Usuń liczbę 5 z listy
- Wyświetl długość listy

```python
liczby = list(range(1, 11))
# Twój kod tutaj
```

<details>
<summary>Rozwiązanie</summary>

```python
liczby = list(range(1, 11))
liczby.append(11)
liczby.insert(0, 0)
liczby.remove(5)
print(len(liczby))  # Wynik: 11
```
</details>

## Ćwiczenie 2: Slicing list (łatwe)

Mając listę `owoce = ['jabłko', 'banan', 'gruszka', 'pomarańcza', 'kiwi', 'mango', 'arbuz']`:
- Wyświetl pierwsze 3 owoce
- Wyświetl ostatnie 2 owoce
- Wyświetl co drugi owoc
- Wyświetl listę w odwrotnej kolejności

```python
owoce = ['jabłko', 'banan', 'gruszka', 'pomarańcza', 'kiwi', 'mango', 'arbuz']
# Twój kod tutaj
```

<details>
<summary>Rozwiązanie</summary>

```python
owoce = ['jabłko', 'banan', 'gruszka', 'pomarańcza', 'kiwi', 'mango', 'arbuz']
print(owoce[:3])      # ['jabłko', 'banan', 'gruszka']
print(owoce[-2:])     # ['mango', 'arbuz']
print(owoce[::2])     # ['jabłko', 'gruszka', 'kiwi', 'arbuz']
print(owoce[::-1])    # Lista odwrócona
```
</details>

## Ćwiczenie 3: Krotki - niezmienność (łatwe)

Stwórz krotkę `punkt = (3, 5)` reprezentującą współrzędne punktu na płaszczyźnie. Spróbuj:
- Wyświetl współrzędne x i y osobno
- Spróbuj zmienić wartość x na 10 (co się stanie?)
- Stwórz nową krotkę z nowymi współrzędnymi (10, 5)

```python
punkt = (3, 5)
# Twój kod tutaj
```

<details>
<summary>Rozwiązanie</summary>

```python
punkt = (3, 5)
x, y = punkt
print(f"x = {x}, y = {y}")

# punkt[0] = 10  # TypeError - krotki są niemutowalne!

nowy_punkt = (10, 5)
print(nowy_punkt)
```
</details>

## Ćwiczenie 4: Operacje na zbiorach (średnie)

Masz dwa zbiory studentów uczęszczających na różne kursy:
```python
kurs_python = {'Anna', 'Jan', 'Kasia', 'Piotr', 'Marek'}
kurs_java = {'Jan', 'Kasia', 'Tomek', 'Ewa', 'Marek'}
```

Znajdź:
- Studentów uczęszczających na oba kursy (przecięcie)
- Studentów uczęszczających na co najmniej jeden kurs (suma)
- Studentów tylko na kursie Pythona (różnica)
- Studentów na dokładnie jednym kursie (różnica symetryczna)

**Oczekiwane wyniki:**
- Oba kursy: `{'Jan', 'Kasia', 'Marek'}`
- Co najmniej jeden: `{'Anna', 'Ewa', 'Jan', 'Kasia', 'Marek', 'Piotr', 'Tomek'}`
- Tylko Python: `{'Anna', 'Piotr'}`
- Dokładnie jeden: `{'Anna', 'Ewa', 'Piotr', 'Tomek'}`

## Ćwiczenie 5: Słownik - dane kontaktowe (łatwe)

Stwórz słownik zawierający dane kontaktowe osoby (imię, nazwisko, email, telefon). Następnie:
- Wyświetl email osoby
- Dodaj klucz 'wiek' z wartością 25
- Zmień numer telefonu
- Usuń klucz 'wiek'

<details>
<summary>Rozwiązanie</summary>

```python
kontakt = {
    'imię': 'Jan',
    'nazwisko': 'Kowalski',
    'email': 'jan.kowalski@example.com',
    'telefon': '123456789'
}

print(kontakt['email'])
kontakt['wiek'] = 25
kontakt['telefon'] = '987654321'
del kontakt['wiek']
print(kontakt)
```
</details>

## Ćwiczenie 6: Operatory arytmetyczne - kalkulator (łatwe)

Napisz prosty kalkulator, który dla dwóch liczb `a = 17` i `b = 5` wykona i wyświetli wyniki następujących operacji:
- Dodawanie
- Odejmowanie
- Mnożenie
- Dzielenie (zwykłe i całkowite)
- Reszta z dzielenia (modulo)
- Potęgowanie

**Oczekiwane wyniki:**
```
17 + 5 = 22
17 - 5 = 12
17 * 5 = 85
17 / 5 = 3.4
17 // 5 = 3
17 % 5 = 2
17 ** 5 = 1419857
```

## Ćwiczenie 7: List comprehension (średnie)

Mając listę liczb od 1 do 20, stwórz nową listę używając list comprehension, która zawiera:
- Kwadraty wszystkich liczb parzystych
- Liczby podzielne przez 3
- Liczby pierwsze (wskazówka: liczba pierwsza dzieli się tylko przez 1 i samą siebie)

**Oczekiwane wyniki:**
- Kwadraty parzystych: `[4, 16, 36, 64, 100, 144, 196, 256, 324, 400]`
- Podzielne przez 3: `[3, 6, 9, 12, 15, 18]`
- Liczby pierwsze: `[2, 3, 5, 7, 11, 13, 17, 19]`

<details>
<summary>Wskazówka do liczb pierwszych</summary>

Możesz napisać pomocniczą funkcję sprawdzającą, czy liczba jest pierwsza:
```python
def czy_pierwsza(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True
```
</details>

## Ćwiczenie 8: Zagnieżdżone słowniki - system studentów (średnie)

Stwórz słownik reprezentujący bazę danych studentów, gdzie kluczem jest numer indeksu, a wartością kolejny słownik zawierający: imię, nazwisko, rok studiów, oceny (lista).

Następnie:
- Dodaj nowego studenta
- Dodaj ocenę dla istniejącego studenta
- Oblicz średnią ocen dla studenta
- Wyświetl wszystkich studentów na 2. roku

```python
studenci = {
    '123456': {'imię': 'Anna', 'nazwisko': 'Nowak', 'rok': 2, 'oceny': [4.5, 5.0, 4.0]},
    '123457': {'imię': 'Piotr', 'nazwisko': 'Wiśniewski', 'rok': 1, 'oceny': [3.5, 4.0]},
}
# Twój kod tutaj
```

## Ćwiczenie 9: CRUD - zarządzanie książkami (średnie/trudne)

Stwórz prosty system CRUD (Create, Read, Update, Delete) do zarządzania biblioteką książek. Książki przechowuj w liście słowników. Każda książka powinna mieć: id, tytuł, autor, rok wydania.

Zaimplementuj funkcje:
- `create_book(biblioteka, id, tytul, autor, rok)` - dodaje książkę
- `read_books(biblioteka)` - wyświetla wszystkie książki
- `read_book(biblioteka, id)` - znajduje książkę po id
- `delete_book(biblioteka, id)` - usuwa książkę

**Przykład użycia:**
```python
biblioteka = []
create_book(biblioteka, 1, "Władca Pierścieni", "J.R.R. Tolkien", 1954)
create_book(biblioteka, 2, "1984", "George Orwell", 1949)
read_books(biblioteka)
delete_book(biblioteka, 2)
```

## Ćwiczenie 10: Operacje na krotce krotek (średnie)

Masz krotkę zawierającą informacje o produktach (nazwa, cena, ilość):
```python
produkty = (
    ('jabłko', 3.5, 10),
    ('banan', 4.2, 5),
    ('gruszka', 5.0, 8),
    ('pomarańcza', 3.8, 12)
)
```

Oblicz:
- Całkowitą wartość magazynu (suma: cena × ilość dla wszystkich produktów)
- Najdroższy produkt
- Produkty, których jest mniej niż 10 sztuk

**Oczekiwane wyniki:**
- Wartość magazynu: 141.6
- Najdroższy: `('gruszka', 5.0, 8)`
- Mało sztuk: `[('banan', 4.2, 5), ('gruszka', 5.0, 8)]`

## Ćwiczenie 11: Dictionary comprehension (średnie)

Używając dictionary comprehension, stwórz:
- Słownik mapujący liczby od 1 do 10 na ich kwadraty
- Słownik z listy słów, gdzie kluczem jest słowo, a wartością jego długość
- Słownik z temperatur w Celsjuszach (0, 10, 20, 30, 40) przeliczonych na Fahrenheity

**Wzór na przeliczenie:** F = C × 9/5 + 32

**Oczekiwane wyniki dla temperatur:**
```python
{0: 32.0, 10: 50.0, 20: 68.0, 30: 86.0, 40: 104.0}
```

<details>
<summary>Rozwiązanie dla kwadratów</summary>

```python
kwadraty = {x: x**2 for x in range(1, 11)}
```
</details>

## Ćwiczenie 12: Metody słowników (łatwe/średnie)

Mając słownik:
```python
oceny = {'matematyka': 4.5, 'fizyka': 5.0, 'chemia': 3.5}
```

Użyj odpowiednich metod słowników, aby:
- Pobrać wartość dla klucza 'informatyka' z wartością domyślną 0.0
- Dodać przedmiot 'biologia' z oceną 4.0 tylko jeśli nie istnieje
- Wyświetlić wszystkie klucze
- Wyświetlić wszystkie wartości
- Wyświetlić wszystkie pary klucz-wartość

<details>
<summary>Rozwiązanie</summary>

```python
oceny = {'matematyka': 4.5, 'fizyka': 5.0, 'chemia': 3.5}

print(oceny.get('informatyka', 0.0))  # 0.0
oceny.setdefault('biologia', 4.0)
print(oceny.keys())      # dict_keys(['matematyka', 'fizyka', 'chemia', 'biologia'])
print(oceny.values())    # dict_values([4.5, 5.0, 3.5, 4.0])
print(oceny.items())     # dict_items([...])
```
</details>

## Ćwiczenie 13: Zaawansowane operacje na listach (trudne)

Masz listę liczb zawierającą duplikaty:
```python
liczby = [1, 2, 3, 2, 4, 5, 1, 6, 3, 7, 8, 5]
```

Napisz kod, który:
- Usuwa duplikaty zachowując kolejność pierwszego wystąpienia
- Znajduje wszystkie liczby występujące więcej niż raz
- Tworzy słownik z liczbą wystąpień każdej liczby

**Oczekiwane wyniki:**
- Bez duplikatów: `[1, 2, 3, 4, 5, 6, 7, 8]`
- Duplikaty: `[1, 2, 3, 5]`
- Liczba wystąpień: `{1: 2, 2: 2, 3: 2, 4: 1, 5: 2, 6: 1, 7: 1, 8: 1}`

<details>
<summary>Wskazówka</summary>

Możesz użyć `dict.fromkeys()` do usunięcia duplikatów z zachowaniem kolejności, lub pętli z osobną listą/zbiorem do śledzenia, co już widziałeś.
</details>

## Dodatkowe materiały

- [Dokumentacja Python - Struktury danych](https://docs.python.org/3/tutorial/datastructures.html)
- [Real Python - Lists and Tuples](https://realpython.com/python-lists-tuples/)
- [Real Python - Dictionaries](https://realpython.com/python-dicts/)
- [Real Python - Sets](https://realpython.com/python-sets/)

# Ćwiczenia z Pythona 

Ćwiczenia nalezy wykonywać od góry do dołu, krok po kroku, aby uniknąć problemów z zależnościami i konfiguracją środowiska.

---

## Ćwiczenie 0 – Pobranie repozytorium

Pobierz repozytorium na swój lokalny komputer.

**Opcja 1: Klonowanie przez Git**
```bash
git clone https://github.com/AdrianRacki/python_exercises_wut_2025.git
cd python_exercises_wut_2025
```

---

## Ćwiczenie 1 – Utworzenie i aktywacja środowiska wirtualnego

W folderze projektu utwórz środowisko wirtualne:
```bash
uv venv
uv init
```

Aktywuj środowisko:

**Windows:**
```bash
.venv\Scripts\activate
```

**macOS / Linux:**
```bash
source .venv/bin/activate
```

Sprawdź, czy środowisko działa:
```bash
python --version
```

Zainiacalizuj uv i zainstaluj ipython
```bash
uv add ipython
```

W folderze `src` utwórz plik `main.py` i dodaj prosty test:
```python
print("Środowisko działa poprawnie")
```

Uruchom skrypt:
```bash
python src/main.py
```

---

## Ćwiczenie 2 – Python vs IPython

Uruchom interpreter Pythona poleceniem:
```bash
python
```

Wykonaj kilka działań arytmetycznych, np. `5 ** 3`, `10 // 3`, `7 % 2`.

Zakończ (`exit()`), uruchom IPythona:
```bash
ipython
```

W IPythonie sprawdź:
- Różnice w sposobie wprowadzania komend (historia, autouzupełnianie, pomoc `?`).
- Zobacz pomoc dla funkcji:
```python
print?
```

---

## Ćwiczenie 3 – Zmienne i operatory przypisania

Utwórz trzy zmienne:
```python
a = 10
b = 3
wynik = a ** b + a / b - (a // b)
```

Wypisz wartości każdej zmiennej w czytelnej formie:
```python
print(f"a = {a}, b = {b}, wynik = {wynik}")
```

- Zmień wartość `a` i `b`, ponownie uruchom program – co się zmienia?
- Dopisz linijkę, która sprawdzi typ zmiennej `wynik`.

---

## Ćwiczenie 4 – Nazwy zmiennych i dobre praktyki

W pliku `naming_test.py` spróbuj stworzyć zmienne o niepoprawnych nazwach, np.:
```python
1liczba = 5
imie-nazwisko = "Jan"
wynik końcowy = 3.5
```

Uruchom skrypt – przeczytaj komunikaty błędów.

Popraw nazwy zgodnie z konwencją:
- tylko litery, cyfry i `_`
- małe litery
- opisowe nazwy (np. `total_sum`, `user_name`)

Dodaj komentarz przy każdej zmiennej, opisujący jej znaczenie.

---

## Ćwiczenie 5 – Typy liczbowe i konwersje

Utwórz zmienne różnych typów:
```python
calkowita = 12
zmiennoprzecinkowa = 4.75
zespolona = 2 + 3j
```

Wyświetl ich typy za pomocą `type()`.

Spróbuj wykonać:
```python
wynik = calkowita + zmiennoprzecinkowa + zespolona
print(wynik)
```

Następnie wykonaj konwersje typów:
- `int()` → `float` → `int`
- `float()` → `string` → `float`

---

## Ćwiczenie 6 – Operatory arytmetyczne i kolejność działań

Dla zmiennych `x = 8`, `y = 3` oblicz:
```python
wynik1 = x + y * 2
wynik2 = (x + y) * 2
wynik3 = x ** y % 5
```

- Wypisz wszystkie wyniki i wyjaśnij w komentarzach, dlaczego są różne.
- Spróbuj zmienić `x` i `y`, zobacz jak wpływa to na wyniki.
- Użyj operatora przypisania `+=` do zwiększenia `x` o 5.

---

## Ćwiczenie 7 – Operatory porównania i logiki

Utwórz zmienne:
```python
wiek = 20
ma_dowod = True
```

Napisz logikę, która sprawdzi:
- Czy osoba jest pełnoletnia.
- Czy może wejść na imprezę (wiek ≥ 18 i ma dowód).

Wypisz wyniki logiczne w stylu:
```python
print("Pełnoletni:", wiek >= 18)
print("Może wejść:", wiek >= 18 and ma_dowod)
```

---

## Ćwiczenie 8 – Operatory logiczne w praktyce

Zdefiniuj zmienne:
```python
student_zalogowany = True
posiada_dostep = False
```

Sprawdź różne kombinacje warunków:
```python
print(student_zalogowany and posiada_dostep)
print(student_zalogowany or posiada_dostep)
print(not student_zalogowany)
```

Napisz krótką logikę decyzyjną:
```python
if student_zalogowany and posiada_dostep:
    print("Witaj w systemie!")
else:
    print("Brak dostępu")
```

---

## Ćwiczenie 9 – Pętla while: liczby i warunki

Utwórz program, który wypisze liczby od 1 do 20, ale tylko te podzielne przez 3.

- Użyj zmiennej `liczba = 1` i pętli `while liczba <= 20:`
- Dodaj warunek logiczny `if liczba % 3 == 0:` do wypisywania.
- Pamiętaj o zwiększaniu licznika (`liczba = liczba + 1`).
- Spróbuj zmienić zakres i warunek — np. wypisywać liczby niepodzielne przez 4.

---

## Ćwiczenie 10 – Mini projekt: suma i średnia liczb

Napisz program, który:
- Dodaje kolejne liczby całkowite od 1 do n (użytkownik podaje n).
- Wykorzystuje pętlę `while` (bez `break` ani `continue`).
- Na końcu oblicza i wyświetla:
  - sumę liczb,
  - średnią arytmetyczną.

**Przykład:**
```python
n = int(input("Podaj liczbę n: "))
licznik = 1
suma = 0

while licznik <= n:
    suma = suma + licznik
    licznik = licznik + 1

srednia = suma / n
print(f"Suma: {suma}, Średnia: {srednia}")
```

---

## Zadanie dodatkowe:

Spróbuj zmodyfikować program tak, by obliczał tylko sumę liczb parzystych lub nieparzystych od 1 do n.
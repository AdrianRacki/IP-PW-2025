# Ćwiczenia z Pythona – Lab 3-4

**Uwaga:** Przed rozpoczęciem upewnij się, że masz skonfigurowane środowisko wirtualne (Ćwiczenie 0 z Lab 1-2).

Ćwiczenia należy wykonywać od góry do dołu, krok po kroku.

---

## Ćwiczenie 1 – Pierwsza funkcja

Napisz funkcję `powitanie()`, która wypisze na ekran tekst "Witaj w świecie funkcji!".

```python
def powitanie():
    print("Witaj w świecie funkcji!")

powitanie()
```

Uruchom program i sprawdź, czy funkcja działa poprawnie.

---

## Ćwiczenie 2 – Funkcja z parametrem

Napisz funkcję `powitaj_osobe(imie)`, która przyjmuje imię jako argument i wypisuje powitanie.

```python
def powitaj_osobe(imie):
    print("Witaj,", imie, "!")

powitaj_osobe("Anna")
powitaj_osobe("Marek")
```

- Wywołaj funkcję kilka razy z różnymi imionami.
- Co się stanie, jeśli nie podasz argumentu?

---

## Ćwiczenie 3 – Funkcja zwracająca wartość

Napisz funkcję `suma(a, b)`, która zwraca sumę dwóch liczb.

```python
def suma(a, b):
    return a + b

wynik = suma(5, 7)
print("Suma:", wynik)
```

Następnie napisz podobne funkcje dla:
- odejmowania
- mnożenia
- dzielenia (pamiętaj o przypadku dzielenia przez 0!)

---

## Ćwiczenie 4 – Podstawy instrukcji if

Napisz program, który sprawdza, czy liczba jest dodatnia, ujemna czy równa zero.

```python
liczba = int(input("Podaj liczbę: "))

if liczba > 0:
    print("Liczba jest dodatnia")
elif liczba < 0:
    print("Liczba jest ujemna")
else:
    print("Liczba jest równa zero")
```

Przetestuj program dla różnych wartości.

---

## Ćwiczenie 5 – Funkcja z warunkiem

Napisz funkcję `sprawdz_wiek(wiek)`, która:
- Zwraca "Niepełnoletni" dla wieku < 18
- Zwraca "Pełnoletni" dla wieku >= 18 i < 65
- Zwraca "Senior" dla wieku >= 65

**Przykład użycia:**
```python
print(sprawdz_wiek(15))  # Niepełnoletni
print(sprawdz_wiek(30))  # Pełnoletni
print(sprawdz_wiek(70))  # Senior
```

---

## Ćwiczenie 6 – Stringi: apostrofy vs cudzysłowy

Przetestuj różne sposoby definiowania stringów:

```python
tekst1 = 'To jest tekst w apostrofach'
tekst2 = "To jest tekst w cudzysłowach"
tekst3 = "Użyłem apostrofu: it's working"
tekst4 = 'Użyłem cudzysłowu: "Hello"'
```

Wypisz wszystkie teksty i sprawdź:
- Co się stanie, jeśli użyjesz apostrofu wewnątrz tekstu w apostrofach bez znaku ucieczki?
- Kiedy musisz użyć `\` (backslash)?

---

## Ćwiczenie 7 – Długość stringa i podstawowe operacje

```python
imie = "Python"
nazwisko = "Programming"

# Długość
print("Długość imienia:", len(imie))
print("Długość nazwiska:", len(nazwisko))

# Łączenie stringów
pelne_imie = imie + " " + nazwisko
print(pelne_imie)

# Powtarzanie
linia = "-" * 20
print(linia)
```

**Zadanie:** Napisz program, który:
- Pobiera od użytkownika imię i nazwisko
- Wypisuje pełne imię
- Wypisuje liczbę znaków w pełnym imieniu (ze spacją)
- Tworzy ozdobną ramkę z `=` o długości równej pełnemu imieniu

---

## Ćwiczenie 8 – Indeksowanie stringów

```python
slowo = "Python"

print(slowo[0])   # P
print(slowo[1])   # y
print(slowo[-1])  # n (ostatni znak)
print(slowo[-2])  # o (przedostatni)
```

**Zadanie:** Dla słowa "Programowanie":
- Wypisz pierwszą literę
- Wypisz ostatnią literę
- Wypisz trzecią literę
- Spróbuj wypisać literę o indeksie większym niż długość słowa – co się stanie?

---

## Ćwiczenie 9 – Slicing (wycinki)

```python
tekst = "Python Programming"

print(tekst[0:6])    # Python
print(tekst[7:18])   # Programming
print(tekst[:6])     # Python (od początku)
print(tekst[7:])     # Programming (do końca)
print(tekst[::2])    # co druga litera
print(tekst[::-1])   # odwrócony tekst
```

**Zadanie:** Dla słowa "Informatyka":
- Wypisz pierwsze 5 znaków
- Wypisz ostatnie 4 znaki
- Wypisz co trzecią literę
- Odwróć całe słowo

---

## Ćwiczenie 10 – Funkcja sprawdzająca palindrom

Napisz funkcję `czy_palindrom(slowo)`, która sprawdza, czy słowo jest palindromem (czyta się tak samo od przodu i od tyłu).

**Wskazówka:** Użyj slicingu do odwrócenia słowa i porównaj z oryginałem.

**Przykład:**
```python
print(czy_palindrom("kajak"))  # True
print(czy_palindrom("python")) # False
```

---

## Ćwiczenie 11 – Funkcja z wieloma warunkami

Napisz funkcję `ocena_na_slowa(ocena)`, która:
- Przyjmuje ocenę numeryczną (2-5)
- Zwraca jej słowny odpowiednik:
  - 5 → "celujący"
  - 4 → "dobry"
  - 3 → "dostateczny"
  - 2 → "niedostateczny"
  - inna wartość → "nieprawidłowa ocena"

Przetestuj funkcję dla różnych wartości.

---

## Ćwiczenie 12 – Funkcja formatująca dane

Napisz funkcję `wizytowka(imie, nazwisko, wiek)`, która zwraca sformatowany string:

**Oczekiwany wynik:**
```
wizytowka("Jan", "Kowalski", 25)
# Zwraca:
# ====================
# Jan Kowalski
# Wiek: 25 lat
# ====================
```

**Wskazówka:** Użyj operatora `+` i `*` do tworzenia ramki oraz `\n` dla nowych linii.

---

## Ćwiczenie 13 – Kalkulator z wyborem operacji

Napisz program, który:
1. Pobiera dwie liczby od użytkownika
2. Pyta o operację: +, -, *, /
3. Wykonuje odpowiednią operację używając if/elif/else
4. Wypisuje wynik

**Rozszerzenie:** Zamień to w funkcję `kalkulator(a, b, operacja)`.

---

## Ćwiczenie 14 – Metoda Newtona-Raphsona (NIEOBOWIĄZKOWE)

**Zadanie zaawansowane:** Zaimplementuj metodę Newtona-Raphsona do znajdowania miejsc zerowych funkcji.

**Algorytm:**
```
x_{n+1} = x_n - f(x_n) / f'(x_n)
```

Napisz funkcję `newton_raphson(f, df, x0, tolerancja, max_iteracji)`, gdzie:
- `f` – funkcja, dla której szukamy miejsca zerowego
- `df` – pochodna funkcji `f`
- `x0` – punkt startowy
- `tolerancja` – dokładność wyniku
- `max_iteracji` – maksymalna liczba iteracji

**Przykład:**
```python
def f(x):
    return x**2 - 4

def df(x):
    return 2*x

wynik = newton_raphson(f, df, 3, 0.0001, 100)
print("Miejsce zerowe:", wynik)
# Dla x0=3 powinno zbiegać do 2.0
# Dla x0=-3 powinno zbiegać do -2.0
```

**Wyzwanie dodatkowe:** 
- Porównaj liczbę iteracji potrzebnych w metodzie bisekcji vs Newton-Raphson
- Co się dzieje, gdy pochodna w punkcie jest bliska zeru?
- Przetestuj dla funkcji `f(x) = x**3 - 2*x - 5`

---

## Zadania dodatkowe:

1. **Walidacja PESEL:** Napisz funkcję, która sprawdza, czy podany ciąg znaków ma długość 11 i składa się tylko z cyfr.

2. **Cenzura słów:** Napisz funkcję `cenzuruj(tekst, slowo_zakazane)`, która zamienia każdą literę zakazanego słowa na `*` w tekście.

3. **Formatowanie liczby:** Napisz funkcję, która dodaje spacje co 3 cyfry w dużej liczbie (np. `1000000` → `"1 000 000"`).

4. **Mini-gra:** Napisz grę w zgadywanie liczby, gdzie komputer losuje liczbę (użyj `import random; random.randint(1, 100)`), a użytkownik próbuje ją odgadnąć. Program podpowiada "za mało" lub "za dużo".

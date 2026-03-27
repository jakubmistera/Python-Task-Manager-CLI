# 📋 System Zarządzania Zadaniami (Python CLI)

Projekt akademicki realizowany w zespole projektowym (rola: Lider zespołu). Aplikacja w języku Python służąca do zarządzania zadaniami, przypisywania ról oraz śledzenia postępów prac. Interfejs oparty na wierszu poleceń (CLI) z wykorzystaniem modułu `argparse`.

## 🎯 Cel projektu
Stworzenie w pełni funkcjonalnego menedżera zadań obsługującego zadania indywidualne i zespołowe, z uwzględnieniem różnych priorytetów, terminów realizacji oraz statusów. Projekt stanowił praktyczne ćwiczenie z zakresu programowania obiektowego (OOP) oraz dobrych praktyk pisania kodu (Clean Code).

## 🛠 Wykorzystane technologie i koncepcje (Python)
Projekt demonstruje znajomość średniozaawansowanych i zaawansowanych mechanizmów języka Python:
* **Programowanie Obiektowe (OOP):** Dziedziczenie (klasa bazowa `Task` oraz klasy pochodne `PersonalTask` i `TeamTask`).
* **Dekoratory:** Wykorzystanie `@property` do enkapsulacji i zarządzania dostępem do atrybutów (np. walidacja statusu zadania).
* **Menedżery kontekstu:** Bezpieczne operacje wejścia/wyjścia (I/O) przy zapisie i odczycie danych do/z pliku.
* **Testowanie (TDD):** Implementacja testów jednostkowych za pomocą frameworka `pytest` (weryfikacja funkcji dodawania i edycji zadań).
* **Obsługa wyjątków:** Bloki `try/except` chroniące przed nieprawidłowym formatem danych wejściowych z konsoli.
* **Typowanie i Dokumentacja:** Wykorzystanie Type Hints (adnotacji typów) oraz Docstringów opisujących klasy i metody.

## ⚙️ Architektura Systemu (Diagram Klas)

Struktura opiera się na relacjach dziedziczenia i kompozycji:
1. `Task` - klasa abstrakcyjna / nadrzędna (tytuł, opis, data, priorytet, status).
2. `PersonalTask` - dziedziczy po `Task`, rozszerzona o atrybut `assignee` (konkretny członek zespołu).
3. `TeamTask` - dziedziczy po `Task`, rozszerzona o listę `team_members` (wielu wykonawców).
4. `TaskManager` - kontroler zarządzający kolekcją zadań (dodawanie, usuwanie, filtrowanie, zapis/odczyt plików).

<img width="878" height="995" alt="image" src="https://github.com/user-attachments/assets/2add7e54-e79a-445b-94ea-8eeeb43f7738" />

## 🚀 Użycie programu (Interfejs CLI)

<img width="945" height="553" alt="image" src="https://github.com/user-attachments/assets/e012f8f4-61b9-4d48-b52b-166a98930664" />

Aplikacja obsługuje argumenty wiersza poleceń dzięki bibliotece `argparse`. Przykłady wywołań:

**Dodanie zadania indywidualnego:**
```bash
python main.py --add_personal --title "Przygotowanie prezentacji" --description "Slajdy dotyczące układów sterowania" --due_date "2025-02-01" --priority 1 --status "pending" --assignee "Damian G"



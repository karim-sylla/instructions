# Aplikacja Webowa GPT z Flask

## Spis treści
1. [Wstęp](#wstęp)
2. [Wymagania wstępne](#wymagania-wstępne)
3. [Krok 1: Utworzenie folderu projektu](#krok-1-utworzenie-folderu-projektu)
4. [Krok 2: Plik requirements.txt (rozszerzony)](#krok-2-plik-requirementstxt-rozszerzony)
5. [Krok 3: Plik .env (bez zmian)](#krok-3-plik-env-bez-zmian)
6. [Krok 4: Konfiguracja i aktywacja środowiska](#krok-4-konfiguracja-i-aktywacja-środowiska)
7. [Krok 5: Instalacja pakietów](#krok-5-instalacja-pakietów)
8. [Krok 6: Generowanie aplikacji z pomocą GitHub Copilot](#krok-6-generowanie-aplikacji-z-pomocą-github-copilot)
9. [Krok 7: Weryfikacja struktury i uruchomienie aplikacji](#krok-7-weryfikacja-struktury-i-uruchomienie-aplikacji)
10. [Słowniczek pojęć](#słowniczek-pojęć)
11. [Podsumowanie komend](#podsumowanie-komend)

## Wstęp

Ta instrukcja przeprowadzi Cię przez proces tworzenia bardziej zaawansowanej aplikacji, będącej rozszerzeniem poprzedniego przykładu. Zamiast prostej aplikacji konsolowej, stworzymy **aplikację webową Flask** z graficznym interfejsem użytkownika dostępnym przez przeglądarkę. Rozwiązanie to oferuje znacznie więcej możliwości, takich jak dostosowywanie parametrów modelu, wybór formatów odpowiedzi i personalizację wiadomości systemowych.

>**Uwaga dla tych, którzy wykonali poprzednią instrukcję:** Proces konfiguracji środowiska jest bardzo podobny do tego z aplikacji konsolowej. Większość zmian dotyczy struktury projektu i samego kodu aplikacji. Jeśli rozumiesz już podstawy tworzenia środowiska Python, ten projekt będzie naturalnym rozszerzeniem Twoich umiejętności.

## Wymagania wstępne

Wymagania są identyczne jak w przypadku poprzedniej instrukcji:
- Visual Studio Code (VS Code)
- Python 
- Klucz API OpenAI
- GitHub Copilot lub dostęp do modelu GPT, który można wykorzystać do generowania kodu (np. ChatGPT)

## Krok 1: Utworzenie folderu projektu

Podobnie jak w poprzednim przykładzie, utwórz nowy folder dla projektu (np. "flask_gpt") i otwórz go w VS Code. Ten proces został szczegółowo wyjaśniony w pierwszej instrukcji.

## Krok 2: Plik requirements.txt (rozszerzony)

### Cel:
Stworzenie pliku z rozszerzoną listą zależności dla aplikacji webowej.

### Instrukcja:
1. Utwórz plik "requirements.txt" podobnie jak w poprzedniej instrukcji.
2. W pliku wpisz następujące linie:

```
flask
requests
python-dotenv
tiktoken
```

3. Zapisz plik (Ctrl+S).

### Co nowego:
W tym przypadku używamy tych samych bibliotek co poprzednio, ale będziemy ich używać inaczej:
- `flask`: Teraz będzie służyć do tworzenia pełnoprawnej aplikacji webowej, a nie tylko prostego skryptu
- `tiktoken`: Tym razem wykorzystamy ją do śledzenia liczby tokenów, aby monitorować użycie API

## Krok 3: Plik .env (bez zmian)

Plik .env tworzymy identycznie jak w poprzedniej instrukcji. Umieść w nim swój klucz API OpenAI:

```
OPENAI_API_KEY=twoj_klucz_api
```

Zastosowanie tego pliku jest takie samo jak poprzednio - chroni Twój klucz API przed bezpośrednim umieszczeniem w kodzie źródłowym.



## Krok 4: Konfiguracja i aktywacja środowiska

### Cel:
Skonfigurowanie i aktywacja wirtualnego środowiska Python.

### Instrukcja:
1. Utwórz i aktywuj wirtualne środowisko tak samo jak w poprzednim przykładzie:
```
python -m venv venv
.\venv\Scripts\Activate
```

2. Po aktywacji na początku linii w terminalu powinien pojawić się prefix "(venv)".

### Przypomnienie:
Ten proces jest identyczny jak w poprzedniej instrukcji. Wirtualne środowisko oddziela zależności tego projektu od innych projektów Python na Twoim komputerze. Jest to szczególnie ważne w aplikacjach Flask, które często wymagają konkretnych wersji bibliotek.

## Krok 5: Instalacja pakietów

### Cel:
Zainstalowanie wymaganych bibliotek.

### Instrukcja:
1. Upewnij się, że wirtualne środowisko jest aktywne (widoczny prefix "(venv)").
2. Zainstaluj biblioteki używając tej samej komendy co poprzednio:

```
pip install -r requirements.txt
```

### Wyjaśnienie:
Proces instalacji jest taki sam jak w poprzedniej instrukcji, jednak w tym przypadku będziemy wykorzystywać więcej funkcjonalności tych bibliotek do budowy aplikacji webowej.

## Krok 6: Generowanie aplikacji z pomocą GitHub Copilot

### Cel:
Wykorzystanie GitHub Copilot do wygenerowania aplikacji webowej.

### Instrukcja:
1. Utwórz nowy plik `app.py` w głównym folderze projektu.
2. W pliku `app.py` wprowadź następujący prompt dla GitHub Copilot:

```markdown
# Prompt dla GitHub Copilot

Stwórz kompletną aplikację Flask do interakcji z modelami OpenAI przez przeglądarkę. Aplikacja powinna:

1. Mieć interfejs graficzny z dwoma głównymi sekcjami: panel boczny z ustawieniami i główny obszar do wprowadzania pytań.
2. Pozwalać na wybór modelu OpenAI (gpt-4o-mini, gpt-4o) i dostosowanie parametrów generowania odpowiedzi (temperatura, liczba tokenów, itp.)
3. Pozwalać użytkownikowi na wprowadzenie wiadomości systemowej dla modelu.
4. Wyświetlać odpowiedzi modelu oraz informacje o liczbie użytych tokenów.
5. Umożliwiać wybór między zwykłą odpowiedzią tekstową a odpowiedzią w formacie JSON.
6. Obsługiwać błędy i zawierać zabezpieczenia.

Pobieraj klucz API z pliku .env, używając bibliotek wymienionych w requirements.txt. Utwórz niezbędną strukturę folderów, w tym 'templates' i 'static'.
```

3. Pozwól GitHub Copilot dokończyć kod i stworzyć wszystkie niezbędne pliki.

### Co powinieneś otrzymać:
GitHub Copilot powinien stworzyć kompletną aplikację, zawierającą:

1. Plik `app.py` z pełną logiką aplikacji
2. Niezbędną strukturę folderów (templates, static)
3. Wszystkie wymagane pliki szablonów HTML oraz zasoby CSS/JavaScript 

Wygenerowany kod powinien być gotowy do uruchomienia, możesz jednak potrzebować dokonać drobnych poprawek zależnie od twoich potrzeb.

## Krok 7: Weryfikacja struktury i uruchomienie aplikacji

### Cel:
Sprawdzenie wygenerowanej struktury projektu i uruchomienie aplikacji.

### Instrukcja:
1. Po wygenerowaniu kodu przez GitHub Copilot, sprawdź utworzoną strukturę projektu:
   - Upewnij się, że został utworzony folder `templates` zawierający pliki HTML
   - Sprawdź, czy został utworzony folder `static` do przechowywania plików CSS i JavaScript
   - Jeśli któryś z tych folderów nie został utworzony, utwórz go ręcznie

2. Upewnij się, że wirtualne środowisko jest aktywne.

3. Uruchom aplikację Flask komendą:
```
python app.py
```

4. Po uruchomieniu, w terminalu powinieneś zobaczyć komunikat podobny do:
```
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

5. Otwórz przeglądarkę i przejdź pod adres http://127.0.0.1:5000/

### Testowanie aplikacji:
1. Wypróbuj interfejs, wprowadzając różne pytania i zmieniając parametry modelu.
2. Przetestuj różne formaty odpowiedzi, jeśli są dostępne.
3. Sprawdź, czy wyświetlane są statystyki tokenów po otrzymaniu odpowiedzi.

### Przykładowe pytania testowe:
- "Wytłumacz czym jest framework Flask w kilku punktach."
- "Jakie są główne różnice między modelami gpt-4o-mini a gpt-4o?"
- "Wymień 5 przykładowych zastosowań API OpenAI w e-commerce."

## Słowniczek pojęć

W tej aplikacji pojawiają się zarówno pojęcia znane z poprzedniej instrukcji, jak i nowe terminy:

- **Flask**: Framework webowy w Pythonie do tworzenia aplikacji internetowych.
- **Template/Szablon**: Plik HTML z dynamicznymi elementami, które są wypełniane danymi przez Flask.
- **Route/Trasa**: Zdefiniowany adres URL obsługiwany przez aplikację Flask.
- **Endpoint**: Punkt końcowy API, pod którym dostępna jest określona funkcjonalność.
- **AJAX/Fetch**: Technologie JavaScript do asynchronicznego pobierania danych bez przeładowywania strony.
- **JSON Schema**: Struktura definiująca format danych JSON, którą model GPT ma wypełnić.
- **GitHub Copilot**: Narzędzie AI do generowania kodu na podstawie opisów lub kontekstu.

## Podsumowanie komend

```
# Utworzenie wirtualnego środowiska
python -m venv venv

# Aktywacja wirtualnego środowiska
.\venv\Scripts\Activate

# Instalacja wymaganych pakietów
pip install -r requirements.txt

# Uruchomienie aplikacji
python app.py
```
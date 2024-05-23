# Interpreter Języka Emotikonów

Celem tego projektu jest stworzenie interpretera języka emotikonowego, który służyłby dzieciom do łatwej nauki programowania w prosty i angażujący sposób. Emotikony są językiem XXI wieku, dlatego uważamy że dzieciom zdecydowanie ułatwi to zrozumienie logiki programowania. 
- Rodzaj translatora: Kompilator
- Planowany wynik działania programu: Kompilator EmojiReader do języka Python (wynik w postaci pliku .py)
## Język Implementacji
- Python 3

## Narzędzia i Biblioteki
- ANTLR4: [Oficjalna strona ANTLR4](https://www.antlr.org/)
  
- GraphViz https://graphviz.org/

## Instalacja i Uruchomienie

1. **Klonowanie Repozytorium**:
   ```sh
   git clone <adres-repozytorium>
   cd <katalog-repozytorium>
   ```
2.**Instalacja Zależności**:
  Zainstaluj środowisko wykonawcze ANTLR4 dla Pythona używając pip:
  ```sh
  pip install antlr4-python3-runtime==4.13.1
  ```
3.**Uruchomienie Interpretera**:
  Uruchom główny skrypt:
  ```sh
  python main.py
```
## Użytkowanie
## 1. Identyfikacja Tokenów
```
    "IDENTIFIER" : "[A-Za-z]+[A-za-z0-9]*",              # Identifiers (variables, function names, etc.)
    "NUMBER"     : "[0-9]+{.}?[0-9]+",                   # Numeric literals
    "STRING"     : "️ " [A-za-z0-9-_\]" ",                # String literals
    "NEWLINE"    : "🗽",                                 # Newline tokens
    "PLUS"       : "➕",                                 # Addition operator
    "MINUS"      : "➖",                                 # Subtraction operator
    "MULTIPLY"   : "✖️",                                 # Multiplication operator
    "DIVIDE"     : "➗",                                 # Division operator
    "EQUAL"      : "🟰",                                 # Assignment operator
    "GREATER"    : "🐉",                                 # Greater operator
    "SMALLER"    : "🐁",                                 # Smaller operator
    "EGREATER"   : "🐆",                                 # GreaterOrEqual operator
    "ESMALLER"   : "🐿️",                                 # SmallerOrEqual operator
    "MOD"        : "%",                                   # Modulo
    "LPAR"       : "🌜",                                 # Left parenthesis
    "RPAR"       : "🌛",                                 # Right parenthesis
    "LSQB"       : "🫲",                                 # Left square bracket
    "RSQB"       : "🫱",                                 # Right square bracket
    "COMMA"      : "📎",                                 # Comma
    "COLON"      : "🖇️",                                 # Colon
    "SEMI"       : "📌",                                 # Semicolon
    "QUOTE"      : "🎬 "                                 # Quote
    "WS"         : "[ \t\r\n]+",                         # Whitespace
    "OR"         : "🕵️‍♀️",                                 # Or (|| in other programming languages)
    "AND"        : "👭",                                 # And (&& in other programming languages)
    "PERCENT"    : "🍾",                                 # Percent (%)
    "COMMENT"    : "☁️[A-Za-z0-9_/-*]*☁️",               # Commment
    "PRINT"      : "🖨️",                                 # Print
    "NOT"        : "❗",                                 # Not
    "IF"         : "❓",                                 # If
    "ELSE"       : "❗❗",                               # Else
    "ELSIF"      : "❓❗",                               # Elsif
    "FOR"        : "🎁",                                 # For
    "IN"         : "📭",                                 # In
    "RANGE"      : "🏔️",                                 # Range
    "ENUMERATE"  : "📻",                                 # Enumerate
    "WHILE"      : "🌪️",                                 # While
    "SWITCH"     : "📋",                                 # Switch
    "CASE"       : "✅",                                 # Case
    "BREAK"      : "🚦",                                 # Break
    "CONTINUE"   : "💆",                                 # Continue
    "RETURN"     : "🪃",                                 # Return
    "DEF"        : "💡",                                 # Def
    "TRUE"       : "👍",                                 # True
    "FALSE       : "👎",                                 # False
    "TRY"        : "🔮",                                 # Try
    "CATCH"      : "🎣",                                 # Catch
    "FINALLY"    : "⌛",                                 # Finally
    "RAISE"      : "🌅",                                 # Raise
    "CONST"      : "💀",                                 # Constant
    "IMPORT"     : "🌎",                                 # Import
    "FROM"       : "🚛",                                 # From
    "LAMBDA"     : "🌈",                                 # Lambda
    "NONE"       : "🗑️",                                 # None
    "ECOMPLEMENT": "〰",                                  # Complement
    "ARROW"      : "->",                                  # Arrow
```

## 2. Gramatyka:



## 3. Opis i schemat struktury programu:
- Kod źródłowy jest wczytywany z pliku lub z interfejsu.
- Przechodzi przez skaner, który przekształca go na tokeny.
- Następnie tokeny są analizowane przez parser, który przyporządkowuje je do odpowiednich konstrukcji gramatycznych.
- Na podstawie parsowania, generowane są odpowiednie instrukcje w języku Python.
- Implementacja w języku Python obejmuje również klasę Listenera, która przetwarza drzewo parsowania i generuje kod w języku Python.

 ## 4. Informacje o stosowanych generatorach skanerów/parserów, pakietach zewnętrznych
ANTLR to generator parserów do czytania, przetwarzania, wykonywania lub tłumaczenia tekstu strukturalnego lub plików binarnych. Jest szeroko stosowany do tworzenia języków, narzędzi i frameworków. Na podstawie gramatyki ANTLR generuje parser, który może budować drzewa parsowania, a także generuje interfejs słuchacza (lub gościa), który ułatwia reagowanie na rozpoznawanie interesujących fraz.


## 5. Informacje o zastosowaniu specyficznych metod rozwiązania problemu: 
Język, który stworzyliśmy na potrzeby tego projektu jest językiem ułatwiającym naukę programowania. Poprzez zdefiniowanie słów kluczowych w postaci emotikonów młodsze osoby nie mają problemu ze zrozumieniem koncepcji ich działania. To rozwiązanie pozwoli dzieciom oswajać się z programowaniem już od najmłodszych lat.


## 6. Krótka instrukcja obsługi:
Na początku musimy pobrać kompletny plik JAR ANTLR. Po stworzeniu pliku .g4 składającego się z opisanych tokenów i gramatyki należy go skompilować w użyciem pobranego wcześniej JAR'a ANTLR. Używamy polecenia:


Zidentyfikowane tokeny zostaną zapisane do pliku tokens.txt.

-**Drzewo Parsowania**:

Wynik analizy składniowej (drzewo parsowania) zostanie zapisany w diretory Results, a dokładniej do pliku parsing_tree.txt, natomiast wersja png - w pliku 'dot parsing tree'. 

-**Kod wykonywalny**:

Wykonywalny kod przetłumaczony z emotikonowego języka programowania znajduje się w katalogu Results

-**Edycja Pliku Testowego**:

Możesz dostosować plik testowy do swoich potrzeb, aby przetestować różne aspekty interpretera.


## Autorzy i Kontakt

**Martyna Baran**: martynab@student.agh.edu.pl

**Gabriela Czapska**: czapska@student.agh.edu.pl


Projekt wykonany na potrzeby przedmiotu "Teoria kompilacji i kompilatory" na kierunku Informatyka i Systemy Inteligentne w Akademii Górniczo-Hutniczej w Krakowie.

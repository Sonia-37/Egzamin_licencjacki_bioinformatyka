# Warsztat programisty — kompletne notatki na egzamin


## Spis treści

1. [Wstęp: informatyka, algorytmy, złożoność](#1-wstep-algorytmy-zlozonosc)
2. [Systemy pozycyjne i reprezentacja liczb](#2-systemy-pozycyjne)
3. [Algorytmy klasyczne: gcd, wyszukiwanie, sortowanie](#3-algorytmy-klasyczne)
4. [Teoria języków formalnych i automatów](#4-jezyki-formalne-i-automaty)
5. [Wyrażenia regularne w praktyce](#5-wyrazenia-regularne)
6. [Systemy operacyjne, procesy, wątki](#6-systemy-operacyjne)
7. [Linux: pliki, strumienie, filtry](#7-linux)
8. [Skrypty powłoki (bash)](#8-skrypty-powloki)
9. [Narzędzia: vi, grep, sed, awk, make](#9-narzedzia)
10. [Git i praca zespołowa, etyka](#10-git-praca-zespolowa)
11. [Kompilacja: gcc](#11-kompilacja-gcc)
12. [LaTeX](#12-latex)
13. [Teoria informacji: entropia, kodowanie, kompresja, szyfrowanie](#13-teoria-informacji)
14. [Ściąga zbiorcza](#14-sciaga)

---

## 1. Wstęp: informatyka, algorytmy, złożoność

### 1.1. Podstawowe pojęcia

- **Informatyka** — nauka o przetwarzaniu informacji za pomocą automatycznych metod (algorytmów) i maszyn (komputerów).
- **Algorytm** — skończony, jednoznaczny ciąg instrukcji rozwiązujący zadany problem dla dowolnych poprawnych danych wejściowych. Cechy: skończoność, określoność (jednoznaczność), poprawne wejście/wyjście, efektywność.
- **Program** — zapis algorytmu w konkretnym języku programowania, wykonywalny przez komputer.
- **Struktura danych** — sposób organizacji danych w pamięci (tablica, lista, stos, kolejka, drzewo, graf, tablica haszująca). Dobór struktury wpływa na efektywność algorytmu (stąd słynne: *algorytmy + struktury danych = programy*, N. Wirth).

### 1.2. Złożoność obliczeniowa

Mierzymy, **jak rośnie** czas (lub pamięć) algorytmu wraz z rozmiarem danych $n$. Interesuje nas zachowanie asymptotyczne (dla dużych $n$), niezależne od sprzętu.

**Notacja $O$ (duże O — ograniczenie górne):** $f(n)=O(g(n))$, gdy od pewnego $n_0$ zachodzi $f(n)\le c\cdot g(n)$ dla pewnej stałej $c>0$. Mówi "rośnie nie szybciej niż $g$".

Inne notacje: $\Omega$ (dolne ograniczenie, "nie wolniej niż"), $\Theta$ (dokładny rząd, $O$ i $\Omega$ jednocześnie).

**Typowe klasy złożoności (od najlepszej):**

| Złożoność | Nazwa | Przykład |
|---|---|---|
| $O(1)$ | stała | dostęp do elementu tablicy |
| $O(\log n)$ | logarytmiczna | wyszukiwanie binarne |
| $O(n)$ | liniowa | wyszukiwanie liniowe |
| $O(n\log n)$ | liniowo-logarytmiczna | sortowanie przez scalanie |
| $O(n^2)$ | kwadratowa | sortowanie bąbelkowe |
| $O(2^n)$ | wykładnicza | przegląd wszystkich podzbiorów |
| $O(n!)$ | silnia | przegląd wszystkich permutacji |

**Złożoność:** pesymistyczna (najgorszy przypadek), średnia, optymistyczna (najlepszy). Na egzaminie najczęściej liczy się **pesymistyczna**.

> **Pułapka:** $O$ pomija stałe i niższe rzędy: $3n^2+5n+7 = O(n^2)$. Ale to nie znaczy, że stałe nie mają znaczenia w praktyce dla małych $n$.

### 1.3. Problemy obliczalne i nieobliczalne (teoria obliczeń)

- Nie każdy problem da się rozwiązać algorytmicznie. Klasyczny przykład **nierozstrzygalny**: **problem stopu** (czy dany program zatrzyma się dla danego wejścia) — udowodniono (Turing), że nie istnieje algorytm rozstrzygający to dla wszystkich programów.
- Klasy złożoności **P** (rozwiązywalne w czasie wielomianowym) i **NP** (rozwiązanie da się wielomianowo *sprawdzić*). Otwarty problem **P vs NP** to jeden z najważniejszych w informatyce.

---

## 2. Systemy pozycyjne

### 2.1. Idea systemu pozycyjnego

W systemie o **podstawie** $b$ liczba zapisana cyframi $d_k d_{k-1}\dots d_1 d_0$ oznacza:
$$d_k b^k + d_{k-1}b^{k-1} + \dots + d_1 b^1 + d_0 b^0.$$
Wartość cyfry zależy od jej **pozycji** (stąd "pozycyjny"). Cyfry: $0,1,\dots,b-1$.

| System | Podstawa | Cyfry | Zastosowanie |
|---|---|---|---|
| dwójkowy (binarny) | 2 | 0,1 | wewnętrzna reprezentacja w komputerze |
| ósemkowy (oktalny) | 8 | 0–7 | uprawnienia w Linuksie |
| dziesiętny | 10 | 0–9 | codzienne |
| szesnastkowy (heksadecymalny) | 16 | 0–9, A–F | adresy, kolory, zrzuty pamięci |

W hex: $A=10, B=11, C=12, D=13, E=14, F=15$.

### 2.2. Konwersje — metody (typowe zadanie!)

**Z systemu $b$ na dziesiętny:** podstaw do wzoru pozycyjnego (zsumuj cyfry × potęgi podstawy).
> $1011_2 = 1\cdot8 + 0\cdot4 + 1\cdot2 + 1\cdot1 = 11_{10}$.
> $2F_{16} = 2\cdot16 + 15 = 47_{10}$.

**Z dziesiętnego na system $b$:** **dziel przez $b$, zbieraj reszty**, czytaj reszty **od dołu**.
> $13_{10}$ na binarny: $13:2=6$ r.$1$; $6:2=3$ r.$0$; $3:2=1$ r.$1$; $1:2=0$ r.$1$ → czytamy od dołu: $1101_2$.

**Binarny ↔ szesnastkowy (szybko!):** grupuj bity po **4** (bo $16=2^4$). Binarny ↔ ósemkowy: po **3** (bo $8=2^3$).
> $1011\,0110_2 = \mathtt{B6}_{16}$ (1011=B, 0110=6).

**Część ułamkowa na system $b$:** **mnóż przez $b$, zbieraj części całkowite** (od góry).
> $0.625_{10}$ na binarny: $0.625\cdot2=1.25$→1; $0.25\cdot2=0.5$→0; $0.5\cdot2=1.0$→1 → $0.101_2$.

### 2.3. Arytmetyka binarna

Dodawanie jak w dziesiętnym, z przeniesieniem przy $1+1=10_2$:
```
  1011  (11)
+ 0110  (6)
------
 10001  (17)
```
Mnożenie/odejmowanie analogicznie. Przesunięcie bitowe w lewo o 1 = mnożenie przez 2, w prawo = dzielenie całkowite przez 2.

### 2.4. Reprezentacja liczb całkowitych — kod uzupełnień do dwóch (U2)

Komputery przechowują liczby ze znakiem najczęściej w **kodzie uzupełnień do dwóch** (two's complement). Dla $n$ bitów:
- zakres: od $-2^{n-1}$ do $2^{n-1}-1$ (np. 8 bitów: $-128$ do $127$),
- najstarszy bit to **bit znaku** (1 = liczba ujemna),
- **negacja liczby:** zaneguj wszystkie bity i **dodaj 1**.

> **Przykład (8 bitów):** $5 = 00000101$. $-5$: neguj → $11111010$, +1 → $11111011$.

Zaleta U2: dodawanie i odejmowanie działa **tak samo** dla liczb dodatnich i ujemnych (jeden układ sumujący), istnieje jedno zero. Inne kody (rzadziej): znak-moduł, uzupełnień do jedności (mają dwa zera — wada).

> **Pułapka — przepełnienie (overflow):** dodanie dwóch dużych dodatnich może dać wynik ujemny, gdy przekroczy zakres.

### 2.5. Kodowanie stało- i zmiennopozycyjne

**Stałopozycyjne (fixed-point):** ustalona liczba bitów przed i po przecinku. Proste i szybkie, ale ograniczony zakres i precyzja.

**Zmiennopozycyjne (floating-point, IEEE 754):** liczba zapisana jako
$$(-1)^{S}\cdot M \cdot 2^{E},$$
gdzie $S$ — bit znaku, $M$ — mantysa, $E$ — wykładnik (z **przesunięciem/bias**). Standard **IEEE 754**:

| Typ | Bity razem | Znak | Wykładnik (bias) | Mantysa |
|---|---|---|---|---|
| pojedyncza precyzja (float) | 32 | 1 | 8 (bias 127) | 23 |
| podwójna precyzja (double) | 64 | 1 | 11 (bias 1023) | 52 |

Pozwala reprezentować bardzo duże i bardzo małe liczby kosztem **skończonej precyzji**.

> **Pułapka zmiennopozycyjna (ważne!):** wiele ułamków dziesiętnych (np. $0.1$) **nie** ma skończonej reprezentacji binarnej → błędy zaokrągleń. Dlatego nigdy nie porównuje się floatów przez `==`, tylko z tolerancją.

---

## 3. Algorytmy klasyczne

### 3.1. Największy wspólny dzielnik — algorytm Euklidesa (gcd)

**Idea:** $\gcd(a,b)=\gcd(b,\;a\bmod b)$, aż drugi argument stanie się $0$; wtedy $\gcd(a,0)=a$.

```
gcd(a, b):
    while b != 0:
        a, b = b, a mod b
    return a
```
> **Przykład.** $\gcd(48,18)$: $\gcd(18,12)\to\gcd(12,6)\to\gcd(6,0)=6$.

Złożoność $O(\log\min(a,b))$ — bardzo szybki. Wersja rekurencyjna: `gcd(a,b) = b==0 ? a : gcd(b, a mod b)`.

### 3.2. Minimum / maksimum

Przejdź raz przez tablicę, pamiętając dotychczasowe min/max:
```
min = A[0]
for i = 1 to n-1:
    if A[i] < min: min = A[i]
```
Złożoność $O(n)$, $n-1$ porównań. Jednoczesne min i max da się zrobić w $\approx \tfrac{3n}{2}$ porównań (parami).

### 3.3. Wyszukiwanie

**Liniowe (sekwencyjne):** sprawdzaj kolejno; działa na **nieposortowanych** danych. $O(n)$.

**Binarne (połówkowe):** **tylko na posortowanych** danych. Porównaj ze środkowym; jeśli za mały — szukaj w prawej połowie, jeśli za duży — w lewej. Co krok połowa danych odpada.
```
lo=0, hi=n-1
while lo <= hi:
    mid = (lo+hi)/2
    if A[mid]==x: return mid
    else if A[mid]<x: lo=mid+1
    else hi=mid-1
return NOT_FOUND
```
Złożoność $O(\log n)$.
> **Pułapka:** wyszukiwanie binarne na **nieposortowanej** tablicy daje błędne wyniki. Najpierw sortowanie!

### 3.4. Sortowanie — przegląd

| Algorytm | Średnio | Pesymistycznie | Pamięć | Stabilny? | Idea |
|---|---|---|---|---|---|
| bąbelkowe (bubble) | $O(n^2)$ | $O(n^2)$ | $O(1)$ | tak | zamiana sąsiednich, "bąbelki" wypływają |
| przez wstawianie (insertion) | $O(n^2)$ | $O(n^2)$ | $O(1)$ | tak | wstawiaj element w posortowaną część; najlepszy $O(n)$ dla prawie posortowanych |
| przez wybieranie (selection) | $O(n^2)$ | $O(n^2)$ | $O(1)$ | nie | znajdź minimum i wstaw na początek |
| przez scalanie (merge) | $O(n\log n)$ | $O(n\log n)$ | $O(n)$ | tak | dziel i scalaj posortowane połowy |
| szybkie (quicksort) | $O(n\log n)$ | $O(n^2)$ | $O(\log n)$ | nie | partycjonowanie wokół pivota |
| kopcowe (heapsort) | $O(n\log n)$ | $O(n\log n)$ | $O(1)$ | nie | kopiec binarny |

**Dolne ograniczenie** sortowania przez porównania: $\Omega(n\log n)$ — szybciej (np. $O(n)$) tylko algorytmy nieporównaniowe jak sortowanie kubełkowe/pozycyjne (przy założeniach o danych).

- **stabilność** = zachowanie kolejności elementów o równych kluczach.
- **quicksort** ma pesymistyczne $O(n^2)$ (np. już posortowane dane z pivotem skrajnym), ale w praktyce zwykle najszybszy; losowy wybór pivota redukuje ryzyko.

> **Typowe zadanie egzaminacyjne:** prześledź działanie algorytmu krok po kroku na małej tablicy, podaj liczbę porównań/zamian, podaj złożoność.

---

## 4. Języki formalne i automaty

### 4.1. Podstawowe pojęcia

- **Alfabet** $\Sigma$ — skończony zbiór symboli (np. $\{0,1\}$, $\{a,b\}$).
- **Słowo (łańcuch)** — skończony ciąg symboli alfabetu. **Słowo puste** $\varepsilon$ (długość 0).
- $\Sigma^*$ — zbiór **wszystkich** słów nad $\Sigma$ (w tym $\varepsilon$).
- **Język** $L$ — dowolny podzbiór $\Sigma^*$ (zbiór wybranych słów).
- Operacje na językach: suma, przekrój, **konkatenacja** $L_1L_2$, **domknięcie Kleene'a** $L^*$ (sklejanie dowolnej liczby słów z $L$, w tym zero → $\varepsilon$).

### 4.2. Gramatyki i hierarchia Chomsky'ego

**Gramatyka formalna** to czwórka $(N, \Sigma, P, S)$: symbole nieterminalne $N$, terminalne $\Sigma$, produkcje $P$ (reguły przepisywania), symbol startowy $S$. Język gramatyki = wszystkie słowa terminalne wyprowadzalne z $S$.

**Hierarchia Chomsky'ego** (od najogólniejszych do najprostszych):

| Typ | Nazwa | Akceptujący automat |
|---|---|---|
| Typ 0 | rekurencyjnie przeliczalne | maszyna Turinga |
| Typ 1 | kontekstowe | automat liniowo ograniczony (LBA) |
| Typ 2 | bezkontekstowe | automat ze stosem (PDA) |
| Typ 3 | **regularne** | automat skończony (DFA/NFA) |

Każda klasa zawiera następną: regularne ⊂ bezkontekstowe ⊂ kontekstowe ⊂ rekurencyjnie przeliczalne.

### 4.3. Automat skończony (DFA/NFA)

**Deterministyczny automat skończony (DFA)** to piątka $(Q,\Sigma,\delta,q_0,F)$:
- $Q$ — skończony zbiór **stanów**,
- $\Sigma$ — alfabet,
- $\delta: Q\times\Sigma\to Q$ — **funkcja przejścia** (z każdego stanu i symbolu dokładnie jeden następny stan),
- $q_0$ — stan początkowy,
- $F\subseteq Q$ — stany **akceptujące**.

Automat **akceptuje** słowo, gdy po przeczytaniu wszystkich symboli kończy w stanie z $F$. Język rozpoznawany przez automat skończony to dokładnie **język regularny**.

**NFA (niedeterministyczny):** z danego stanu może być wiele (lub zero) przejść dla symbolu; akceptuje, jeśli **istnieje** ścieżka prowadząca do stanu akceptującego. Twierdzenie: **NFA i DFA rozpoznają tę samą klasę języków** (regularne) — każdy NFA da się przekształcić w DFA (konstrukcja podzbiorów).

> **Lemat o pompowaniu** (pumping lemma): narzędzie do **dowodzenia, że język NIE jest regularny** (np. $\{a^n b^n : n\ge0\}$ nie jest regularny — automat skończony "nie umie liczyć").

### 4.4. Twierdzenie Kleene'a

**Język jest regularny wtedy i tylko wtedy, gdy opisuje go wyrażenie regularne** (i wtedy i tylko wtedy, gdy rozpoznaje go automat skończony). To spina regexy, automaty i gramatyki regularne w jedną całość.

---

## 5. Wyrażenia regularne

### 5.1. Składnia (teoria → praktyka)

Wyrażenie regularne (regex) opisuje wzorzec dopasowania tekstu.

| Konstrukcja | Znaczenie |
|---|---|
| `.` | dowolny pojedynczy znak |
| `*` | zero lub więcej powtórzeń poprzedniego |
| `+` | jedno lub więcej |
| `?` | zero lub jedno (opcjonalne) |
| `{n}`, `{n,m}` | dokładnie $n$ / od $n$ do $m$ powtórzeń |
| `[abc]` | jeden ze znaków a, b, c |
| `[a-z]` | zakres |
| `[^abc]` | dowolny **oprócz** a, b, c |
| `^` , `$` | początek / koniec wiersza |
| `\|` | alternatywa ("lub") |
| `( )` | grupowanie |
| `\d \w \s` | cyfra / znak słowny / biały znak (rozszerzenia) |

> **Przykłady.**
> - `^[0-9]+$` — wiersz złożony tylko z cyfr.
> - `[A-Za-z_][A-Za-z0-9_]*` — poprawny identyfikator (jak nazwa zmiennej w C).
> - `\b\w+@\w+\.\w+\b` — uproszczony adres e-mail.

### 5.2. Pułapki

- Klasyczne (POSIX, jak w `grep`) regexy bez `-E` wymagają **escapowania** `+`, `?`, `(`, `)`, `{` przez backslash. `grep -E` (lub `egrep`) używa rozszerzonej składni bez tych ukośników.
- `*` jest **zachłanny** (dopasowuje jak najwięcej) — w niektórych narzędziach dostępny wariant leniwy `*?`.
- Regex **nie** opisze języków niereguralnych (np. zrównoważonych nawiasów) — to ograniczenie wynikające z teorii (§4).

---

## 6. Systemy operacyjne

### 6.1. Czym jest system operacyjny

**System operacyjny (OS)** to oprogramowanie pośredniczące między sprzętem a aplikacjami; zarządza zasobami komputera. Główne **funkcje**:
- zarządzanie **procesami** (uruchamianie, planowanie, kończenie),
- zarządzanie **pamięcią** (przydział, pamięć wirtualna),
- zarządzanie **systemem plików** (organizacja danych na dysku),
- zarządzanie **urządzeniami** (sterowniki, wejście/wyjście),
- **interfejs** użytkownika (powłoka, GUI) i **bezpieczeństwo** (uprawnienia, użytkownicy).

**Krótka historia:** od przetwarzania wsadowego (batch), przez systemy z podziałem czasu (time-sharing), do współczesnych wielozadaniowych, wielordzeniowych. Rodziny: UNIX/Linux, Windows, macOS.

**Jądro (kernel)** — rdzeń OS działający w trybie uprzywilejowanym; aplikacje proszą o usługi przez **wywołania systemowe (system calls)**.

### 6.2. Procesy

**Proces** — wykonujący się program wraz z kontekstem (kod, dane, stos, licznik rozkazów, otwarte pliki, przydzielona pamięć). Każdy ma unikalny **PID**.

**Stany procesu** (uproszczony model):
- **nowy** → **gotowy** (ready) → **wykonywany** (running) → **zakończony**,
- dodatkowo **oczekujący/zablokowany** (waiting) — czeka na zdarzenie (np. wejście/wyjście).

Przejścia: planista (scheduler) wybiera proces gotowy → running; przy oczekiwaniu na I/O → waiting; po zdarzeniu → ready.

### 6.3. Wątki

**Wątek** — najmniejsza jednostka wykonania w obrębie procesu. Wiele wątków jednego procesu **dzieli** pamięć (kod, dane), ale ma własny stos i licznik rozkazów. Zalety: lekkie, szybka komunikacja; wada: konieczna **synchronizacja** dostępu do współdzielonych danych (sekcje krytyczne, mutexy, semafory; ryzyko **zakleszczenia / deadlock** i **wyścigu / race condition**).

### 6.4. Zarządzanie i planowanie (scheduling)

**Planista** decyduje, który gotowy proces dostanie procesor. Strategie:
- **FCFS** (first-come-first-served) — kolejność przybycia,
- **SJF** (shortest job first) — najkrótsze zadanie,
- **Round Robin** — każdy dostaje kwant czasu po kolei (wywłaszczanie),
- **priorytetowe** — wg priorytetu.

Wielozadaniowość: **z wywłaszczaniem (preemptive)** — OS odbiera procesor po kwancie czasu; bez wywłaszczania — proces sam oddaje sterowanie.

---

## 7. Linux

### 7.1. System plików i nawigacja

System plików to drzewo z korzeniem `/`. Ścieżki **bezwzględne** (od `/`) i **względne** (od bieżącego katalogu).

| Polecenie | Działanie |
|---|---|
| `pwd` | pokaż bieżący katalog |
| `ls -l` | lista plików (szczegółowo) |
| `cd /ścieżka` | zmień katalog (`cd ..` w górę, `cd ~` do domowego) |
| `mkdir`, `rmdir` | utwórz / usuń katalog |
| `cp`, `mv`, `rm` | kopiuj, przenieś/zmień nazwę, usuń |
| `cat`, `less`, `head`, `tail` | wyświetl zawartość pliku |
| `find /ścieżka -name "*.txt"` | szukaj plików |
| `man polecenie` | dokumentacja |

Skróty: `.` bieżący katalog, `..` nadrzędny, `~` katalog domowy, `*` dowolny ciąg (glob), `?` dowolny znak.

### 7.2. Uprawnienia (powiązane z systemem ósemkowym!)

Każdy plik ma uprawnienia dla trzech grup: **właściciel (u)**, **grupa (g)**, **inni (o)**, każde z prawami **r** (read=4), **w** (write=2), **x** (execute=1).

`chmod 755 plik` → właściciel rwx (7=4+2+1), grupa i inni r-x (5=4+1). To bezpośrednie zastosowanie systemu ósemkowego z wykładu.

| Polecenie | Działanie |
|---|---|
| `chmod 644 plik` | ustaw uprawnienia (ósemkowo) |
| `chown user:grupa plik` | zmień właściciela |
| `ls -l` | pokaż uprawnienia (np. `-rwxr-xr-x`) |

### 7.3. Strumienie i przekierowania

Każdy proces ma trzy standardowe strumienie:
- **stdin** (0) — wejście,
- **stdout** (1) — wyjście,
- **stderr** (2) — błędy.

| Operator | Działanie |
|---|---|
| `>` | przekieruj stdout do pliku (nadpisz) |
| `>>` | dopisz do pliku |
| `<` | wczytaj stdin z pliku |
| `2>` | przekieruj błędy |
| `\|` (potok) | wyjście jednego polecenia → wejście następnego |

> **Przykład potoku:** `cat plik.txt | grep "error" | sort | uniq -c` — wypisz, przefiltruj linie z "error", posortuj, policz unikalne.

### 7.4. Filtry (najważniejsze polecenia tekstowe)

**Filtr** czyta stdin, przetwarza, pisze na stdout. Klasyczne: `grep` (filtruje linie), `sort` (sortuje), `uniq` (usuwa/zlicza duplikaty), `wc` (liczy linie/słowa/znaki), `cut` (wycina kolumny), `tr` (zamienia znaki), `head`/`tail`. Łączenie filtrów potokami to filozofia Uniksa: małe narzędzia robiące jedną rzecz dobrze.

### 7.5. Procesy w Linuksie

| Polecenie | Działanie |
|---|---|
| `ps aux` | lista procesów |
| `top` / `htop` | monitor procesów na żywo |
| `kill PID`, `kill -9 PID` | wyślij sygnał / wymuś zakończenie |
| `polecenie &` | uruchom w tle |
| `jobs`, `fg`, `bg` | zarządzanie zadaniami w tle |
| `nohup`, `nice` | odporność na rozłączenie / priorytet |

---

## 8. Skrypty powłoki

### 8.1. Podstawy skryptu bash

Skrypt to plik tekstowy z poleceniami. Pierwsza linia (**shebang**) wskazuje interpreter:
```bash
#!/bin/bash
echo "Witaj, $1"     # $1 to pierwszy argument
```
Nadanie praw wykonania: `chmod +x skrypt.sh`, uruchomienie: `./skrypt.sh`.

### 8.2. Zmienne, argumenty, podstawienia

```bash
nazwa="Ala"           # bez spacji wokół =
echo "$nazwa"         # użycie: $nazwa lub ${nazwa}
liczba=$((3 + 4))     # arytmetyka
dzis=$(date)          # podstawienie wyniku polecenia
```
Zmienne specjalne: `$0` nazwa skryptu, `$1..$9` argumenty, `$#` liczba argumentów, `$@` wszystkie argumenty, `$?` kod wyjścia ostatniego polecenia, `$$` PID.

### 8.3. Instrukcje warunkowe i pętle

```bash
if [ "$x" -gt 10 ]; then
    echo "duże"
elif [ "$x" -eq 10 ]; then
    echo "równe"
else
    echo "małe"
fi

for i in 1 2 3; do echo $i; done
for f in *.txt; do echo "$f"; done

while [ "$n" -gt 0 ]; do
    n=$((n - 1))
done
```

**Operatory porównań liczbowych:** `-eq -ne -lt -le -gt -ge`. **Dla łańcuchów:** `=`, `!=`, `-z` (pusty), `-n` (niepusty). **Testy plików:** `-f` (plik), `-d` (katalog), `-e` (istnieje).

> **Pułapki bash:** zawsze cytuj zmienne w `"$zmienna"` (spacje!); spacje wewnątrz `[ ]` są **wymagane**; `=` przy przypisaniu **bez** spacji, a w teście **ze** spacjami.

---

## 9. Narzędzia

### 9.1. vi / vim — edytor

Działa w **trybach**, co jest największą pułapką dla początkujących:
- **tryb normalny** (po wejściu) — nawigacja i komendy,
- **tryb wstawiania** — wpisywanie tekstu (`i`, `a`, `o`),
- **tryb poleceń** (`:`) — zapis, wyjście, wyszukiwanie.

| Komenda | Działanie |
|---|---|
| `i` / `a` | wstawianie przed / po kursorze |
| `Esc` | powrót do trybu normalnego |
| `:w` / `:q` / `:wq` / `:q!` | zapisz / wyjdź / zapisz i wyjdź / wyjdź bez zapisu |
| `dd` / `yy` / `p` | usuń / skopiuj linię / wklej |
| `/wzorzec` | szukaj |
| `u` / `Ctrl+r` | cofnij / ponów |

> **Klasyczny problem egzaminacyjny/praktyczny:** "jak wyjść z vима" → `Esc` potem `:q!`.

### 9.2. grep — wyszukiwanie wzorców

`grep [opcje] wzorzec pliki` — wypisuje linie pasujące do wzorca (regex).

| Opcja | Działanie |
|---|---|
| `-i` | ignoruj wielkość liter |
| `-v` | linie **nie**pasujące |
| `-n` | numery linii |
| `-c` | policz pasujące linie |
| `-r` | rekurencyjnie po katalogach |
| `-E` | rozszerzone regexy (egrep) |

> `grep -rn "TODO" .` — znajdź wszystkie "TODO" w projekcie z numerami linii.

### 9.3. sed — strumieniowy edytor

Przetwarza tekst linia po linii. Najczęstsze — **zamiana**:
```bash
sed 's/stary/nowy/' plik      # zamień pierwsze wystąpienie w każdej linii
sed 's/stary/nowy/g' plik     # zamień wszystkie (global)
sed -n '5,10p' plik           # wypisz linie 5-10
sed '/wzorzec/d' plik         # usuń linie pasujące
```

### 9.4. awk — przetwarzanie kolumn/rekordów

Traktuje każdą linię jako rekord podzielony na pola `$1, $2, ...` (`$0` = cała linia, `NF` = liczba pól, `NR` = numer linii).
```bash
awk '{print $1, $3}' plik              # wypisz 1. i 3. kolumnę
awk -F: '{print $1}' /etc/passwd       # separator ":"
awk '$3 > 100 {print $1}' plik         # warunek
awk '{sum += $1} END {print sum}' plik # sumowanie kolumny
```

### 9.5. make — automatyzacja budowania

`make` czyta plik **Makefile** z **regułami** postaci:
```makefile
cel: zależności
	polecenie        # UWAGA: wcięcie MUSI być tabulatorem, nie spacjami!
```
Przykład:
```makefile
program: main.o utils.o
	gcc -o program main.o utils.o

main.o: main.c
	gcc -c main.c
```
`make` przebudowuje cel **tylko gdy** zależności są nowsze niż cel (oszczędza czas). To najczęstsza pułapka: **tabulator, nie spacje** przed poleceniem.

---

## 10. Git i praca zespołowa

### 10.1. Po co kontrola wersji

**System kontroli wersji (VCS)** śledzi zmiany w kodzie w czasie: pozwala cofać się, porównywać wersje, współpracować bez nadpisywania zmian innych, prowadzić równoległe gałęzie. **Git** jest **rozproszony** — każdy ma pełną kopię historii (repozytorium).

### 10.2. Podstawowy obieg pracy

Trzy "obszary": katalog roboczy → poczekalnia (staging/index) → repozytorium (commity).

| Polecenie | Działanie |
|---|---|
| `git init` / `git clone URL` | nowe repo / sklonuj istniejące |
| `git status` | stan plików |
| `git add plik` / `git add .` | dodaj do poczekalni |
| `git commit -m "opis"` | zatwierdź zmiany |
| `git log` | historia commitów |
| `git diff` | różnice |
| `git push` / `git pull` | wyślij / pobierz zmiany ze zdalnego repo |

### 10.3. Gałęzie i scalanie

| Polecenie | Działanie |
|---|---|
| `git branch nazwa` | utwórz gałąź |
| `git checkout nazwa` / `git switch` | przełącz gałąź |
| `git merge nazwa` | scal gałąź do bieżącej |

**Konflikt scalania** powstaje, gdy dwie gałęzie zmieniły to samo miejsce — git oznacza konflikt znacznikami `<<<<<<<`, `=======`, `>>>>>>>`, które trzeba ręcznie rozwiązać.

**Platformy:** GitHub, GitLab, Bitbucket — hosting repozytoriów + **pull/merge requesty** (przegląd kodu), **issues** (śledzenie zadań/błędów), CI/CD.

### 10.4. Etyka i praca zespołowa

Wymagana przez kartę przedmiotu (K1, K2, efekty MKO_K1_K02..06):
- **uczciwość intelektualna** — nie podszywaj się pod cudzą pracę, podawaj źródła, respektuj licencje (open source, prawa autorskie),
- **odpowiedzialność** za wspólny kod, czytelne commity i dokumentacja,
- **współpraca** — przeglądy kodu (code review), jasna komunikacja, podział ról,
- świadomość **społecznych i prawnych** aspektów (ochrona danych, plagiat, prawo autorskie).

### 10.5. Dokumentacja projektu

Dobra dokumentacja: plik **README** (opis, instalacja, użycie), komentarze w kodzie, opis API, licencja. Ułatwia współpracę i utrzymanie projektu.

---

## 11. Kompilacja: gcc

### 11.1. Etapy kompilacji programu w C

Od kodu źródłowego do programu wykonywalnego przechodzimy przez etapy:
1. **Preprocesor** — rozwija dyrektywy `#include`, `#define`.
2. **Kompilacja** — kod C → kod asemblera.
3. **Asemblacja** — asembler → kod maszynowy (plik obiektowy `.o`).
4. **Linkowanie (konsolidacja)** — łączy pliki obiektowe i biblioteki → plik wykonywalny.

### 11.2. gcc w praktyce

| Polecenie | Działanie |
|---|---|
| `gcc program.c -o program` | skompiluj do pliku `program` |
| `gcc -c plik.c` | tylko do pliku obiektowego `.o` |
| `gcc -Wall ...` | włącz ostrzeżenia (zalecane!) |
| `gcc -g ...` | informacje dla debuggera (gdb) |
| `gcc -O2 ...` | optymalizacja |
| `./program` | uruchomienie |

> **Pułapka:** błędy **kompilacji** (składnia) vs błędy **linkowania** (np. niezdefiniowana funkcja, `undefined reference`) to różne etapy — komunikaty wyglądają inaczej.

---

## 12. LaTeX

### 12.1. Czym jest

**LaTeX** to system **składu tekstu** (nie WYSIWYG) — piszesz źródło z poleceniami, kompilujesz do PDF. Standard w matematyce dzięki doskonałemu składowi wzorów.

### 12.2. Szkielet dokumentu

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage{amsmath}          % pakiety
\title{Tytuł}
\author{Autor}
\begin{document}
\maketitle
\section{Wstęp}
Tekst akapitu. Wzór w linii: $a^2+b^2=c^2$.
Wzór wyróżniony:
\[ \int_0^1 x^2\,dx = \frac{1}{3} \]
\end{document}
```

### 12.3. Kluczowe elementy

- **Środowiska:** `\begin{...}...\end{...}` (np. `itemize`, `enumerate`, `equation`, `table`, `figure`).
- **Tryb matematyczny:** `$...$` (w linii), `\[...\]` lub `equation` (wyróżniony).
- Struktura: `\section`, `\subsection`; listy `\item`; `\frac`, `\sqrt`, `\sum`, `\int`, indeksy `_` i potęgi `^`.
- Kompilacja: `pdflatex plik.tex` (czasem dwukrotnie — dla spisu treści i odnośników).

---

## 13. Teoria informacji

### 13.1. Ilość informacji i entropia

Teoria informacji (Claude Shannon) mierzy ilość informacji w **bitach**. Im mniej prawdopodobne zdarzenie, tym więcej niesie informacji.

**Ilość informacji** zdarzenia o prawdopodobieństwie $p$:
$$I = -\log_2 p \quad[\text{bity}].$$

**Entropia** źródła o symbolach z prawdopodobieństwami $p_1,\dots,p_n$ — średnia ilość informacji na symbol:
$$H = -\sum_{i=1}^{n} p_i \log_2 p_i \quad[\text{bity/symbol}].$$

Własności:
- $H$ jest **maksymalna** ($=\log_2 n$), gdy wszystkie symbole **jednakowo prawdopodobne** (największa niepewność),
- $H=0$, gdy jeden symbol ma prawdopodobieństwo 1 (brak niepewności),
- entropia wyznacza **dolną granicę** średniej długości kodu (twierdzenie Shannona o kodowaniu bezstratnym).

> **Przykład.** Rzut uczciwą monetą: $p=\tfrac12$ na każdą stronę, $H=-\tfrac12\log_2\tfrac12-\tfrac12\log_2\tfrac12 = 1$ bit. Moneta zawsze orzeł: $H=0$.

### 13.2. Kodowanie

**Kod** przypisuje symbolom ciągi bitów. **Kod przedrostkowy (prefiksowy)** — żaden kod nie jest początkiem innego → da się jednoznacznie zdekodować bez separatorów.

**Kodowanie Huffmana** (kompresja bezstratna, optymalny kod prefiksowy):
1. Wypisz symbole z częstościami.
2. Połącz **dwa najrzadsze** w węzeł o sumie częstości.
3. Powtarzaj, aż zostanie jedno drzewo.
4. Krawędzie: 0 w lewo, 1 w prawo; kod symbolu = ścieżka od korzenia.

Efekt: częste symbole dostają **krótsze** kody → krótszy średni zapis. Średnia długość zbliża się do entropii.

> **Typowe zadanie:** zbuduj drzewo Huffmana dla danych częstości, podaj kody i średnią długość kodu, porównaj z entropią.

### 13.3. Kompresja

- **Bezstratna** — odtwarza oryginał dokładnie (Huffman, LZ77/LZW, DEFLATE → ZIP, gzip, PNG). Stosowana, gdy każdy bit się liczy (tekst, kod, archiwa).
- **Stratna** — pomija dane mniej istotne percepcyjnie, mniejszy rozmiar (JPEG, MP3, MP4). Dla obrazu/dźwięku/wideo.

Granica kompresji bezstratnej wynika z entropii — nie da się skompresować poniżej zawartości informacyjnej.

### 13.4. Szyfrowanie (podstawy)

**Szyfrowanie** chroni poufność: tekst jawny → (klucz) → szyfrogram.
- **Symetryczne** — ten sam klucz do szyfrowania i deszyfrowania (AES, DES). Szybkie; problem: bezpieczna wymiana klucza.
- **Asymetryczne (klucz publiczny)** — para kluczy: publiczny (szyfruje) i prywatny (deszyfruje), np. **RSA**. Rozwiązuje wymianę klucza; wolniejsze.
- **Funkcje skrótu (hash)** — jednokierunkowe (SHA-256); do podpisów, weryfikacji integralności, haseł. **Nieodwracalne** — to nie szyfrowanie.

Proste szyfry historyczne (na rozgrzewkę): **Cezara** (przesunięcie alfabetu o stałą), podstawieniowe, Vigenère'a. Łatwe do złamania analizą częstości — pokazują, czym dobre szyfrowanie **nie** jest.

> **Pojęcia obok siebie:** kodowanie ≠ szyfrowanie ≠ kompresja ≠ hashowanie. Kodowanie = reprezentacja; szyfrowanie = poufność (z kluczem); kompresja = zmniejszenie rozmiaru; hash = jednokierunkowy skrót.

---

## 14. Ściąga

### Systemy pozycyjne
- Na dziesiętny: wzór pozycyjny ($\sum d_i b^i$). Z dziesiętnego: dziel przez $b$, reszty od dołu.
- Bin↔hex: grupy po 4 bity; bin↔oct: po 3 bity.
- U2: negacja = zaneguj bity + 1; zakres $[-2^{n-1}, 2^{n-1}-1]$.
- IEEE 754 float: 1+8+23 bity (bias 127); double: 1+11+52 (bias 1023).

### Złożoności
- Wyszukiwanie: liniowe $O(n)$, binarne $O(\log n)$ (posortowane!).
- Sortowania $O(n^2)$: bąbelkowe, wstawianie, wybieranie. $O(n\log n)$: scalanie, kopcowe, quicksort (śr.). Quicksort pesymistycznie $O(n^2)$.
- Dolna granica sortowania przez porównania: $\Omega(n\log n)$.
- Euklides $\gcd$: $O(\log\min(a,b))$.

### Automaty (hierarchia Chomsky'ego)
- Typ 3 regularne ↔ automat skończony ↔ wyrażenia regularne (tw. Kleene'a).
- Typ 2 bezkontekstowe ↔ automat ze stosem; Typ 1 kontekstowe ↔ LBA; Typ 0 ↔ maszyna Turinga.
- Lemat o pompowaniu → dowód, że język NIE jest regularny.

### Linux / strumienie
- `>` nadpisz, `>>` dopisz, `<` wejście, `|` potok, `2>` błędy.
- Uprawnienia ósemkowo: r=4, w=2, x=1 → `chmod 755`.
- Filtry: `grep sort uniq wc cut tr head tail`.

### Narzędzia
- `sed 's/a/b/g'` zamiana; `awk '{print $1}'` kolumny; `grep -rn` szukanie; `make` (TAB!).
- git: `add → commit → push`; gałęzie `branch/checkout/merge`.

### gcc
- `gcc -Wall prog.c -o prog`; etapy: preprocesor → kompilacja → asemblacja → linkowanie.

### Teoria informacji
- Entropia $H=-\sum p_i\log_2 p_i$; maksymalna przy równych prawdopodobieństwach ($\log_2 n$).
- Huffman: łącz dwa najrzadsze symbole → optymalny kod prefiksowy.
- Kompresja bezstratna (ZIP, Huffman) vs stratna (JPEG, MP3).
- Szyfrowanie symetryczne (AES) vs asymetryczne (RSA); hash (SHA) jednokierunkowy.

### Strategia na egzamin
1. **Konwersje systemów** ćwicz na czas — to pewne punkty.
2. **U2 i IEEE 754** — znaj algorytm negacji i układ bitów.
3. **Algorytmy** — umiej prześledzić krok po kroku i podać złożoność.
4. **Automaty/regex** — narysuj automat, napisz regex, rozpoznaj typ języka.
5. **Polecenia Linuksa/narzędzi** — znaj na pamięć podstawowy zestaw i potoki.
6. **Entropia i Huffman** — przećwicz pełne zadanie obliczeniowe.
7. **Rozróżniaj pojęcia:** kodowanie / kompresja / szyfrowanie / hash; proces / wątek; kompilacja / linkowanie.
# Logika i teoria mnogości — kompletne notatki na zaliczenie

## Spis treści

1. [Rachunek zdań (logika zdań)](#1-rachunek-zdan)
2. [Kwantyfikatory (rachunek predykatów)](#2-kwantyfikatory)
3. [Zbiory i działania na nich](#3-zbiory-i-dzialania-na-nich)
4. [Relacje (ogólnie)](#4-relacje)
5. [Relacje równoważności](#5-relacje-rownowaznosci)
6. [Funkcje](#6-funkcje)
7. [Własności funkcji: injekcja, surjekcja, bijekcja](#7-wlasnosci-funkcji)
8. [Zbiory równoliczne — moce zbiorów](#8-zbiory-rownoliczne)
9. [Zbiory przeliczalne i mocy continuum](#9-zbiory-przeliczalne-i-continuum)
10. [Relacje porządku](#10-relacje-porzadku)
11. [Lemat Kuratowskiego-Zorna](#11-lemat-kuratowskiego-zorna)
12. [Ściąga — symbole i prawa zbiorczo](#12-sciaga)

---

## 1. Rachunek zdań

### 1.1. Zdanie logiczne

**Zdanie (w sensie logiki)** to wyrażenie, któremu można jednoznacznie przypisać wartość logiczną: **prawda** (1, P) albo **fałsz** (0, F) — i nigdy obie naraz. "Pada deszcz" jest zdaniem; "Która godzina?" nie jest; "$x>3$" samo w sobie też nie (to forma zdaniowa — zależy od $x$).

### 1.2. Spójniki logiczne i tabele prawdy

Oznaczenia zdań: $p, q, r,\dots$ Podstawowe spójniki:

| $p$ | $q$ | $\lnot p$ | $p\land q$ | $p\lor q$ | $p\Rightarrow q$ | $p\Leftrightarrow q$ |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 1 | 1 | 0 | 1 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 | 1 | 1 | 0 |
| 0 | 0 | 1 | 0 | 0 | 1 | 1 |

- $\lnot p$ — **negacja** ("nie $p$").
- $p\land q$ — **koniunkcja** ("$p$ i $q$"); prawdziwa, gdy oba prawdziwe.
- $p\lor q$ — **alternatywa** ("$p$ lub $q$"); fałszywa tylko gdy oba fałszywe (to "lub" **nierozłączne**).
- $p\Rightarrow q$ — **implikacja** ("jeśli $p$, to $q$"); **fałszywa tylko w jednym przypadku: $p$ prawda, $q$ fałsz**. To najczęstsze źródło błędów.
- $p\Leftrightarrow q$ — **równoważność** ("$p$ wtedy i tylko wtedy, gdy $q$"); prawdziwa, gdy obie strony mają tę samą wartość.

> **Pułapka implikacji:** z fałszu wynika cokolwiek — "Jeśli $2+2=5$, to jestem papieżem" jest **prawdziwe** logicznie (poprzednik fałszywy → cała implikacja prawdziwa). Implikacja **nie** twierdzi, że istnieje związek przyczynowy.

### 1.3. Tautologie i prawa rachunku zdań

**Tautologia** — formuła prawdziwa przy **każdym** wartościowaniu zmiennych (sprawdzasz tabelą prawdy: same jedynki w ostatniej kolumnie). **Kontrtautologia** — zawsze fałszywa. Formuła **spełnialna** — prawdziwa przy przynajmniej jednym wartościowaniu.

Najważniejsze prawa (wszystkie są tautologiami):

| Nazwa | Prawo |
|---|---|
| Prawo wyłączonego środka | $p\lor\lnot p$ |
| Prawo sprzeczności | $\lnot(p\land\lnot p)$ |
| Podwójna negacja | $\lnot\lnot p\Leftrightarrow p$ |
| Prawa de Morgana | $\lnot(p\land q)\Leftrightarrow \lnot p\lor\lnot q$ |
| | $\lnot(p\lor q)\Leftrightarrow \lnot p\land\lnot q$ |
| Implikacja przez alternatywę | $(p\Rightarrow q)\Leftrightarrow(\lnot p\lor q)$ |
| Negacja implikacji | $\lnot(p\Rightarrow q)\Leftrightarrow(p\land\lnot q)$ |
| Kontrapozycja (transpozycja) | $(p\Rightarrow q)\Leftrightarrow(\lnot q\Rightarrow\lnot p)$ |
| Przemienność | $p\land q\Leftrightarrow q\land p$; $p\lor q\Leftrightarrow q\lor p$ |
| Łączność | $(p\land q)\land r\Leftrightarrow p\land(q\land r)$ |
| Rozdzielność | $p\land(q\lor r)\Leftrightarrow(p\land q)\lor(p\land r)$ |
| | $p\lor(q\land r)\Leftrightarrow(p\lor q)\land(p\lor r)$ |
| Sylogizm (przechodniość) | $\big((p\Rightarrow q)\land(q\Rightarrow r)\big)\Rightarrow(p\Rightarrow r)$ |
| Modus ponens | $\big(p\land(p\Rightarrow q)\big)\Rightarrow q$ |
| Modus tollens | $\big(\lnot q\land(p\Rightarrow q)\big)\Rightarrow\lnot p$ |

> **Negacja implikacji — zapamiętaj!** Zaprzeczeniem "jeśli $p$ to $q$" jest "$p$ i nie $q$" (a **nie** "jeśli $p$ to nie $q$").

### 1.4. Jak rozwiązywać zadania z rachunku zdań

- **Sprawdzić, czy formuła jest tautologią:** zbuduj pełną tabelę prawdy ($2^n$ wierszy dla $n$ zmiennych) albo metodą "nie wprost" — załóż, że formuła jest fałszywa, i szukaj sprzeczności. Jeśli sprzeczność wymuszona zawsze → tautologia.
- **Upraszczanie formuł:** stosuj prawa z tabeli powyżej, jak przy przekształceniach algebraicznych.
- **Implikacja → szukaj kontrprzykładu:** żeby obalić $p\Rightarrow q$ wystarczy jeden przypadek $p=1, q=0$.

---

## 2. Kwantyfikatory

### 2.1. Forma zdaniowa (predykat)

**Forma zdaniowa** $\varphi(x)$ to wyrażenie z wolną zmienną, które staje się zdaniem po podstawieniu konkretu (np. $x>3$). Kwantyfikatory "wiążą" zmienną, robiąc z formy zdanie.

- **Kwantyfikator ogólny** $\forall x\,\varphi(x)$ — "dla każdego $x$ zachodzi $\varphi(x)$".
- **Kwantyfikator szczegółowy (egzystencjalny)** $\exists x\,\varphi(x)$ — "istnieje $x$ takie, że $\varphi(x)$".

(Spotykane zapisy: $\bigwedge_x$ zamiast $\forall x$ oraz $\bigvee_x$ zamiast $\exists x$ — to konwencja polskich podręczników, np. Rasiowej.)

### 2.2. Negacja kwantyfikatorów (KLUCZOWE)

$$\lnot\,\forall x\,\varphi(x) \;\Leftrightarrow\; \exists x\,\lnot\varphi(x),$$
$$\lnot\,\exists x\,\varphi(x) \;\Leftrightarrow\; \forall x\,\lnot\varphi(x).$$

**Reguła praktyczna:** negując zdanie z kwantyfikatorami, "przesuwasz" negację w prawo, **zamieniając $\forall$ na $\exists$ i odwrotnie**, aż dojdzie do predykatu, który negujesz.

> **Przykład.** $\lnot\big(\forall x\,\exists y\;(x<y)\big)\Leftrightarrow \exists x\,\forall y\;\lnot(x<y)\Leftrightarrow \exists x\,\forall y\;(x\ge y).$

### 2.3. Kolejność kwantyfikatorów ma znaczenie!

$\forall x\,\exists y\,\varphi(x,y)$ to **nie** to samo co $\exists y\,\forall x\,\varphi(x,y)$.

> **Przykład (liczby rzeczywiste).**
> - $\forall x\,\exists y\;(y>x)$ — "dla każdej liczby istnieje większa" → **prawda**.
> - $\exists y\,\forall x\;(y>x)$ — "istnieje liczba większa od wszystkich" → **fałsz**.
> Zmiana kolejności tych samych kwantyfikatorów zmieniła wartość logiczną!

Kwantyfikatory **tego samego rodzaju** można przestawiać: $\forall x\forall y \equiv \forall y\forall x$.

---

## 3. Zbiory i działania na nich

### 3.1. Podstawowe pojęcia

**Zbiór** to pojęcie pierwotne (nie definiujemy go) — kolekcja rozróżnialnych obiektów (elementów). Zapis $a\in A$ ("$a$ należy do $A$"), $a\notin A$ ("nie należy").

**Sposoby określania zbioru:**
- wyliczenie: $A=\{1,2,3\}$,
- przez własność: $A=\{x : \varphi(x)\}$ ("zbiór tych $x$, dla których zachodzi $\varphi$"), np. $\{x\in\mathbb{R}: x^2<4\}=(-2,2)$.

**Zbiór pusty** $\varnothing$ — nie ma żadnego elementu. Jest **podzbiorem każdego zbioru**.

**Zawieranie:** $A\subseteq B \iff \forall x\,(x\in A\Rightarrow x\in B)$ ("$A$ jest podzbiorem $B$").
**Równość zbiorów:** $A=B \iff (A\subseteq B \land B\subseteq A)$. To podstawowa metoda dowodzenia równości zbiorów — pokazujesz **dwa zawierania**.

> **Uwaga na różnicę:** $\in$ (należenie elementu) to coś innego niż $\subseteq$ (zawieranie zbiorów). Np. $1\in\{1,2\}$, ale $\{1\}\subseteq\{1,2\}$. Zapis $1\subseteq\{1,2\}$ jest błędny.

### 3.2. Działania na zbiorach

| Działanie | Definicja | Opis |
|---|---|---|
| Suma | $A\cup B=\{x: x\in A \lor x\in B\}$ | elementy w $A$ **lub** $B$ |
| Przekrój (iloczyn) | $A\cap B=\{x: x\in A \land x\in B\}$ | elementy w **obu** |
| Różnica | $A\setminus B=\{x: x\in A \land x\notin B\}$ | w $A$, ale nie w $B$ |
| Dopełnienie | $A'=A^c=U\setminus A$ | poza $A$ (względem uniwersum $U$) |
| Różnica symetryczna | $A\triangle B=(A\setminus B)\cup(B\setminus A)$ | w dokładnie jednym |

**Zbiory rozłączne:** $A\cap B=\varnothing$.

### 3.3. Prawa działań na zbiorach (analogiczne do rachunku zdań!)

| Nazwa | Prawo |
|---|---|
| Przemienność | $A\cup B=B\cup A$, $A\cap B=B\cap A$ |
| Łączność | $(A\cup B)\cup C=A\cup(B\cup C)$ |
| Rozdzielność | $A\cap(B\cup C)=(A\cap B)\cup(A\cap C)$ |
| | $A\cup(B\cap C)=(A\cup B)\cap(A\cup C)$ |
| **Prawa de Morgana** | $(A\cup B)'=A'\cap B'$ |
| | $(A\cap B)'=A'\cup B'$ |
| Idempotentność | $A\cup A=A$, $A\cap A=A$ |
| Pochłanianie | $A\cup(A\cap B)=A$ |

> **Wskazówka:** dowody tych praw robi się przez logikę — przepisujesz $x\in(\dots)$ na warunek logiczny i stosujesz odpowiednie prawo rachunku zdań. De Morgan dla zbiorów = de Morgan dla logiki.

### 3.4. Iloczyn kartezjański

$$A\times B=\{(a,b): a\in A \land b\in B\}$$
— zbiór **par uporządkowanych**. Para uporządkowana to $(a,b)$, gdzie kolejność ma znaczenie: $(a,b)=(c,d)\iff a=c\land b=d$. (Formalnie, def. Kuratowskiego: $(a,b)=\{\{a\},\{a,b\}\}$.)

Jeśli $|A|=m$, $|B|=n$ (skończone), to $|A\times B|=mn$. Uogólnienie: $A_1\times\dots\times A_n$ — $n$-ki uporządkowane. Np. $\mathbb{R}^2=\mathbb{R}\times\mathbb{R}$ to płaszczyzna.

### 3.5. Zbiór potęgowy

$$\mathcal{P}(A)=2^A=\{X: X\subseteq A\}$$
— zbiór **wszystkich podzbiorów** $A$. Jeśli $|A|=n$, to $|\mathcal{P}(A)|=2^n$ (stąd zapis $2^A$).

> **Przykład.** $A=\{1,2\}$: $\mathcal{P}(A)=\{\varnothing,\{1\},\{2\},\{1,2\}\}$ — 4 elementy. Pamiętaj o $\varnothing$ i o całym $A$!

### 3.6. Suma i przekrój rodziny zbiorów

Dla rodziny $\{A_t\}_{t\in T}$:
$$\bigcup_{t\in T}A_t=\{x:\exists t\in T\; x\in A_t\},\qquad \bigcap_{t\in T}A_t=\{x:\forall t\in T\; x\in A_t\}.$$
Zauważ związek z kwantyfikatorami: suma ↔ $\exists$, przekrój ↔ $\forall$.

---

## 4. Relacje

### 4.1. Definicja

**Relacja (dwuargumentowa)** między zbiorami $A$ i $B$ to dowolny podzbiór $R\subseteq A\times B$. Zapisujemy $aRb$ albo $(a,b)\in R$ ("$a$ jest w relacji $R$ z $b$").

Gdy $A=B$, mówimy o relacji **w zbiorze $A$** ($R\subseteq A\times A$).

### 4.2. Własności relacji w zbiorze $A$

Niech $R\subseteq A\times A$. Relacja jest:

| Własność | Warunek |
|---|---|
| **zwrotna** | $\forall a\in A:\; aRa$ |
| **przeciwzwrotna** | $\forall a\in A:\; \lnot(aRa)$ |
| **symetryczna** | $\forall a,b:\; aRb\Rightarrow bRa$ |
| **antysymetryczna** | $\forall a,b:\; (aRb\land bRa)\Rightarrow a=b$ |
| **przechodnia** | $\forall a,b,c:\; (aRb\land bRc)\Rightarrow aRc$ |
| **spójna (liniowa)** | $\forall a,b:\; aRb\lor bRa$ |

Te własności są "cegiełkami" — z nich budujemy relacje równoważności (§5) i relacje porządku (§10).

> **Pułapka:** "antysymetryczna" to **nie** to samo co "niesymetryczna". Relacja może być jednocześnie symetryczna i antysymetryczna (np. relacja równości $=$).

---

## 5. Relacje równoważności

### 5.1. Definicja

**Relacja równoważności** to relacja $\sim$ w zbiorze $A$, która jest jednocześnie:
1. **zwrotna**: $a\sim a$,
2. **symetryczna**: $a\sim b\Rightarrow b\sim a$,
3. **przechodnia**: $a\sim b\land b\sim c\Rightarrow a\sim c$.

Intuicja: $\sim$ "skleja" elementy podobne w jednym sensie (np. "ma ten sam kolor", "daje tę samą resztę z dzielenia").

### 5.2. Klasy abstrakcji (klasy równoważności)

**Klasa abstrakcji** elementu $a$:
$$[a]=\{x\in A: x\sim a\}$$
— zbiór wszystkich elementów równoważnych $a$.

**Najważniejsze twierdzenie:** klasy abstrakcji relacji równoważności tworzą **podział** zbioru $A$, tzn.:
- każda klasa jest niepusta ($a\in[a]$),
- dwie klasy są albo **identyczne**, albo **rozłączne** ($[a]=[b]$ lub $[a]\cap[b]=\varnothing$),
- suma wszystkich klas = całe $A$.

Zachodzi też w drugą stronę: **każdy podział zbioru wyznacza relację równoważności** (dwa elementy są w relacji ⟺ leżą w tym samym kawałku podziału). To **wzajemnie jednoznaczna odpowiedniość** między relacjami równoważności a podziałami.

### 5.3. Zbiór ilorazowy

$$A/{\sim}=\{[a]: a\in A\}$$
— zbiór wszystkich klas abstrakcji ("zbiór ilorazowy"). Każda klasa to jeden "punkt" tego nowego zbioru.

> **Sztandarowy przykład (kongruencja mod $n$).** W $\mathbb{Z}$: $a\sim b \iff n\mid(a-b)$ (ta sama reszta z dzielenia przez $n$). To relacja równoważności. Klasy: $[0],[1],\dots,[n-1]$ — reszty. Zbiór ilorazowy $\mathbb{Z}/{\sim}=\mathbb{Z}_n$ (liczby modulo $n$).

### 5.4. Jak rozwiązywać zadania

- **Sprawdzić, czy relacja jest równoważnością:** zweryfikuj kolejno zwrotność, symetrię, przechodniość. Jeśli któraś nie zachodzi — podaj **kontrprzykład**.
- **Wyznaczyć klasy abstrakcji:** dla wzorcowego elementu wypisz wszystkie z nim równoważne; policz, ile jest różnych klas.

---

## 6. Funkcje

### 6.1. Definicja

**Funkcja** $f:A\to B$ to relacja $f\subseteq A\times B$, która **każdemu** $a\in A$ przypisuje **dokładnie jeden** $b\in B$. Piszemy $b=f(a)$.

Formalnie dwa warunki:
1. **Określoność:** $\forall a\in A\;\exists b\in B\; (a,b)\in f$ (każdy argument ma wartość),
2. **Jednoznaczność:** $\big((a,b)\in f \land (a,c)\in f\big)\Rightarrow b=c$ (tylko jedna wartość).

- $A$ — **dziedzina** ($\operatorname{dom} f$),
- $B$ — **przeciwdziedzina** (kodziedzina),
- $f(A)=\{f(a):a\in A\}$ — **obraz** (zbiór wartości), zawsze $f(A)\subseteq B$.

### 6.2. Obraz i przeciwobraz zbioru

Dla $X\subseteq A$ i $Y\subseteq B$:
$$f(X)=\{f(x):x\in X\}\quad(\text{obraz zbioru }X),$$
$$f^{-1}(Y)=\{a\in A: f(a)\in Y\}\quad(\text{przeciwobraz zbioru }Y).$$

> **Uwaga:** zapis $f^{-1}(Y)$ (przeciwobraz) ma sens dla **każdej** funkcji, nawet nieodwracalnej — to **nie** to samo co funkcja odwrotna $f^{-1}$ (która wymaga bijekcji, §7).

Własności (warto znać, bywają na zaliczeniu):
$$f(X_1\cup X_2)=f(X_1)\cup f(X_2),\qquad f(X_1\cap X_2)\subseteq f(X_1)\cap f(X_2).$$
> **Wyjątek/pułapka:** dla przekroju jest tylko **zawieranie $\subseteq$**, równość zachodzi nie zawsze (a zawsze, gdy $f$ injektywna). Dla przeciwobrazu jest lepiej — przeciwobraz zachowuje sumę **i** przekrój z równością.

### 6.3. Złożenie funkcji

Dla $f:A\to B$, $g:B\to C$:
$$(g\circ f)(a)=g(f(a)),\qquad g\circ f: A\to C.$$
Czytaj "od prawej": najpierw $f$, potem $g$. **Składanie jest łączne** ($h\circ(g\circ f)=(h\circ g)\circ f$), ale **nieprzemienne** (na ogół $g\circ f\ne f\circ g$).

---

## 7. Własności funkcji

### 7.1. Trzy kluczowe typy

| Typ | Definicja | Intuicja |
|---|---|---|
| **Injekcja** (różnowartościowa, "1-1") | $f(a_1)=f(a_2)\Rightarrow a_1=a_2$ | różne argumenty → różne wartości |
| **Surjekcja** ("na") | $\forall b\in B\;\exists a\in A:\; f(a)=b$ | obraz wypełnia całe $B$: $f(A)=B$ |
| **Bijekcja** (wzajemnie jednoznaczna) | injekcja **i** surjekcja | idealne sparowanie $A\leftrightarrow B$ |

**Równoważne sformułowanie injekcji** (wygodne w dowodach): $a_1\ne a_2 \Rightarrow f(a_1)\ne f(a_2)$.

### 7.2. Funkcja odwrotna

$f:A\to B$ ma funkcję odwrotną $f^{-1}:B\to A$ **wtedy i tylko wtedy, gdy $f$ jest bijekcją**. Wtedy:
$$f^{-1}(f(a))=a \quad\text{oraz}\quad f(f^{-1}(b))=b,$$
czyli $f^{-1}\circ f=\mathrm{id}_A$ i $f\circ f^{-1}=\mathrm{id}_B$.

### 7.3. Jak rozwiązywać zadania o własnościach funkcji

**Dowód injekcji:** załóż $f(a_1)=f(a_2)$ i doprowadź do $a_1=a_2$.
**Dowód surjekcji:** weź dowolne $b\in B$ i **wskaż/skonstruuj** $a$ takie, że $f(a)=b$ (zwykle rozwiązując równanie $f(a)=b$ względem $a$ i sprawdzając, że $a\in A$).
**Obalenie:** jeden kontrprzykład wystarczy (dla injekcji — dwa różne argumenty o tej samej wartości; dla surjekcji — element $B$ nieosiągany).

> **Przykład.** $f:\mathbb{R}\to\mathbb{R}$, $f(x)=x^2$: **nie** injekcja ($f(-1)=f(1)$) i **nie** surjekcja (nie ma wartości ujemnych). Ale $f:[0,\infty)\to[0,\infty)$, $f(x)=x^2$ **jest** bijekcją. Widać, że własności zależą od dziedziny i przeciwdziedziny, a nie tylko od wzoru!

### 7.4. Złożenie a własności

- Złożenie dwóch injekcji jest injekcją; dwóch surjekcji — surjekcją; dwóch bijekcji — bijekcją.
- Jeśli $g\circ f$ injektywna → $f$ injektywna. Jeśli $g\circ f$ surjektywna → $g$ surjektywna.

---

## 8. Zbiory równoliczne

### 8.1. Równoliczność

**Definicja.** Zbiory $A$ i $B$ są **równoliczne** (mają tę samą moc), $A\sim B$ lub $|A|=|B|$, gdy istnieje **bijekcja** $f:A\to B$.

Równoliczność jest "relacją równoważności" na klasach zbiorów (zwrotna, symetryczna, przechodnia). Klasę abstrakcji nazywamy **mocą** (liczbą kardynalną) zbioru, $|A|$.

> **Zaskakujący fakt o zbiorach nieskończonych:** zbiór może być równoliczny ze swoją **właściwą** częścią! Np. $\mathbb{N}\sim\{\text{liczby parzyste}\}$ przez $n\mapsto 2n$. To jest wręcz **definicja** zbioru nieskończonego (Dedekind): zbiór jest nieskończony, gdy jest równoliczny z pewnym swoim właściwym podzbiorem.

### 8.2. Twierdzenie Cantora-Bernsteina(-Schrödera)

**Twierdzenie.** Jeśli istnieje injekcja $A\to B$ **oraz** injekcja $B\to A$, to istnieje bijekcja $A\to B$, czyli $|A|=|B|$.

To kluczowe narzędzie: żeby pokazać równoliczność, **nie trzeba** budować bijekcji — wystarczą **dwie injekcje** w przeciwnych kierunkach (zwykle dużo łatwiejsze).

**Porównywanie mocy:** $|A|\le|B|$ oznacza "istnieje injekcja $A\to B$". Cantor-Bernstein mówi, że $|A|\le|B|$ i $|B|\le|A|$ dają $|A|=|B|$ (antysymetria — czyli moce są uporządkowane).

### 8.3. Twierdzenie Cantora (jest więcej niż jedna nieskończoność!)

**Twierdzenie Cantora.** Dla każdego zbioru $A$:
$$|A| < |\mathcal{P}(A)|,$$
tzn. zbiór potęgowy ma **ściśle większą** moc niż sam zbiór. Nie istnieje surjekcja $A\to\mathcal{P}(A)$.

Konsekwencja: istnieje **nieskończenie wiele różnych nieskończoności** ($|A|<|\mathcal P(A)|<|\mathcal P(\mathcal P(A))|<\dots$). Nie ma "największego" zbioru ani "zbioru wszystkich zbiorów".

---

## 9. Zbiory przeliczalne i continuum

### 9.1. Zbiory skończone i nieskończone

- **Skończony:** równoliczny z $\{1,2,\dots,n\}$ dla pewnego $n$ (lub pusty).
- **Nieskończony:** nie jest skończony.

### 9.2. Zbiory przeliczalne

**Definicja.** Zbiór jest **przeliczalny** (mocy $\aleph_0$, "alef zero"), gdy jest równoliczny ze zbiorem liczb naturalnych $\mathbb{N}$ — czyli jego elementy da się **ustawić w ciąg** $a_1,a_2,a_3,\dots$ (ponumerować).

**Co najwyżej przeliczalny** = skończony **lub** przeliczalny.

**Kluczowe twierdzenia:**
- Każdy nieskończony podzbiór zbioru przeliczalnego jest przeliczalny.
- **Suma co najwyżej przeliczalnej liczby zbiorów co najwyżej przeliczalnych jest co najwyżej przeliczalna.**
- Iloczyn kartezjański dwóch zbiorów przeliczalnych jest przeliczalny.

**Przykłady zbiorów przeliczalnych:**
- $\mathbb{Z}$ (całkowite) — przeliczalny: ustaw $0,1,-1,2,-2,3,-3,\dots$
- $\mathbb{N}\times\mathbb{N}$ — przeliczalny (numerowanie "po przekątnych").
- $\mathbb{Q}$ (wymierne) — **przeliczalny!** (mimo że gęsty) — metoda przekątniowa Cantora: ułóż ułamki w tabelę i przechodź po przekątnych, pomijając powtórzenia.

> **Intuicja, która zawodzi:** "wymiernych jest tyle samo co naturalnych" brzmi paradoksalnie, ale to prawda — obie moce to $\aleph_0$.

### 9.3. Zbiory mocy continuum

**Definicja.** Zbiór ma **moc continuum** $\mathfrak{c}$ (lub $2^{\aleph_0}$), gdy jest równoliczny z $\mathbb{R}$.

**Twierdzenie Cantora (nieprzeliczalność $\mathbb{R}$):** zbiór $\mathbb{R}$ liczb rzeczywistych jest **nieprzeliczalny**. Dowód — **metoda przekątniowa Cantora**: zakładamy, że da się wypisać wszystkie liczby z $[0,1]$ w ciąg, i konstruujemy liczbę różniącą się od $n$-tej na $n$-tym miejscu po przecinku — sprzeczność. Więc $|\mathbb{R}|>|\mathbb{N}|$.

**Przykłady zbiorów mocy continuum:**
- dowolny przedział $(a,b)$, $[a,b]$ — równoliczny z $\mathbb{R}$,
- $\mathbb{R}^n$ (każda skończona potęga!) — też moc continuum,
- $\mathcal{P}(\mathbb{N})$ — zbiór potęgowy liczb naturalnych ma moc $\mathfrak{c}=2^{\aleph_0}$,
- zbiór liczb niewymiernych.

**Hierarchia mocy:**
$$\underbrace{\text{skończone}}_{0,1,2,\dots} \;<\; \underbrace{\aleph_0}_{\mathbb{N},\mathbb{Z},\mathbb{Q}} \;<\; \underbrace{\mathfrak{c}=2^{\aleph_0}}_{\mathbb{R},\mathbb{R}^n,\mathcal P(\mathbb N)} \;<\; 2^{\mathfrak c} \;<\;\dots$$

### 9.4. Hipoteza continuum (ciekawostka, ale bywa wspominana)

**Hipoteza continuum (CH):** nie istnieje zbiór o mocy ściśle między $\aleph_0$ a $\mathfrak{c}$. Gödel i Cohen udowodnili, że CH jest **niezależna** od standardowych aksjomatów teorii mnogości (ZFC) — nie da się jej ani udowodnić, ani obalić.

### 9.5. Jak rozwiązywać zadania o mocach

- **Pokazać przeliczalność:** zbuduj numerowanie (ciąg) lub injekcję w $\mathbb{N}\times\mathbb{N}$/$\mathbb{Q}$, albo przedstaw zbiór jako co najwyżej przeliczalną sumę zbiorów przeliczalnych.
- **Pokazać moc continuum:** zbuduj bijekcję z $\mathbb{R}$ lub przedziałem, albo dwie injekcje + Cantor-Bernstein.
- **Pokazać nieprzeliczalność:** metoda przekątniowa albo injekcja z $\mathbb{R}$ (lub z $\mathcal P(\mathbb N)$).

---

## 10. Relacje porządku

### 10.1. Częściowy porządek

**Relacja częściowego porządku** (oznaczana $\preceq$ lub $\le$) w zbiorze $A$ to relacja, która jest:
1. **zwrotna**: $a\preceq a$,
2. **antysymetryczna**: $a\preceq b\land b\preceq a\Rightarrow a=b$,
3. **przechodnia**: $a\preceq b\land b\preceq c\Rightarrow a\preceq c$.

Parę $(A,\preceq)$ nazywamy **zbiorem (częściowo) uporządkowanym** (poset).

> Porównaj z relacją równoważności (§5): zamiast **symetrii** mamy **antysymetrię** — to jedyna, ale fundamentalna różnica. Symetria "skleja", antysymetria "ustawia w kolejności".

### 10.2. Porządek liniowy i częściowy — różnica

- **Porządek liniowy (całkowity):** dodatkowo **spójny** — każde dwa elementy są porównywalne: $\forall a,b\;(a\preceq b\lor b\preceq a)$.
- **Porządek częściowy:** mogą istnieć elementy **nieporównywalne** (ani $a\preceq b$, ani $b\preceq a$).

> **Przykłady.**
> - $(\mathbb{R},\le)$ — porządek **liniowy** (każde dwie liczby porównywalne).
> - $(\mathcal P(X),\subseteq)$ — porządek **częściowy**: zbiory $\{1\}$ i $\{2\}$ są nieporównywalne (żaden nie zawiera drugiego).
> - Podzielność $(\mathbb{N},\mid)$ — porządek częściowy: $2$ i $3$ nieporównywalne.

### 10.3. Wyróżnione elementy — uważać na definicje!

Niech $(A,\preceq)$ i $B\subseteq A$.

| Pojęcie | Definicja | Uwaga |
|---|---|---|
| element **największy** $A$ | $\forall a\in A:\; a\preceq m$ | porównywalny ze WSZYSTKIMI; jest co najwyżej jeden |
| element **najmniejszy** | $\forall a\in A:\; m\preceq a$ | jw. |
| element **maksymalny** | nie istnieje $a$ z $m\prec a$ | "nic nad nim", ale może być nieporównywalny z innymi; może być **wiele** |
| element **minimalny** | nie istnieje $a$ z $a\prec m$ | jw. |
| **ograniczenie górne** $B$ | $g\in A:\;\forall b\in B\; b\preceq g$ | niekoniecznie w $B$ |
| **ograniczenie dolne** $B$ | $d\in A:\;\forall b\in B\; d\preceq b$ | |
| **kres górny** (supremum) $\sup B$ | **najmniejsze** ograniczenie górne | |
| **kres dolny** (infimum) $\inf B$ | **największe** ograniczenie dolne | |

> **Najczęstsza pułapka:** "największy" ≠ "maksymalny"! Element największy jest porównywalny z każdym i jest jedyny; element maksymalny tylko "nie ma nic nad sobą" i może ich być kilka (w porządku częściowym). W porządku **liniowym** te pojęcia się pokrywają.

### 10.4. Łańcuchy i porządek dobry

- **Łańcuch** w $(A,\preceq)$ — podzbiór, w którym **każde dwa elementy są porównywalne** (czyli sam jest liniowo uporządkowany). Pojęcie kluczowe dla lematu Zorna.
- **Antyłańcuch** — podzbiór elementów parami nieporównywalnych.
- **Porządek dobry (dobre uporządkowanie):** porządek liniowy, w którym **każdy niepusty podzbiór ma element najmniejszy**. Przykład: $(\mathbb{N},\le)$ jest dobrze uporządkowany; $(\mathbb{R},\le)$ **nie** (np. przedział otwarty nie ma najmniejszego).

---

## 11. Lemat Kuratowskiego-Zorna

### 11.1. Sformułowanie

**Lemat Kuratowskiego-Zorna.** Niech $(A,\preceq)$ będzie niepustym zbiorem częściowo uporządkowanym, w którym **każdy łańcuch ma ograniczenie górne** (w $A$). Wtedy $A$ ma **element maksymalny**.

Rozłóżmy założenie na czynniki:
- $A\ne\varnothing$,
- dla **każdego** łańcucha $L\subseteq A$ istnieje $g\in A$ takie, że $b\preceq g$ dla wszystkich $b\in L$ ("łańcuch jest ograniczony z góry").

Teza: istnieje element maksymalny (nie da się go już "przebić" w górę).

### 11.2. Kontekst: aksjomat wyboru

Lemat Zorna jest **równoważny** (w ramach ZF) z:
- **Aksjomatem wyboru (AC):** dla każdej rodziny niepustych zbiorów istnieje funkcja wyboru, która z każdego wybiera po jednym elemencie.
- **Twierdzeniem Zermela o dobrym uporządkowaniu:** każdy zbiór można dobrze uporządkować.

Te trzy są logicznie równoważne — to "wielka trójca" teorii mnogości. Lemat Zorna jest zwykle najwygodniejszy w zastosowaniach.

### 11.3. Po co to się stosuje (typowe zastosowania)

Lemat Zorna służy do dowodzenia istnienia obiektów "maksymalnych", których nie da się skonstruować jawnie:
- każda przestrzeń wektorowa ma **bazę** (nawet nieskończeniewymiarowa),
- każdy ideał właściwy w pierścieniu zawiera się w **ideale maksymalnym**,
- twierdzenie Hahna-Banacha (analiza funkcjonalna).

### 11.4. Schemat dowodu "przez Zorna"

1. Zdefiniuj odpowiedni zbiór $A$ obiektów częściowych, uporządkowany inkluzją $\subseteq$ (zwykle).
2. Sprawdź, że $A\ne\varnothing$.
3. Weź dowolny łańcuch $L$ i pokaż, że jego **suma** (albo inne naturalne ograniczenie) jest elementem $A$ i ogranicza $L$ z góry.
4. Z lematu Zorna istnieje element maksymalny $m$.
5. Pokaż, że ta maksymalność oznacza żądaną własność (np. że $m$ jest bazą / ideałem maksymalnym).

---

## 12. Ściąga

### Symbole

| Symbol | Znaczenie | Symbol | Znaczenie |
|---|---|---|---|
| $\lnot$ | negacja | $\in,\notin$ | należy / nie należy |
| $\land,\lor$ | i, lub | $\subseteq$ | zawiera się |
| $\Rightarrow,\Leftrightarrow$ | implikacja, równoważność | $\cup,\cap,\setminus$ | suma, przekrój, różnica |
| $\forall,\exists$ | dla każdego, istnieje | $A'$ | dopełnienie |
| $A\times B$ | iloczyn kartezjański | $\mathcal P(A)$ | zbiór potęgowy |
| $\sim$ / $[a]$ | równoważność / klasa | $A/{\sim}$ | zbiór ilorazowy |
| $\aleph_0$ | moc przeliczalna | $\mathfrak c$ | moc continuum |
| $\preceq$ | porządek | $\sup,\inf$ | kres górny, dolny |

### Najważniejsze prawa

- **de Morgan (logika):** $\lnot(p\land q)\equiv\lnot p\lor\lnot q$; $\lnot(p\lor q)\equiv\lnot p\land\lnot q$.
- **de Morgan (zbiory):** $(A\cup B)'=A'\cap B'$; $(A\cap B)'=A'\cup B'$.
- **Negacja kwantyfikatorów:** $\lnot\forall x\,\varphi\equiv\exists x\,\lnot\varphi$; $\lnot\exists x\,\varphi\equiv\forall x\,\lnot\varphi$.
- **Negacja implikacji:** $\lnot(p\Rightarrow q)\equiv p\land\lnot q$.
- **Kontrapozycja:** $(p\Rightarrow q)\equiv(\lnot q\Rightarrow\lnot p)$.

### Definicje "do wyrecytowania"

- **Relacja równoważności:** zwrotna + symetryczna + przechodnia.
- **Częściowy porządek:** zwrotny + **antysymetryczny** + przechodni.
- **Funkcja:** każdemu argumentowi dokładnie jedna wartość.
- **Injekcja:** $f(a_1)=f(a_2)\Rightarrow a_1=a_2$. **Surjekcja:** $f(A)=B$. **Bijekcja:** obie.
- **Równoliczność:** istnieje bijekcja. **Cantor-Bernstein:** dwie injekcje ⇒ bijekcja.
- **Przeliczalny:** równoliczny z $\mathbb{N}$. $\mathbb{Z},\mathbb{Q}$ przeliczalne, $\mathbb{R}$ nieprzeliczalny (moc $\mathfrak c$).
- **Cantor:** $|A|<|\mathcal P(A)|$.
- **Lemat Zorna:** każdy łańcuch ograniczony z góry ⇒ istnieje element maksymalny.

### Strategie na zaliczenie

1. **Równość zbiorów** dowodź przez dwa zawierania ($A\subseteq B$ i $B\subseteq A$).
2. **Własności relacji/funkcji** — albo dowód ogólny, albo obalenie **jednym kontrprzykładem**.
3. **Negacja zdań z kwantyfikatorami** — zamieniaj $\forall\leftrightarrow\exists$ i neguj predykat na końcu; uważaj na kolejność kwantyfikatorów.
4. **Przeliczalność** — szukaj numerowania lub injekcji w $\mathbb N\times\mathbb N$; **continuum** — bijekcja z $\mathbb R$ albo Cantor-Bernstein.
5. **Największy vs maksymalny** — nie myl ich w porządkach częściowych.
6. **Implikacja** jest fałszywa tylko gdy poprzednik prawdziwy, a następnik fałszywy.
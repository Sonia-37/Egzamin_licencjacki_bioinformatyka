# Algebra liniowa z geometrią — kompletne notatki na egzamin

## Spis treści

1. [Liczby zespolone](#1-liczby-zespolone)
2. [Grupy (i struktury algebraiczne)](#2-grupy)
3. [Przestrzenie wektorowe, odwzorowania liniowe, macierze](#3-przestrzenie-wektorowe-odwzorowania-liniowe-macierze)
4. [Wyznaczniki](#4-wyznaczniki)
5. [Układy równań liniowych](#5-uklady-rownan-liniowych)
6. [Wartości i wektory własne](#6-wartosci-i-wektory-wlasne)
7. [Podprzestrzenie niezmiennicze i twierdzenie Jordana](#7-podprzestrzenie-niezmiennicze-i-twierdzenie-jordana)
8. [Iloczyn skalarny i ortogonalizacja](#8-iloczyn-skalarny-i-ortogonalizacja)
9. [Formy kwadratowe](#9-formy-kwadratowe)
10. [Geometria analityczna — krzywe stożkowe i kwadryki](#10-geometria-analityczna)
11. [Ściąga / wzory zbiorczo](#11-sciaga-wzory-zbiorczo)

---

## 1. Liczby zespolone

### 1.1. Po co i jak to rozumieć

Pewne równania nie mają rozwiązań w liczbach rzeczywistych — najprostsze to $x^2 = -1$. Wprowadzamy **jednostkę urojoną** $i$ taką, że:

$$i^2 = -1$$

Dzięki temu **każdy** wielomian stopnia $n$ ma dokładnie $n$ pierwiastków (z krotnościami) — to **zasadnicze twierdzenie algebry**. To jest główny powód, dla którego liczby zespolone są tak ważne.

**Definicja.** Liczba zespolona to wyrażenie postaci

$$z = a + bi, \qquad a, b \in \mathbb{R}$$

- $a = \operatorname{Re}(z)$ — **część rzeczywista**,
- $b = \operatorname{Im}(z)$ — **część urojona** (uwaga: to liczba rzeczywista $b$, a nie $bi$!).

Zbiór wszystkich liczb zespolonych oznaczamy $\mathbb{C}$. Geometrycznie $z = a+bi$ to **punkt $(a,b)$ na płaszczyźnie** (płaszczyzna Gaussa/zespolona): oś pozioma = część rzeczywista, oś pionowa = część urojona.

### 1.2. Działania w postaci algebraicznej

Dla $z = a+bi$, $w = c+di$:

| Działanie | Wzór |
|---|---|
| Suma | $z+w = (a+c) + (b+d)i$ |
| Różnica | $z-w = (a-c) + (b-d)i$ |
| Iloczyn | $z\cdot w = (ac-bd) + (ad+bc)i$ |

Iloczyn liczy się "jak nawiasy", pamiętając $i^2 = -1$:
$$(a+bi)(c+di) = ac + adi + bci + bd\underbrace{i^2}_{-1} = (ac-bd)+(ad+bc)i.$$

**Sprzężenie zespolone:** $\bar z = a - bi$ (odbicie względem osi rzeczywistej). Własności:
$$\overline{z+w}=\bar z+\bar w,\quad \overline{zw}=\bar z\,\bar w,\quad z\bar z = a^2+b^2 \in \mathbb{R}_{\ge 0}.$$

**Moduł** (długość wektora od $0$ do $z$):
$$|z| = \sqrt{a^2+b^2} = \sqrt{z\bar z}.$$

**Dzielenie** — sztuczka: pomnóż licznik i mianownik przez sprzężenie mianownika, żeby pozbyć się $i$ z dołu:
$$\frac{z}{w} = \frac{z\,\bar w}{w\,\bar w} = \frac{z\,\bar w}{|w|^2}.$$

> **Przykład.** $\dfrac{2+3i}{1-i} = \dfrac{(2+3i)(1+i)}{(1-i)(1+i)} = \dfrac{2+2i+3i+3i^2}{1^2+1^2} = \dfrac{(2-3)+(5)i}{2} = -\tfrac12 + \tfrac52 i.$

### 1.3. Postać trygonometryczna

Każdą niezerową liczbę zespoloną zapisujemy przez moduł $r=|z|$ i kąt $\varphi$ (argument):

$$z = r(\cos\varphi + i\sin\varphi).$$

- $r = |z| = \sqrt{a^2+b^2}$,
- $\varphi = \arg z$ — **argument**, kąt między dodatnią osią $\operatorname{Re}$ a wektorem $z$.

**Jak wyznaczyć argument (uwaga na ćwiartkę — najczęstszy błąd!):**
$$\tan\varphi = \frac{b}{a},$$
ale samo $\arctan(b/a)$ daje wynik tylko w przedziale $(-\tfrac\pi2,\tfrac\pi2)$. Trzeba **patrzeć na znaki $a$ i $b$**, by ustalić właściwą ćwiartkę:

- $a>0$: $\varphi=\arctan(b/a)$,
- $a<0$: $\varphi=\arctan(b/a)+\pi$,
- $a=0,\ b>0$: $\varphi=\tfrac\pi2$; $a=0,\ b<0$: $\varphi=-\tfrac\pi2$.

Argument jest określony z dokładnością do $2k\pi$. **Argument główny** $\operatorname{Arg} z$ to ten z przedziału $(-\pi,\pi]$ (lub $[0,2\pi)$ — zależnie od konwencji wykładowcy).

**Mnożenie i dzielenie w postaci trygonometrycznej** (tu tkwi cała siła tej postaci — kąty się dodają!):
$$z_1 z_2 = r_1 r_2\big(\cos(\varphi_1+\varphi_2) + i\sin(\varphi_1+\varphi_2)\big),$$
$$\frac{z_1}{z_2} = \frac{r_1}{r_2}\big(\cos(\varphi_1-\varphi_2) + i\sin(\varphi_1-\varphi_2)\big).$$

### 1.4. Wzór de Moivre'a (potęgowanie)

$$z^n = r^n\big(\cos(n\varphi) + i\sin(n\varphi)\big), \qquad n \in \mathbb{Z}.$$

To zamienia żmudne potęgowanie wielomianowe na proste podniesienie modułu do potęgi i pomnożenie kąta.

> **Przykład.** $(1+i)^{8}$. Mamy $r=\sqrt2$, $\varphi=\tfrac\pi4$. Więc $(1+i)^8 = (\sqrt2)^8(\cos 2\pi + i\sin 2\pi) = 16\cdot(1+0i)=16.$

### 1.5. Pierwiastkowanie — zawsze $n$ pierwiastków!

To częsty temat egzaminacyjny. **Pierwiastek stopnia $n$** z liczby $z=r(\cos\varphi+i\sin\varphi)$ ma **dokładnie $n$ różnych wartości**:

$$z_k = \sqrt[n]{r}\left(\cos\frac{\varphi+2k\pi}{n} + i\sin\frac{\varphi+2k\pi}{n}\right), \quad k=0,1,\dots,n-1.$$

**Interpretacja geometryczna:** wszystkie pierwiastki leżą na okręgu o promieniu $\sqrt[n]{r}$ i są rozmieszczone **równomiernie** (wierzchołki $n$-kąta foremnego), co $\tfrac{2\pi}{n}$.

> **Przykład.** Pierwiastki stopnia 3 z $z=8$: $r=8$, $\varphi=0$, $\sqrt[3]{8}=2$. Kąty: $0,\ \tfrac{2\pi}{3},\ \tfrac{4\pi}{3}$. Wyniki: $2$, $-1+i\sqrt3$, $-1-i\sqrt3$.

> **Pułapka:** $\sqrt[n]{z}$ w $\mathbb{C}$ to **zbiór $n$ liczb**, a nie jedna. Nie ma "tej jednej dodatniej" jak w $\mathbb{R}$.

### 1.6. Postać wykładnicza i wzór Eulera

$$e^{i\varphi} = \cos\varphi + i\sin\varphi \quad(\text{wzór Eulera}) \;\Rightarrow\; z = r e^{i\varphi}.$$

Szczególny przypadek (tożsamość Eulera): $e^{i\pi}+1=0$. Postać wykładnicza najwygodniej obsługuje mnożenie/potęgowanie: $e^{i\alpha}e^{i\beta}=e^{i(\alpha+\beta)}$.

### 1.7. Zasadnicze twierdzenie algebry

**Twierdzenie.** Każdy wielomian zespolony stopnia $n\ge 1$ ma w $\mathbb{C}$ dokładnie $n$ pierwiastków (liczonych z krotnościami). $\mathbb{C}$ jest **ciałem algebraicznie domkniętym**.

Konsekwencja praktyczna: dla wielomianów o współczynnikach rzeczywistych pierwiastki zespolone występują **parami sprzężonymi** ($z$ i $\bar z$).

### 1.8. Czego wymaga karta przedmiotu (U1)

Umieć wyznaczyć: część rzeczywistą, urojoną, moduł, argument, sumę, iloczyn, potęgę całkowitą liczby zespolonej. Wszystko powyżej to pokrywa.

---

## 2. Grupy

### 2.1. Działanie (operacja binarna)

**Definicja.** Działanie w zbiorze $G$ to funkcja $\ast: G\times G \to G$, która każdej parze $(a,b)$ przypisuje element $a\ast b \in G$. Kluczowe: wynik **musi należeć do $G$** (mówimy, że $G$ jest *zamknięty* na działanie).

### 2.2. Definicja grupy

**Definicja.** Para $(G, \ast)$ jest **grupą**, jeśli spełnione są trzy aksjomaty (plus zamkniętość):

1. **Łączność:** $(a\ast b)\ast c = a\ast(b\ast c)$ dla wszystkich $a,b,c\in G$.
2. **Element neutralny:** istnieje $e\in G$ taki, że $a\ast e = e\ast a = a$ dla każdego $a$.
3. **Element odwrotny:** dla każdego $a\in G$ istnieje $a^{-1}\in G$ taki, że $a\ast a^{-1} = a^{-1}\ast a = e$.

**Grupa przemienna (abelowa):** dodatkowo $a\ast b = b\ast a$ dla wszystkich $a,b$.

### 2.3. Jak sprawdzić, czy $(G,\ast)$ jest grupą — przepis na zadanie (U2)

Sprawdzaj po kolei:

1. **Zamkniętość** — czy $a\ast b$ zawsze wpada do $G$? (Częsty haczyk: np. $\mathbb{N}$ z odejmowaniem — wynik może być ujemny, więc nie jest zamknięty.)
2. **Łączność** — zwykle wynika z natury działania (dodawanie, mnożenie liczb, składanie funkcji są łączne).
3. **Element neutralny** — znajdź $e$. Dla $+$ to $0$, dla $\cdot$ to $1$.
4. **Elementy odwrotne** — czy **każdy** element ma odwrotny w $G$?
5. (Dla abelowości) **przemienność**.

> **Pułapka:** $(\mathbb{R}, \cdot)$ **nie** jest grupą, bo $0$ nie ma elementu odwrotnego. Ale $(\mathbb{R}\setminus\{0\}, \cdot)$ **jest** grupą abelową.

### 2.4. Ważne przykłady

| Zbiór i działanie | Grupa? | Neutralny | Odwrotny do $a$ |
|---|---|---|---|
| $(\mathbb{Z}, +)$ | tak, abelowa | $0$ | $-a$ |
| $(\mathbb{Q}, +),\ (\mathbb{R},+),\ (\mathbb{C},+)$ | tak, abelowe | $0$ | $-a$ |
| $(\mathbb{Q}\setminus\{0\}, \cdot)$ | tak, abelowa | $1$ | $1/a$ |
| $(\mathbb{N}, +)$ | **nie** (brak odwrotnych) | — | — |
| $(\mathbb{Z}, \cdot)$ | **nie** (tylko $\pm1$ mają odwrotne) | — | — |
| $(\mathbb{Z}_n, +)$ — reszty mod $n$ | tak, abelowa | $0$ | $n-a$ |
| $S_n$ — permutacje $n$ elementów, składanie | tak, **nieabelowa** dla $n\ge 3$ | identyczność | permutacja odwrotna |
| $GL_n(\mathbb{R})$ — macierze odwracalne, mnożenie | tak, nieabelowa dla $n\ge2$ | $I$ | $A^{-1}$ |

### 2.5. Podstawowe własności (wynikają z aksjomatów)

- Element neutralny jest **jednoznaczny**.
- Element odwrotny jest **jednoznaczny**.
- $(a^{-1})^{-1} = a$ oraz $(a\ast b)^{-1} = b^{-1}\ast a^{-1}$ (uwaga na odwrócenie kolejności!).
- Prawa skracania: jeśli $a\ast b = a\ast c$, to $b=c$.

### 2.6. Pojęcia poboczne (warto znać)

- **Podgrupa** $H\le G$: podzbiór $H\subseteq G$, który sam jest grupą z tym samym działaniem (zawiera $e$, zamknięty na działanie i branie odwrotności).
- **Rząd grupy** $|G|$: liczba jej elementów.
- **Ciało** (ważne dla dalszej części kursu): zbiór z dwoma działaniami $+$ i $\cdot$, gdzie $(G,+)$ to grupa abelowa, $(G\setminus\{0\},\cdot)$ to grupa abelowa i zachodzi rozdzielność. Przykłady: $\mathbb{Q}, \mathbb{R}, \mathbb{C}$. Przestrzenie wektorowe definiuje się nad ciałem.

---

## 3. Przestrzenie wektorowe, odwzorowania liniowe, macierze

### 3.1. Przestrzeń wektorowa — fundament

**Intuicja:** zbiór obiektów ("wektorów"), które można **dodawać** i **mnożyć przez liczby** (skalary), i wszystko zachowuje się "rozsądnie".

**Definicja.** Przestrzeń wektorowa nad ciałem $K$ (zwykle $\mathbb{R}$ lub $\mathbb{C}$) to zbiór $V$ z dodawaniem $+$ i mnożeniem przez skalar, spełniający aksjomaty: $(V,+)$ jest grupą abelową, oraz dla skalarów $\alpha,\beta$ i wektorów $u,v$:
$$\alpha(u+v)=\alpha u+\alpha v,\quad (\alpha+\beta)v=\alpha v+\beta v,\quad \alpha(\beta v)=(\alpha\beta)v,\quad 1\cdot v = v.$$

**Najważniejszy przykład:** $\mathbb{R}^n$ — wektory to ciągi $n$ liczb $(x_1,\dots,x_n)$.

### 3.2. Kombinacja liniowa, liniowa niezależność, baza, wymiar

- **Kombinacja liniowa** wektorów $v_1,\dots,v_k$: wyrażenie $\alpha_1 v_1 + \dots + \alpha_k v_k$.
- **Liniowa niezależność:** wektory $v_1,\dots,v_k$ są liniowo niezależne, gdy jedynym sposobem otrzymania wektora zerowego jest wzięcie wszystkich skalarów równych zeru:
$$\alpha_1 v_1+\dots+\alpha_k v_k = 0 \;\Longrightarrow\; \alpha_1=\dots=\alpha_k=0.$$
Jeśli istnieje nietrywialne rozwiązanie ($\ne$ same zera) — wektory są **liniowo zależne** (jeden da się wyrazić przez pozostałe).
- **Baza:** liniowo niezależny układ wektorów, który **rozpina** całą przestrzeń (każdy wektor jest ich kombinacją liniową, i to **jednoznacznie**).
- **Wymiar** $\dim V$: liczba wektorów w bazie (każda baza ma tyle samo wektorów). $\dim \mathbb{R}^n = n$.

**Jak sprawdzić liniową niezależność (praktyka):** ustaw wektory w kolumny/wiersze macierzy i policz **rząd** (lub wyznacznik, gdy macierz kwadratowa). Pełny rząd = niezależne. Wyznacznik $\ne 0$ = niezależne.

> **Przykład.** Czy $(1,2),(2,4)$ niezależne? $\det\begin{pmatrix}1&2\\2&4\end{pmatrix}=4-4=0$ → **zależne** (drugi to dwukrotność pierwszego).

### 3.3. Odwzorowanie (przekształcenie) liniowe

**Definicja.** $T:V\to W$ jest **liniowe**, jeśli zachowuje dodawanie i mnożenie przez skalar:
$$T(u+v)=T(u)+T(v), \qquad T(\alpha v)=\alpha\,T(v).$$
Równoważnie jednym warunkiem: $T(\alpha u + \beta v) = \alpha T(u)+\beta T(v)$.

Zawsze zachodzi $T(0)=0$ — szybki test: jeśli $T(0)\ne 0$, to odwzorowanie **nie** jest liniowe (np. $T(x)=x+1$ nie jest liniowe).

**Jądro i obraz:**
- **Jądro** $\ker T = \{v\in V: T(v)=0\}$ — co przechodzi na zero.
- **Obraz** $\operatorname{im} T = \{T(v): v\in V\}$ — wszystkie wyniki.

**Twierdzenie o rzędzie i defekcie (rank–nullity):**
$$\dim(\ker T) + \dim(\operatorname{im} T) = \dim V.$$
$T$ jest różnowartościowe $\iff \ker T=\{0\}$.

### 3.4. Macierz odwzorowania liniowego (U3)

Każde odwzorowanie liniowe $T:\mathbb{R}^n\to\mathbb{R}^m$ ma macierz $A$ wymiaru $m\times n$. **Kolumny macierzy to obrazy wektorów bazowych:**
$$A = \big[\, T(e_1)\ \big|\ T(e_2)\ \big|\ \cdots\ \big|\ T(e_n)\,\big].$$
Wtedy $T(x) = A x$ (mnożenie macierzy przez wektor).

> **Przykład (obrót o kąt $\theta$ na płaszczyźnie):**
> $T(e_1)=(\cos\theta,\sin\theta)$, $T(e_2)=(-\sin\theta,\cos\theta)$, więc
> $$A=\begin{pmatrix}\cos\theta & -\sin\theta\\ \sin\theta & \cos\theta\end{pmatrix}.$$

> **Przykład (rzut na oś $x$ w $\mathbb{R}^2$):** $T(x,y)=(x,0)$, macierz $\begin{pmatrix}1&0\\0&0\end{pmatrix}$.

### 3.5. Działania na macierzach

Niech $A=[a_{ij}]$, $B=[b_{ij}]$.

- **Dodawanie** (tylko jednakowe wymiary): $(A+B)_{ij}=a_{ij}+b_{ij}$.
- **Mnożenie przez skalar:** $(\alpha A)_{ij}=\alpha a_{ij}$.
- **Mnożenie macierzy** $A_{m\times n}\cdot B_{n\times p} = C_{m\times p}$ (liczba kolumn $A$ = liczba wierszy $B$!):
$$c_{ij}=\sum_{k=1}^{n} a_{ik}b_{kj} \quad(\text{"wiersz } i \text{ razy kolumna } j\text{"}).$$
- **Transpozycja** $A^{T}$: zamiana wierszy z kolumnami, $(A^T)_{ij}=a_{ji}$.

**Uwaga — najważniejsze pułapki mnożenia:**
- **Nieprzemienne:** zazwyczaj $AB \ne BA$.
- $(AB)^T = B^T A^T$ (odwrócenie kolejności).
- $AB=0$ **nie** implikuje $A=0$ lub $B=0$.
- Macierz **jednostkowa** $I$ (jedynki na przekątnej): $AI=IA=A$.

### 3.6. Macierz odwrotna

$A$ jest **odwracalna** (nieosobliwa), gdy istnieje $A^{-1}$ z $AA^{-1}=A^{-1}A=I$. Warunek: $A$ kwadratowa i $\det A \ne 0$.

**Metody wyznaczania $A^{-1}$:**
1. **Wzór dla $2\times2$** (warto znać na pamięć):
$$A=\begin{pmatrix}a&b\\c&d\end{pmatrix},\quad A^{-1}=\frac{1}{ad-bc}\begin{pmatrix}d&-b\\-c&a\end{pmatrix}.$$
2. **Metoda dołączonej macierzy:** $A^{-1}=\dfrac{1}{\det A}\,\operatorname{adj}(A)$, gdzie $\operatorname{adj}(A)=C^T$ (transponowana macierz dopełnień algebraicznych — patrz §4).
3. **Metoda Gaussa-Jordana:** zapisz $[A\,|\,I]$ i operacjami na wierszach sprowadź lewą część do $I$; prawa stanie się $A^{-1}$.

Własności: $(A^{-1})^{-1}=A$, $(AB)^{-1}=B^{-1}A^{-1}$, $(A^T)^{-1}=(A^{-1})^T$.

---

## 4. Wyznaczniki

### 4.1. Co to jest i jak rozumieć

Wyznacznik $\det A$ (oznaczany też $|A|$) to liczba przypisana macierzy **kwadratowej**. Interpretacja geometryczna: $|\det A|$ to **współczynnik skali objętości** przy przekształceniu $A$ (w 2D — pole, w 3D — objętość). Znak mówi o orientacji. Kluczowy fakt:

$$\boxed{\det A \ne 0 \iff A \text{ odwracalna} \iff \text{kolumny liniowo niezależne} \iff \text{układ } Ax=0 \text{ ma tylko } x=0.}$$

### 4.2. Wzory dla małych macierzy (U4)

**$1\times1$:** $\det[a]=a$.

**$2\times2$:**
$$\det\begin{pmatrix}a&b\\c&d\end{pmatrix}=ad-bc.$$

**$3\times3$ — reguła Sarrusa** (dopisz dwie pierwsze kolumny z prawej, mnóż po przekątnych):
$$\det\begin{pmatrix}a&b&c\\d&e&f\\g&h&i\end{pmatrix}=aei+bfg+cdh-ceg-afh-bdi.$$
> **Pułapka:** reguła Sarrusa działa **tylko** dla $3\times3$. Dla $4\times4$ i większych — Laplace lub eliminacja Gaussa.

### 4.3. Rozwinięcie Laplace'a (dowolny wymiar)

**Dopełnienie algebraiczne** $A_{ij}=(-1)^{i+j}M_{ij}$, gdzie $M_{ij}$ (minor) to wyznacznik macierzy po wykreśleniu $i$-tego wiersza i $j$-tej kolumny.

Rozwinięcie względem $i$-tego wiersza:
$$\det A=\sum_{j=1}^{n} a_{ij}A_{ij}=\sum_{j=1}^{n}(-1)^{i+j}a_{ij}M_{ij}.$$
**Strategia:** rozwijaj względem wiersza/kolumny z **największą liczbą zer** — najmniej liczenia. Szachownica znaków:
$$\begin{pmatrix}+&-&+&\cdots\\-&+&-&\cdots\\+&-&+&\cdots\\ \vdots&&&\ddots\end{pmatrix}.$$

### 4.4. Własności wyznacznika (skracają liczenie)

1. $\det(A^T)=\det A$.
2. Zamiana dwóch wierszy (kolumn) zmienia **znak** wyznacznika.
3. Pomnożenie wiersza przez $\alpha$ mnoży wyznacznik przez $\alpha$. Stąd $\det(\alpha A)=\alpha^n\det A$ dla $n\times n$.
4. Dodanie do wiersza wielokrotności innego wiersza **nie zmienia** wyznacznika (podstawa eliminacji Gaussa!).
5. Jeśli wiersz (kolumna) jest zerowy lub dwa wiersze są proporcjonalne → $\det A = 0$.
6. **Macierz trójkątna/diagonalna:** $\det = $ iloczyn elementów na przekątnej.
7. **Twierdzenie Cauchy'ego:** $\det(AB)=\det A\cdot\det B$.
8. $\det(A^{-1})=\dfrac{1}{\det A}$.

**Najszybsza metoda dla dużych macierzy:** sprowadź do postaci trójkątnej operacjami z pkt. 4 (nie zmieniają wyznacznika), pamiętając o znaku przy zamianach wierszy, i pomnóż przekątną.

---

## 5. Układy równań liniowych

### 5.1. Zapis

Układ $m$ równań z $n$ niewiadomymi zapisujemy macierzowo $Ax=b$, gdzie $A$ — macierz współczynników ($m\times n$), $x$ — wektor niewiadomych, $b$ — wektor wyrazów wolnych.

- $b=0$: układ **jednorodny** (zawsze ma rozwiązanie $x=0$, tzw. trywialne).
- $b\ne0$: układ **niejednorodny**.

### 5.2. Twierdzenie Kroneckera–Capellego (kiedy są rozwiązania)

Niech $r=\operatorname{rz}(A)$ — rząd macierzy współczynników, $r'=\operatorname{rz}([A|b])$ — rząd macierzy rozszerzonej, $n$ — liczba niewiadomych.

- $r \ne r'$ → układ **sprzeczny** (brak rozwiązań).
- $r = r' = n$ → **dokładnie jedno** rozwiązanie.
- $r = r' < n$ → **nieskończenie wiele** rozwiązań (z $n-r$ parametrami swobodnymi).

**Rząd macierzy** = liczba liniowo niezależnych wierszy = liczba niezerowych wierszy po sprowadzeniu do postaci schodkowej (eliminacja Gaussa).

### 5.3. Metoda eliminacji Gaussa (uniwersalna, U5)

Operacjami na wierszach (zamiana, mnożenie przez stałą $\ne0$, dodawanie wielokrotności innego wiersza) sprowadzamy $[A|b]$ do **postaci schodkowej**, a potem odczytujemy rozwiązanie "od dołu" (back-substitution). To działa **zawsze** — także gdy układ jest sprzeczny lub ma nieskończenie wiele rozwiązań.

### 5.4. Wzory Cramera (tylko gdy $A$ kwadratowa i $\det A\ne0$)

Dla układu $n\times n$ z $\det A \ne 0$:
$$x_i = \frac{\det A_i}{\det A},$$
gdzie $A_i$ powstaje z $A$ przez zastąpienie $i$-tej kolumny wektorem $b$.

> **Pułapka:** Cramer działa **tylko** dla układów kwadratowych z niezerowym wyznacznikiem. Gdy $\det A = 0$ — użyj Gaussa/Kroneckera-Capellego.

### 5.5. Struktura rozwiązań

Rozwiązanie ogólne układu niejednorodnego = **jedno rozwiązanie szczególne** + **rozwiązanie ogólne układu jednorodnego**:
$$x = x_{szcz} + x_{jednorodne}.$$
Zbiór rozwiązań układu jednorodnego $Ax=0$ to **podprzestrzeń** (jądro $A$) o wymiarze $n-r$.

---

## 6. Wartości i wektory własne

### 6.1. Intuicja

Większość wektorów przy przekształceniu $A$ zmienia kierunek. Ale niektóre, **wektory własne**, zachowują kierunek — zostają tylko rozciągnięte/ściśnięte (i ewentualnie odwrócone). Współczynnik tego rozciągnięcia to **wartość własna**.

**Definicja.** $\lambda$ jest **wartością własną** macierzy $A$, jeśli istnieje **niezerowy** wektor $v$ (wektor własny) taki, że
$$A v = \lambda v.$$

### 6.2. Jak wyznaczać (U6) — algorytm

Przekształcamy $Av=\lambda v$ do $(A-\lambda I)v = 0$. Żeby istniał niezerowy $v$, macierz $A-\lambda I$ musi być osobliwa:

**Krok 1 — wielomian charakterystyczny:**
$$w(\lambda) = \det(A-\lambda I) = 0.$$
To równanie (stopnia $n$) daje wartości własne.

**Krok 2 — wektory własne:** dla każdej $\lambda$ rozwiąż jednorodny układ
$$(A-\lambda I)v = 0.$$
Jego niezerowe rozwiązania to wektory własne. Zbiór wszystkich rozwiązań (z zerem) to **przestrzeń własna** $E_\lambda = \ker(A-\lambda I)$.

> **Przykład.** $A=\begin{pmatrix}2&1\\1&2\end{pmatrix}$.
> $\det\begin{pmatrix}2-\lambda&1\\1&2-\lambda\end{pmatrix}=(2-\lambda)^2-1=\lambda^2-4\lambda+3=(\lambda-1)(\lambda-3)$.
> Wartości własne: $\lambda_1=1,\ \lambda_2=3$.
> Dla $\lambda=1$: $(A-I)v=\begin{pmatrix}1&1\\1&1\end{pmatrix}v=0 \Rightarrow v=(1,-1)$.
> Dla $\lambda=3$: $\begin{pmatrix}-1&1\\1&-1\end{pmatrix}v=0 \Rightarrow v=(1,1)$.

### 6.3. Krotności — kluczowe pojęcia

- **Krotność algebraiczna** $\lambda$: ile razy $\lambda$ jest pierwiastkiem wielomianu charakterystycznego.
- **Krotność geometryczna** $\lambda$: $\dim E_\lambda$ = liczba liniowo niezależnych wektorów własnych dla $\lambda$.

Zawsze: $1 \le$ krotność geometryczna $\le$ krotność algebraiczna.

### 6.4. Diagonalizacja

Macierz $A$ jest **diagonalizowalna**, gdy istnieje baza złożona z wektorów własnych. Wtedy
$$A = PDP^{-1},$$
gdzie $D$ — diagonalna z wartościami własnymi, $P$ — macierz, której kolumny to odpowiadające wektory własne.

**Kryterium:** $A$ ($n\times n$) jest diagonalizowalna $\iff$ dla każdej wartości własnej krotność geometryczna = algebraicznej (czyli mamy łącznie $n$ liniowo niezależnych wektorów własnych).

- Jeśli $A$ ma $n$ **różnych** wartości własnych → na pewno diagonalizowalna.
- Jeśli krotność geometryczna $<$ algebraicznej dla którejś $\lambda$ → **nie** diagonalizowalna (potrzebna postać Jordana — §7).

**Zastosowanie:** $A^k = P D^k P^{-1}$ (potęgowanie macierzy staje się trywialne — przydatne np. w łańcuchach Markowa).

### 6.5. Przydatne fakty kontrolne

- **Ślad** (suma przekątnej) = suma wartości własnych: $\operatorname{tr}(A)=\sum\lambda_i$.
- **Wyznacznik** = iloczyn wartości własnych: $\det A = \prod\lambda_i$.
- Macierz **symetryczna rzeczywista** ma zawsze rzeczywiste wartości własne i jest **zawsze** diagonalizowalna w bazie ortonormalnej (twierdzenie spektralne — patrz §8/§9).

---

## 7. Podprzestrzenie niezmiennicze i twierdzenie Jordana

### 7.1. Podprzestrzeń niezmiennicza

**Definicja.** Podprzestrzeń $U\subseteq V$ jest **niezmiennicza** względem $T$ (lub $A$), jeśli $T(U)\subseteq U$ — czyli obraz każdego wektora z $U$ wciąż leży w $U$. Przykłady: $\{0\}$, cała $V$, każda przestrzeń własna $E_\lambda$, jądro, obraz.

Intuicja: niezmiennicze podprzestrzenie to "kawałki" przestrzeni, które przekształcenie traktuje osobno — pozwalają rozbić działanie $A$ na prostsze części.

### 7.2. Po co Jordan — gdy diagonalizacja zawodzi

Nie każdą macierz da się zdiagonalizować (gdy brakuje wektorów własnych). Twierdzenie Jordana mówi, że **zawsze** (nad $\mathbb{C}$) da się sprowadzić macierz do postaci "prawie diagonalnej" — **postaci Jordana**.

### 7.3. Klatka Jordana

**Klatka Jordana** rozmiaru $k$ dla wartości własnej $\lambda$ to macierz $k\times k$ z $\lambda$ na przekątnej i **jedynkami nad przekątną**:
$$J_k(\lambda)=\begin{pmatrix}\lambda&1&&\\&\lambda&1&\\&&\ddots&1\\&&&\lambda\end{pmatrix}.$$
Klatka $1\times1$ to po prostu $[\lambda]$ (to zwykły wektor własny).

### 7.4. Twierdzenie Jordana

**Twierdzenie.** Każda macierz kwadratowa $A$ nad ciałem algebraicznie domkniętym (np. $\mathbb{C}$) jest podobna do macierzy blokowo-diagonalnej złożonej z klatek Jordana:
$$A = P J P^{-1}, \qquad J = \operatorname{diag}\big(J_{k_1}(\lambda_1), J_{k_2}(\lambda_2),\dots\big).$$
Postać $J$ jest jednoznaczna z dokładnością do kolejności klatek.

### 7.5. Jak ustalić postać Jordana

Dla wartości własnej $\lambda$ o krotności algebraicznej $a$:

1. **Liczba klatek** dla $\lambda$ = krotność geometryczna = $\dim\ker(A-\lambda I)$.
2. **Łączny rozmiar** klatek dla $\lambda$ = krotność algebraiczna $a$.
3. Dokładne rozmiary klatek odczytuje się z ciągu $\dim\ker(A-\lambda I)^j$ dla $j=1,2,\dots$ (liczby wektorów własnych uogólnionych).

**Wektory własne uogólnione:** wektory spełniające $(A-\lambda I)^k v = 0$ dla pewnego $k\ge1$ (zwykły wektor własny to przypadek $k=1$). One uzupełniają bazę, gdy zwykłych wektorów własnych jest za mało.

> **Najprostszy nietrywialny przykład:** $A=\begin{pmatrix}2&1\\0&2\end{pmatrix}$. Jedyna wartość własna $\lambda=2$ ma krotność algebraiczną 2, ale $\ker(A-2I)$ jest 1-wymiarowe (tylko $(1,0)$). Więc jedna klatka $2\times2$ — to już jest postać Jordana.

---

## 8. Iloczyn skalarny i ortogonalizacja

### 8.1. Iloczyn skalarny

**Definicja (w $\mathbb{R}^n$):** standardowy iloczyn skalarny wektorów $u=(u_1,\dots,u_n)$, $v=(v_1,\dots,v_n)$:
$$\langle u,v\rangle = u\cdot v = u_1v_1+u_2v_2+\dots+u_nv_n.$$

**Aksjomaty iloczynu skalarnego** (rzeczywistego) — funkcja $\langle\cdot,\cdot\rangle$ jest:
1. **Symetryczna:** $\langle u,v\rangle=\langle v,u\rangle$.
2. **Liniowa** względem każdego argumentu: $\langle \alpha u+\beta w, v\rangle=\alpha\langle u,v\rangle+\beta\langle w,v\rangle$.
3. **Dodatnio określona:** $\langle v,v\rangle\ge0$, przy czym $=0$ tylko dla $v=0$.

### 8.2. Norma, kąt, ortogonalność

- **Norma (długość):** $\|v\|=\sqrt{\langle v,v\rangle}$.
- **Kąt** między wektorami: $\cos\theta=\dfrac{\langle u,v\rangle}{\|u\|\,\|v\|}$.
- **Ortogonalność (prostopadłość):** $u\perp v \iff \langle u,v\rangle=0$.
- **Nierówność Cauchy'ego-Schwarza:** $|\langle u,v\rangle|\le\|u\|\,\|v\|$.
- **Nierówność trójkąta:** $\|u+v\|\le\|u\|+\|v\|$.

**Wektor jednostkowy (unormowanie):** $\hat v = \dfrac{v}{\|v\|}$ ma długość 1.

### 8.3. Bazy ortogonalne i ortonormalne

- **Ortogonalna:** wektory parami prostopadłe.
- **Ortonormalna:** ortogonalna + każdy wektor ma długość 1.

Bazy ortonormalne są wygodne: współrzędne wektora $v$ to po prostu iloczyny skalarne $\langle v, e_i\rangle$, a obliczenia bardzo się upraszczają.

### 8.4. Rzut ortogonalny

Rzut wektora $v$ na kierunek wektora $u$:
$$\operatorname{proj}_u v = \frac{\langle v,u\rangle}{\langle u,u\rangle}\,u.$$

### 8.5. Proces ortogonalizacji Grama-Schmidta (U7) — algorytm

Mając bazę $v_1,\dots,v_n$, budujemy bazę **ortogonalną** $u_1,\dots,u_n$ (odejmując od każdego kolejnego wektora jego rzuty na już zbudowane):

$$u_1 = v_1,$$
$$u_2 = v_2 - \frac{\langle v_2,u_1\rangle}{\langle u_1,u_1\rangle}u_1,$$
$$u_3 = v_3 - \frac{\langle v_3,u_1\rangle}{\langle u_1,u_1\rangle}u_1 - \frac{\langle v_3,u_2\rangle}{\langle u_2,u_2\rangle}u_2,$$
$$\vdots$$
$$u_k = v_k - \sum_{j=1}^{k-1}\frac{\langle v_k,u_j\rangle}{\langle u_j,u_j\rangle}u_j.$$

Na koniec **unormuj**: $e_k = u_k/\|u_k\|$ — dostajesz bazę **ortonormalną**.

> **Przykład.** $v_1=(1,1,0)$, $v_2=(1,0,1)$.
> $u_1=(1,1,0)$.
> $\langle v_2,u_1\rangle=1$, $\langle u_1,u_1\rangle=2$, więc $u_2=(1,0,1)-\tfrac12(1,1,0)=(\tfrac12,-\tfrac12,1)$.
> Sprawdzenie: $\langle u_1,u_2\rangle = \tfrac12-\tfrac12+0=0$ ✓ (prostopadłe).

> **Pułapka:** kolejność ma znaczenie tylko o tyle, że bierzemy rzuty na **już zortogonalizowane** $u_j$, a nie na oryginalne $v_j$. Częsty błąd to rzutowanie na $v_j$.

---

## 9. Formy kwadratowe

### 9.1. Definicja

**Forma kwadratowa** to jednorodny wielomian stopnia 2:
$$q(x_1,\dots,x_n) = \sum_{i\le j} a_{ij}x_i x_j.$$
Np. $q(x,y)=2x^2+3xy+y^2$.

Każdą formę zapisujemy macierzowo:
$$q(x) = x^T A x,$$
gdzie $A$ jest **symetryczna** ($A=A^T$). Na przekątnej idą współczynniki przy kwadratach, a współczynnik przy $x_ix_j$ ($i\ne j$) **dzielimy na pół** i wstawiamy w pozycje $a_{ij}$ i $a_{ji}$.

> **Przykład.** $q(x,y)=2x^2+3xy+y^2 \Rightarrow A=\begin{pmatrix}2 & 3/2\\ 3/2 & 1\end{pmatrix}.$
> (Połowa przy mieszanym wyrazie — to najczęstszy błąd!)

### 9.2. Określoność formy (U8)

Forma $q$ jest:
- **dodatnio określona**, gdy $q(x)>0$ dla każdego $x\ne0$;
- **ujemnie określona**, gdy $q(x)<0$ dla każdego $x\ne0$;
- **dodatnio/ujemnie półokreślona**, gdy $\ge0$ / $\le0$ (z osiągnięciem zera dla pewnych $x\ne0$);
- **nieokreślona**, gdy przyjmuje wartości i dodatnie, i ujemne.

### 9.3. Kryterium Sylvestera (przez minory główne)

Niech $D_k$ — wyznacznik lewego górnego bloku $k\times k$ macierzy $A$ (minor wiodący).

- **Dodatnio określona** $\iff$ wszystkie $D_k>0$: $D_1>0, D_2>0,\dots,D_n>0$.
- **Ujemnie określona** $\iff$ znaki naprzemienne zaczynając od minusa: $D_1<0, D_2>0, D_3<0,\dots$ (czyli $(-1)^k D_k>0$).
- Jeśli żaden z tych wzorców nie zachodzi (a wszystkie $D_k\ne0$) → **nieokreślona**.

> **Pułapka:** kryterium Sylvestera w tej postaci rozstrzyga **określoność**, ale przypadki półokreślone (gdy jakieś $D_k=0$) wymagają ostrożności — wtedy lepiej liczyć wartości własne.

### 9.4. Kryterium przez wartości własne (najpewniejsze)

Policz wartości własne macierzy symetrycznej $A$ (są zawsze rzeczywiste):
- wszystkie $>0$ → dodatnio określona;
- wszystkie $<0$ → ujemnie określona;
- wszystkie $\ge0$ (jest zero) → dodatnio półokreślona;
- różne znaki → nieokreślona.

### 9.5. Postać kanoniczna

Twierdzenie (o osiach głównych / spektralne dla form): każdą formę kwadratową można sprowadzić do **postaci kanonicznej** (bez wyrazów mieszanych)
$$q = \lambda_1 y_1^2 + \lambda_2 y_2^2 + \dots + \lambda_n y_n^2$$
przez zamianę zmiennych do bazy ortonormalnej wektorów własnych $A$. Liczby dodatnich, ujemnych i zerowych współczynników (sygnatura) są **niezmiennikiem** (prawo bezwładności Sylvestera).

---

## 10. Geometria analityczna

### 10.1. Prosta na płaszczyźnie

| Postać | Wzór |
|---|---|
| ogólna | $Ax+By+C=0$ |
| kierunkowa | $y=ax+b$ ($a$ — współczynnik kierunkowy, $b$ — przesunięcie) |
| kanoniczna / parametryczna | $\dfrac{x-x_0}{u_1}=\dfrac{y-y_0}{u_2}$ lub $(x,y)=(x_0,y_0)+t(u_1,u_2)$ |

- **Wektor normalny** prostej $Ax+By+C=0$: $\vec n=(A,B)$. **Wektor kierunkowy:** $(-B,A)$.
- **Równoległość:** te same kierunki ($a_1=a_2$). **Prostopadłość:** $a_1a_2=-1$ lub $\vec n_1\perp\vec n_2$.
- **Odległość punktu** $(x_0,y_0)$ od prostej: $d=\dfrac{|Ax_0+By_0+C|}{\sqrt{A^2+B^2}}$.

### 10.2. Krzywe stożkowe (rozpoznawanie — U9)

Ogólne równanie drugiego stopnia: $Ax^2+Bxy+Cy^2+Dx+Ey+F=0$. Po sprowadzeniu do postaci kanonicznej (przesunięcie układu / obrót likwidujący wyraz $xy$):

**Okrąg** — środek $(a,b)$, promień $r$:
$$(x-a)^2+(y-b)^2=r^2.$$
Rozpoznanie: współczynniki przy $x^2$ i $y^2$ **równe**, brak wyrazu $xy$.

**Elipsa** — półosie $a,b$:
$$\frac{x^2}{a^2}+\frac{y^2}{b^2}=1.$$
Dwa kwadraty, **te same znaki** (oba +), różne mianowniki. Suma odległości od dwóch ognisk stała.

**Hiperbola:**
$$\frac{x^2}{a^2}-\frac{y^2}{b^2}=1.$$
Dwa kwadraty, **różne znaki**. Ma asymptoty $y=\pm\tfrac{b}{a}x$. Różnica odległości od ognisk stała.

**Parabola:**
$$y^2=2px \quad\text{lub}\quad y=ax^2+bx+c.$$
**Tylko jeden** wyraz kwadratowy (drugiej zmiennej brak w kwadracie).

**Szybka tabela rozpoznawania** (po sprowadzeniu, znak wyznacznika $\delta=B^2-4AC$ formy kwadratowej):

| $\delta=B^2-4AC$ | Krzywa |
|---|---|
| $<0$ | elipsa (lub okrąg, gdy $A=C,\,B=0$) |
| $=0$ | parabola |
| $>0$ | hiperbola |

> **Przypadki zdegenerowane (wyjątki):** równanie 2. stopnia może dawać też zbiory zdegenerowane: punkt ($x^2+y^2=0$), parę prostych ($x^2-y^2=0$), pustą krzywą ($x^2+y^2=-1$), prostą podwójną. Warto o nich pamiętać — egzaminatorzy lubią takie podchwytliwe przykłady.

### 10.3. Geometria w przestrzeni

**Płaszczyzna** — postać ogólna ($\vec n=(A,B,C)$ to wektor normalny):
$$Ax+By+Cz+D=0.$$
Przez punkt $P_0$ o normalnej $\vec n$: $\vec n\cdot(\vec r-\vec r_0)=0$.

**Prosta w przestrzeni** — parametrycznie (punkt $P_0$, kierunek $\vec u$):
$$(x,y,z)=(x_0,y_0,z_0)+t(u_1,u_2,u_3),$$
lub kanonicznie $\dfrac{x-x_0}{u_1}=\dfrac{y-y_0}{u_2}=\dfrac{z-z_0}{u_3}$.

**Iloczyn wektorowy** (do wyznaczania normalnych/kierunków): $\vec a\times\vec b$ jest prostopadły do obu, $\|\vec a\times\vec b\|$ = pole równoległoboku.

**Odległość punktu od płaszczyzny:** $d=\dfrac{|Ax_0+By_0+Cz_0+D|}{\sqrt{A^2+B^2+C^2}}$.

### 10.4. Kwadryki (powierzchnie drugiego stopnia — U9)

| Nazwa | Równanie kanoniczne | Jak rozpoznać |
|---|---|---|
| **Sfera** | $x^2+y^2+z^2=r^2$ | trzy kwadraty, równe współczynniki, znak + |
| **Elipsoida** | $\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}+\dfrac{z^2}{c^2}=1$ | trzy kwadraty, wszystkie + , różne mianowniki |
| **Hiperboloida jednopowłokowa** | $\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}-\dfrac{z^2}{c^2}=1$ | **jeden** znak minus, prawa strona $=1$ (spójna, "klepsydra na odwrót") |
| **Hiperboloida dwupowłokowa** | $\dfrac{x^2}{a^2}-\dfrac{y^2}{b^2}-\dfrac{z^2}{c^2}=1$ | **dwa** znaki minus, $=1$ (dwie osobne czasze) |
| **Paraboloida eliptyczna** | $z=\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}$ | jedna zmienna w pierwszej potędze, dwa kwadraty tego samego znaku |
| **Paraboloida hiperboliczna ("siodło")** | $z=\dfrac{x^2}{a^2}-\dfrac{y^2}{b^2}$ | jedna zmienna liniowo, dwa kwadraty **różnych** znaków |
| **Stożek** | $\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}-\dfrac{z^2}{c^2}=0$ | suma kwadratów = 0 (prawa strona zero) |

**Reguła praktyczna rozpoznawania kwadryk:**
1. Policz, ile zmiennych jest w kwadracie. Trzy → elipsoida/hiperboloida/stożek. Dwie + jedna liniowa → paraboloida.
2. Patrz na **znaki** wyrazów kwadratowych: same plusy → elipsoida/paraboloida eliptyczna; mieszane → hiperboloida/paraboloida hiperboliczna.
3. Patrz na **prawą stronę:** $=1$ → elipsoida/hiperboloida; $=0$ → stożek; brak (zamiast tego liniowa zmienna) → paraboloida.

---

## 11. Ściąga — wzory zbiorczo

**Liczby zespolone:** $|z|=\sqrt{a^2+b^2}$; $z=r(\cos\varphi+i\sin\varphi)=re^{i\varphi}$; de Moivre $z^n=r^n(\cos n\varphi+i\sin n\varphi)$; pierwiastki $\sqrt[n]{r}\,e^{i(\varphi+2k\pi)/n}$, $k=0,\dots,n-1$.

**Grupa:** łączność + neutralny + odwrotny (+ przemienność = abelowa).

**Macierz odwzorowania:** kolumny = obrazy wektorów bazowych. $T(x)=Ax$.

**Mnożenie macierzy:** $c_{ij}=\sum_k a_{ik}b_{kj}$; nieprzemienne; $(AB)^T=B^TA^T$; $(AB)^{-1}=B^{-1}A^{-1}$.

**Odwrotność $2\times2$:** $\frac{1}{ad-bc}\begin{pmatrix}d&-b\\-c&a\end{pmatrix}$.

**Wyznacznik:** $2\times2$: $ad-bc$; $3\times3$: Sarrus; więcej: Laplace lub Gauss. $\det(AB)=\det A\det B$; $\det A\ne0\iff$ odwracalna.

**Układy:** Kronecker-Capelli ($r$ vs $r'$ vs $n$); Cramer $x_i=\det A_i/\det A$ (gdy $\det A\ne0$); Gauss zawsze.

**Wartości własne:** $\det(A-\lambda I)=0$; wektory: $(A-\lambda I)v=0$; $\operatorname{tr}A=\sum\lambda_i$, $\det A=\prod\lambda_i$.

**Jordan:** klatka = $\lambda$ na przekątnej, jedynki nad nią; liczba klatek dla $\lambda$ = krotność geometryczna.

**Gram-Schmidt:** $u_k=v_k-\sum_{j<k}\frac{\langle v_k,u_j\rangle}{\langle u_j,u_j\rangle}u_j$, potem unormuj.

**Forma kwadratowa:** $q(x)=x^TAx$, $A$ symetryczna (mieszane wyrazy /2); Sylvester: dodatnio określona $\iff$ wszystkie minory wiodące $>0$; przez wartości własne — najpewniej.

**Stożkowe:** $\delta=B^2-4AC$: $<0$ elipsa, $=0$ parabola, $>0$ hiperbola.

**Kwadryki:** licz kwadraty + znaki + prawą stronę (patrz tabela §10.4).

---

### Strategia na egzamin pisemny

1. **Zawsze sprawdzaj $\det\ne0$** zanim użyjesz Cramera lub liczysz odwrotność.
2. **Wektory własne** zawsze podstawiaj z powrotem: $Av=\lambda v$ — szybka kontrola.
3. **Gram-Schmidt** — sprawdzaj ortogonalność iloczynem skalarnym po każdym kroku.
4. **Argument liczby zespolonej** — zawsze ustal ćwiartkę po znakach $a,b$.
5. **Forma kwadratowa** — pamiętaj o dzieleniu wyrazów mieszanych na pół przy budowie macierzy.
6. **Kwadryki/stożkowe** — najpierw uporządkuj równanie (kwadraty, znaki, prawa strona), potem dopasuj wzorzec.

# Analiza Matematyczna 2 — Kompletne notatki egzaminacyjne

## Spis treści

1. [Całki niewłaściwe](#1-całki-niewłaściwe)
2. [Szeregi liczbowe](#2-szeregi-liczbowe)
3. [Szeregi potęgowe](#3-szeregi-potęgowe)
4. [Granica i ciągłość funkcji wielu zmiennych](#4-granica-i-ciągłość-funkcji-wielu-zmiennych)
5. [Pochodne cząstkowe i kierunkowe](#5-pochodne-cząstkowe-i-kierunkowe)
6. [Gradient i różniczka](#6-gradient-i-różniczka)
7. [Różniczki wyższych rzędów i wzór Taylora](#7-różniczki-wyższych-rzędów-i-wzór-taylora)
8. [Ekstrema funkcji wielu zmiennych](#8-ekstrema-funkcji-wielu-zmiennych)
9. [Całka Riemanna funkcji wielu zmiennych](#9-całka-riemanna-funkcji-wielu-zmiennych)
10. [Twierdzenie Fubiniego w obszarze normalnym](#10-twierdzenie-fubiniego-w-obszarze-normalnym)
11. [Twierdzenie o zmianie zmiennych w całce](#11-twierdzenie-o-zmianie-zmiennych-w-całce)
12. [Zastosowania całek funkcji wielu zmiennych](#12-zastosowania-całek-funkcji-wielu-zmiennych)
- [Dodatek A — Tabela kryteriów zbieżności szeregów](#dodatek-a--tabela-kryteriów-zbieżności-szeregów)
- [Dodatek B — Jakobiany najczęstszych zamian zmiennych](#dodatek-b--jakobiany-najczęstszych-zamian-zmiennych)
- [Dodatek C — Najczęstsze błędy egzaminacyjne](#dodatek-c--najczęstsze-błędy-egzaminacyjne)

Każdy rozdział ma stały układ: **Intuicja → Definicje → Twierdzenia (z założeniami!) → Jak liczyć → Pułapki i wyjątki**.

---

# 1. Całki niewłaściwe

## 1.1. Intuicja

Zwykła całka Riemanna $\int_a^b f$ wymaga **skończonego przedziału** i **ograniczonej funkcji**. Całka niewłaściwa rozszerza to pojęcie na dwie sytuacje: gdy przedział jest nieskończony, albo gdy funkcja „ucieka do nieskończoności" w jakimś punkcie. Definiujemy ją przez **granicę zwykłych całek**.

## 1.2. Całka niewłaściwa I rodzaju (nieskończony przedział)

$$\int_a^{\infty} f(x)\,dx = \lim_{T\to\infty}\int_a^{T} f(x)\,dx.$$
Analogicznie $\int_{-\infty}^{b}$. Dla całki po całej prostej rozbijamy w dowolnym punkcie $c$:
$$\int_{-\infty}^{\infty} f = \int_{-\infty}^{c} f + \int_{c}^{\infty} f,$$
i **obie** części muszą być zbieżne (osobno).

- Jeśli granica jest **skończona** → całka **zbieżna**.
- Jeśli granica jest nieskończona lub nie istnieje → całka **rozbieżna**.

## 1.3. Całka niewłaściwa II rodzaju (funkcja nieograniczona)

Gdy $f$ ma osobliwość (dąży do $\pm\infty$) w końcu przedziału, np. w $b$:
$$\int_a^{b} f(x)\,dx = \lim_{\varepsilon\to 0^+}\int_a^{b-\varepsilon} f(x)\,dx.$$
Gdy osobliwość jest w $a$: $\lim_{\varepsilon\to 0^+}\int_{a+\varepsilon}^{b}$. Gdy osobliwość jest w **środku** przedziału $c\in(a,b)$ — rozbijamy na dwie całki i badamy obie osobno.

> **Pułapka:** nie wolno „przeoczyć" osobliwości wewnątrz przedziału. $\int_{-1}^{1}\frac{dx}{x^2}$ wygląda niewinnie, ale w $0$ funkcja wybucha — to całka niewłaściwa i w dodatku **rozbieżna**.

## 1.4. Całki wzorcowe (do zapamiętania!)

$$\int_1^{\infty}\frac{dx}{x^p}\ \text{jest}\ \begin{cases}\text{zbieżna} & p>1\\ \text{rozbieżna} & p\le 1\end{cases}\qquad\qquad \int_0^{1}\frac{dx}{x^p}\ \text{jest}\ \begin{cases}\text{zbieżna} & p<1\\ \text{rozbieżna} & p\ge 1\end{cases}$$

Zauważ **odwrotny** warunek! „Na nieskończoności" groźne są małe $p$ (funkcja za wolno maleje), a „przy zerze" groźne są duże $p$ (funkcja za szybko rośnie). Dodatkowo:
$$\int_0^\infty e^{-\lambda x}\,dx = \frac{1}{\lambda}\ (\lambda>0),\qquad \int_2^\infty \frac{dx}{x(\ln x)^p}\ \text{zbieżna}\iff p>1.$$

## 1.5. Kryteria zbieżności (gdy nie umiemy policzyć całki wprost)

Dla funkcji **nieujemnych** $f,g\ge 0$:

**Kryterium porównawcze.** Jeśli $0\le f(x)\le g(x)$ (od pewnego miejsca), to:
- $\int g$ zbieżna $\Rightarrow \int f$ zbieżna („mniejsza od zbieżnej jest zbieżna"),
- $\int f$ rozbieżna $\Rightarrow \int g$ rozbieżna.

**Kryterium ilorazowe (porównawcze w formie granicznej).** Jeśli $\lim_{x\to\infty}\frac{f(x)}{g(x)} = L$, $0<L<\infty$, to całki $\int f$ i $\int g$ są **jednocześnie** zbieżne albo rozbieżne. To najwygodniejsze narzędzie: dobieramy $g$ jako „wzorzec" $\frac{1}{x^p}$.

Przykład: $\int_1^\infty \frac{x}{x^3+1}\,dx$. Dla dużych $x$ zachowuje się jak $\frac{x}{x^3}=\frac{1}{x^2}$ ($p=2>1$ → zbieżna). Iloraz $\frac{x/(x^3+1)}{1/x^2}\to 1$, więc nasza całka też jest zbieżna.

## 1.6. Zbieżność bezwzględna

Całka $\int f$ jest **bezwzględnie zbieżna**, gdy zbieżna jest $\int |f|$. Zbieżność bezwzględna $\Rightarrow$ zbieżność zwykła (nie odwrotnie). To pozwala stosować kryteria porównawcze (dla $|f|$) także do funkcji zmieniających znak.

---

# 2. Szeregi liczbowe

## 2.1. Intuicja

Szereg to **nieskończona suma** $a_1 + a_2 + a_3 + \dots$. Nie da się dodać nieskończenie wielu liczb „naraz", więc definiujemy to jako granicę **sum częściowych** (dodajemy coraz więcej wyrazów i patrzymy, do czego zmierza wynik).

## 2.2. Definicja

Dla ciągu $(a_n)$ tworzymy ciąg **sum częściowych**:
$$S_N = \sum_{n=1}^{N} a_n = a_1 + a_2 + \dots + a_N.$$
**Szereg** $\sum_{n=1}^\infty a_n$ jest **zbieżny**, gdy istnieje skończona granica $S=\lim_{N\to\infty} S_N$; wtedy $S$ to jego suma. W przeciwnym razie szereg jest **rozbieżny**.

## 2.3. Warunek konieczny zbieżności (pierwsza rzecz do sprawdzenia!)

$$\text{Jeśli } \sum a_n \text{ zbieżny, to } \lim_{n\to\infty} a_n = 0.$$
**Kontrapozycja (praktyczna):** jeśli $a_n \not\to 0$, to szereg jest **rozbieżny**. To pierwszy test — szybki i darmowy.

> **Uwaga — to NIE jest warunek wystarczający!** $\lim a_n = 0$ nie gwarantuje zbieżności. Sztandarowy kontrprzykład: szereg harmoniczny $\sum \frac{1}{n}$ ma $a_n = \frac1n \to 0$, a mimo to jest **rozbieżny**.

## 2.4. Szeregi wzorcowe

**Szereg geometryczny** $\sum_{n=0}^\infty q^n$:
$$\text{zbieżny}\iff |q|<1,\quad\text{wtedy suma} = \frac{1}{1-q}\quad\left(\text{ogólnie } \sum_{n=0}^\infty aq^n = \frac{a}{1-q}\right).$$

**Szereg harmoniczny rzędu $p$ (Dirichleta)** $\sum \frac{1}{n^p}$:
$$\text{zbieżny}\iff p>1.$$
W szczególności $\sum\frac1n$ rozbieżny, $\sum\frac{1}{n^2}$ zbieżny (suma $=\frac{\pi^2}{6}$).

## 2.5. Kryteria zbieżności dla szeregów o wyrazach nieujemnych

**Kryterium porównawcze.** Jeśli $0\le a_n\le b_n$: $\sum b_n$ zbieżny $\Rightarrow \sum a_n$ zbieżny; $\sum a_n$ rozbieżny $\Rightarrow \sum b_n$ rozbieżny.

**Kryterium ilorazowe (porównawcze graniczne).** Jeśli $\lim\frac{a_n}{b_n}=L\in(0,\infty)$, to $\sum a_n$ i $\sum b_n$ zachowują się tak samo. Wzorzec zwykle $\frac{1}{n^p}$.

**Kryterium d'Alemberta (ilorazowe).** Niech $g=\lim\left|\frac{a_{n+1}}{a_n}\right|$:
- $g<1$ → **zbieżny** (bezwzględnie),
- $g>1$ → **rozbieżny**,
- $g=1$ → **nie rozstrzyga** (trzeba innego kryterium).

Najlepsze przy silniach i potęgach ($n!$, $a^n$).

**Kryterium Cauchy'ego (pierwiastkowe).** Niech $g=\lim\sqrt[n]{|a_n|}$:
- $g<1$ → zbieżny, $g>1$ → rozbieżny, $g=1$ → nie rozstrzyga.

Najlepsze, gdy $a_n$ zawiera $n$-tą potęgę, np. $\left(\frac{n}{n+1}\right)^{n^2}$.

**Kryterium całkowe.** Jeśli $f$ jest dodatnia, malejąca, $f(n)=a_n$, to $\sum a_n$ i $\int_1^\infty f(x)\,dx$ są **jednocześnie** zbieżne albo rozbieżne. (Tak dowodzi się kryterium dla $\sum\frac{1}{n^p}$.)

## 2.6. Szeregi naprzemienne — kryterium Leibniza

Szereg naprzemienny $\sum (-1)^n a_n$ (gdzie $a_n>0$) jest **zbieżny**, jeśli:
1. $(a_n)$ jest **malejący**, oraz
2. $a_n \to 0$.

Przykład: $\sum \frac{(-1)^{n+1}}{n} = 1 - \frac12 + \frac13 - \dots$ jest zbieżny (do $\ln 2$), choć szereg z modułów $\sum\frac1n$ jest rozbieżny.

## 2.7. Zbieżność bezwzględna i warunkowa

- **Bezwzględnie zbieżny:** $\sum |a_n|$ jest zbieżny. Wtedy $\sum a_n$ też jest zbieżny.
- **Warunkowo zbieżny:** $\sum a_n$ zbieżny, ale $\sum |a_n|$ rozbieżny (jak przykład wyżej).

Kryteria d'Alemberta i Cauchy'ego badają właśnie zbieżność **bezwzględną** (bo używają modułów). Praktyczny schemat dla szeregu o dowolnych znakach: najpierw sprawdź zbieżność bezwzględną ($\sum|a_n|$); jeśli tak — koniec; jeśli nie, a szereg jest naprzemienny — spróbuj Leibniza (będzie warunkowo zbieżny).

## 2.8. Praktyczny algorytm badania szeregu

1. **Warunek konieczny:** czy $a_n\to 0$? Jeśli nie → rozbieżny, koniec.
2. Rozpoznaj typ: geometryczny / $\frac{1}{n^p}$? → gotowa odpowiedź.
3. Są silnie lub czyste potęgi $a^n$? → **d'Alembert**.
4. Jest $n$-ta potęga całego wyrazu? → **Cauchy**.
5. Iloraz wielomianów / wyrażenie „jak $\frac{1}{n^p}$"? → **kryterium ilorazowe** ze wzorcem.
6. Naprzemienny, a moduły rozbieżne? → **Leibniz**.

---

# 3. Szeregi potęgowe

## 3.1. Intuicja

Szereg potęgowy to „nieskończony wielomian" ze zmienną $x$. Dla jednych $x$ się sumuje (jest zbieżny), dla innych nie. Zbiór $x$, dla których jest zbieżny, to (prawie zawsze) **przedział** wokół środka $x_0$ — stąd pojęcie **promienia zbieżności**.

## 3.2. Definicja

$$\sum_{n=0}^{\infty} a_n (x - x_0)^n = a_0 + a_1(x-x_0) + a_2(x-x_0)^2 + \dots$$
Liczby $a_n$ to **współczynniki**, $x_0$ to **środek**. Najczęściej $x_0=0$: $\sum a_n x^n$.

## 3.3. Promień i przedział zbieżności

Istnieje $R\in[0,\infty]$ — **promień zbieżności** — taki, że szereg jest zbieżny (bezwzględnie) dla $|x-x_0|<R$ i rozbieżny dla $|x-x_0|>R$.

**Wzór Cauchy'ego–Hadamarda:**
$$\frac{1}{R} = \lim_{n\to\infty}\sqrt[n]{|a_n|}\qquad\text{lub (gdy istnieje)}\qquad \frac{1}{R} = \lim_{n\to\infty}\left|\frac{a_{n+1}}{a_n}\right|.$$

**Przedział zbieżności** to $(x_0 - R,\ x_0 + R)$, ale **końce trzeba zbadać osobno** — podstawiamy $x = x_0\pm R$ i badamy powstały szereg liczbowy (może być zbieżny w żadnym, jednym lub obu końcach).

Przykłady wartości $R$:
- $\sum x^n$: $R=1$, przedział $(-1,1)$.
- $\sum \frac{x^n}{n!}$: $R=\infty$ (zbieżny dla każdego $x$) — to $e^x$.
- $\sum n!\,x^n$: $R=0$ (tylko $x=0$).

## 3.4. Własności — różniczkowanie i całkowanie „wyraz po wyrazie"

Wewnątrz przedziału zbieżności szereg potęgowy można różniczkować i całkować wyraz po wyrazie, a **promień zbieżności się nie zmienia**:
$$\left(\sum a_n x^n\right)' = \sum n\,a_n x^{n-1},\qquad \int\sum a_n x^n\,dx = \sum \frac{a_n}{n+1}x^{n+1} + C.$$

## 3.5. Szeregi Taylora / Maclaurina (powtórka + zastosowanie)

Funkcję gładką rozwijamy w szereg potęgowy: $f(x)=\sum_{n=0}^\infty \frac{f^{(n)}(x_0)}{n!}(x-x_0)^n$. Kluczowe rozwinięcia Maclaurina (dla $x_0=0$):

$$e^x = \sum_{n=0}^\infty \frac{x^n}{n!},\qquad \sin x = \sum_{n=0}^\infty \frac{(-1)^n x^{2n+1}}{(2n+1)!},\qquad \cos x = \sum_{n=0}^\infty \frac{(-1)^n x^{2n}}{(2n)!},$$

$$\frac{1}{1-x}=\sum_{n=0}^\infty x^n\ (|x|<1),\qquad \ln(1+x)=\sum_{n=1}^\infty \frac{(-1)^{n+1}}{n}x^n\ (-1<x\le 1).$$

Zastosowanie: przybliżanie funkcji, obliczanie sum szeregów, rozwiązywanie równań różniczkowych.

---

# 4. Granica i ciągłość funkcji wielu zmiennych

## 4.1. Intuicja

Przechodzimy z $\mathbb{R}$ (prosta) do $\mathbb{R}^n$ (przestrzeń). Funkcja $f:\mathbb{R}^2\to\mathbb{R}$ to „powierzchnia" nad płaszczyzną — każdemu punktowi $(x,y)$ przypisuje wysokość $z=f(x,y)$. Największa nowość: do punktu na płaszczyźnie można dojść **na nieskończenie wiele sposobów** (nie tylko z lewej i prawej), i to komplikuje pojęcie granicy.

## 4.2. Norma i iloczyn skalarny w $\mathbb{R}^n$

Dla wektorów $\mathbf{x}=(x_1,\dots,x_n)$, $\mathbf{y}=(y_1,\dots,y_n)$:

**Iloczyn skalarny:** $\ \mathbf{x}\cdot\mathbf{y} = \sum_{i=1}^n x_i y_i.$

**Norma euklidesowa:** $\ \|\mathbf{x}\| = \sqrt{\mathbf{x}\cdot\mathbf{x}} = \sqrt{x_1^2+\dots+x_n^2}.$

Inne normy: $\|\mathbf{x}\|_1 = \sum|x_i|$ (miejska/taksówkowa), $\|\mathbf{x}\|_\infty = \max_i |x_i|$ (maksimum).

**Nierówność Cauchy'ego–Schwarza:** $|\mathbf{x}\cdot\mathbf{y}| \le \|\mathbf{x}\|\,\|\mathbf{y}\|$. Stąd kąt: $\cos\theta = \frac{\mathbf{x}\cdot\mathbf{y}}{\|\mathbf{x}\|\|\mathbf{y}\|}$. Wektory prostopadłe $\iff \mathbf{x}\cdot\mathbf{y}=0$.

**Odległość:** $d(\mathbf{x},\mathbf{y}) = \|\mathbf{x}-\mathbf{y}\|$.

## 4.3. Granica funkcji wielu zmiennych

$$\lim_{(x,y)\to(x_0,y_0)} f(x,y) = g$$
oznacza (Cauchy): $\forall\varepsilon>0\ \exists\delta>0$: jeśli $0<\|(x,y)-(x_0,y_0)\|<\delta$, to $|f(x,y)-g|<\varepsilon$. Czyli: gdy punkt jest **dostatecznie blisko** $(x_0,y_0)$ (w dowolnym kierunku!), wartość jest bliska $g$.

## 4.4. Jak pokazać, że granica NIE istnieje (kluczowa technika)

Skoro granica musi być ta sama **niezależnie od drogi dojścia**, to:
> jeśli po dwóch różnych drogach dostaniemy różne wartości — granica nie istnieje.

Typowe drogi: po osiach ($y=0$, potem $x=0$), po prostych $y=kx$ (wynik zależny od $k$ = brak granicy), po parabolach $y=kx^2$.

**Klasyczny przykład:** $f(x,y)=\frac{xy}{x^2+y^2}$ w $(0,0)$.
- Po $y=0$: $f=0 \to 0$.
- Po $y=x$: $f=\frac{x^2}{2x^2}=\frac12 \to \frac12$.
Różne wartości → **granica nie istnieje**.

## 4.5. Współrzędne biegunowe do liczenia granic

Aby **potwierdzić** istnienie granicy w $(0,0)$, podstaw $x=r\cos\varphi$, $y=r\sin\varphi$ i zbadaj $r\to 0^+$. Jeśli wynik **nie zależy od $\varphi$** i dąży do $g$ (można to oszacować niezależnie od kąta), granica istnieje.

Przykład: $\frac{x^3}{x^2+y^2} = \frac{r^3\cos^3\varphi}{r^2} = r\cos^3\varphi$. Mamy $|r\cos^3\varphi|\le r\to 0$ niezależnie od $\varphi$, więc granica $=0$.

## 4.6. Ciągłość

$f$ jest **ciągła** w $(x_0,y_0)$, gdy $\lim_{(x,y)\to(x_0,y_0)} f(x,y) = f(x_0,y_0)$. Funkcje elementarne (wielomiany, wymierne, złożenia z $\exp,\ln,\sin,\dots$) są ciągłe w swojej dziedzinie. Analogia twierdzenia Weierstrassa: funkcja ciągła na zbiorze **domkniętym i ograniczonym** (zwartym) osiąga swoje kresy.

---

# 5. Pochodne cząstkowe i kierunkowe

## 5.1. Intuicja

Skoro funkcja $f(x,y)$ zależy od dwóch zmiennych, to „ma nachylenie" w każdym kierunku. **Pochodna cząstkowa** to nachylenie wzdłuż jednej osi — traktujemy pozostałe zmienne jak stałe. **Pochodna kierunkowa** to nachylenie w dowolnie wybranym kierunku.

## 5.2. Pochodne cząstkowe

Pochodna cząstkowa po $x$ (przy ustalonym $y$):
$$\frac{\partial f}{\partial x}(x_0,y_0) = f_x(x_0,y_0) = \lim_{h\to 0}\frac{f(x_0+h,\,y_0) - f(x_0,y_0)}{h}.$$
Analogicznie $\frac{\partial f}{\partial y} = f_y$.

**W praktyce:** różniczkujesz normalnie względem jednej zmiennej, a pozostałe traktujesz jak liczby (stałe).

Przykład: $f(x,y) = x^2 y + \sin(xy)$.
$$f_x = 2xy + y\cos(xy),\qquad f_y = x^2 + x\cos(xy).$$
(W $f_x$: $y$ to stała, więc pochodna $\sin(xy)$ z reguły łańcuchowej to $\cos(xy)\cdot y$.)

## 5.3. Pochodne cząstkowe wyższych rzędów

$$f_{xx} = \frac{\partial^2 f}{\partial x^2},\quad f_{yy}=\frac{\partial^2 f}{\partial y^2},\quad f_{xy}=\frac{\partial^2 f}{\partial y\,\partial x}\ (\text{najpierw }x\text{, potem }y).$$

**Twierdzenie Schwarza (o pochodnych mieszanych).** Jeśli pochodne mieszane $f_{xy}$ i $f_{yx}$ są ciągłe, to są równe:
$$f_{xy} = f_{yx}.$$
Czyli kolejność różniczkowania nie ma znaczenia (przy ciągłości). To upraszcza rachunki i jest bazą macierzy Hessego.

## 5.4. Pochodna kierunkowa

Pochodna w kierunku wektora **jednostkowego** $\mathbf{v}=(v_1,v_2)$, $\|\mathbf{v}\|=1$:
$$D_{\mathbf{v}} f(x_0,y_0) = \lim_{t\to 0}\frac{f\big((x_0,y_0) + t\mathbf{v}\big) - f(x_0,y_0)}{t}.$$
Pochodne cząstkowe to szczególne przypadki: $f_x = D_{(1,0)}f$, $f_y = D_{(0,1)}f$.

**Wzór roboczy (przy różniczkowalności — patrz rozdz. 6):**
$$D_{\mathbf{v}} f = \nabla f \cdot \mathbf{v} = f_x v_1 + f_y v_2.$$
> **Uwaga:** wektor kierunku musi być **znormalizowany** (długość 1). Jeśli dostajesz kierunek jak $(3,4)$, najpierw podziel przez $\|(3,4)\|=5$: $\mathbf{v}=(\tfrac35,\tfrac45)$.

> **Wyjątek/pułapka:** istnienie wszystkich pochodnych cząstkowych (a nawet kierunkowych) **nie gwarantuje** różniczkowalności ani nawet ciągłości funkcji! Klasyczny przykład $\frac{xy}{x^2+y^2}$ (dodefiniowany $0$ w zerze) ma obie pochodne cząstkowe w $(0,0)$, a nie jest tam ciągły.

---

# 6. Gradient i różniczka

## 6.1. Gradient

**Gradient** to wektor zbudowany z pochodnych cząstkowych:
$$\nabla f = \operatorname{grad} f = \left(\frac{\partial f}{\partial x},\ \frac{\partial f}{\partial y}\right)\quad\left(\text{w }\mathbb{R}^n:\ \left(\tfrac{\partial f}{\partial x_1},\dots,\tfrac{\partial f}{\partial x_n}\right)\right).$$

**Trzy kluczowe własności gradientu:**
1. Wskazuje **kierunek najszybszego wzrostu** funkcji.
2. Jego **długość** $\|\nabla f\|$ to tempo tego najszybszego wzrostu (to maksymalna wartość pochodnej kierunkowej).
3. Jest **prostopadły** do poziomic (linii/powierzchni stałej wartości $f$).

## 6.2. Różniczkowalność i różniczka zupełna

$f$ jest **różniczkowalna** w $(x_0,y_0)$, jeśli przyrost daje się przybliżyć liniowo:
$$f(x_0+h,\,y_0+k) - f(x_0,y_0) = f_x\,h + f_y\,k + o\big(\sqrt{h^2+k^2}\big),$$
gdzie reszta $o(\cdot)$ dąży do zera szybciej niż odległość. **Różniczka zupełna:**
$$df = \frac{\partial f}{\partial x}\,dx + \frac{\partial f}{\partial y}\,dy.$$

**Hierarchia (ważna do zapamiętania):**
$$\text{ciągłość pochodnych cząstkowych} \Rightarrow \text{różniczkowalność} \Rightarrow \text{ciągłość} \;\text{oraz}\; \text{istnienie pochodnych cząstkowych}.$$
Żadna z tych implikacji nie działa „w drugą stronę".

## 6.3. Płaszczyzna styczna i przybliżenie liniowe

Płaszczyzna styczna do wykresu $z=f(x,y)$ w punkcie $(x_0,y_0)$:
$$z = f(x_0,y_0) + f_x(x_0,y_0)(x-x_0) + f_y(x_0,y_0)(y-y_0).$$
To wielowymiarowy odpowiednik stycznej — używany do przybliżeń: $f(x,y)\approx f(x_0,y_0) + f_x\,\Delta x + f_y\,\Delta y$.

## 6.4. Reguła łańcuchowa (dla funkcji wielu zmiennych)

Jeśli $z=f(x,y)$, a $x=x(t)$, $y=y(t)$:
$$\frac{dz}{dt} = \frac{\partial f}{\partial x}\frac{dx}{dt} + \frac{\partial f}{\partial y}\frac{dy}{dt}.$$
Jeśli $x=x(u,v)$, $y=y(u,v)$:
$$\frac{\partial z}{\partial u} = \frac{\partial f}{\partial x}\frac{\partial x}{\partial u} + \frac{\partial f}{\partial y}\frac{\partial y}{\partial u},\qquad \text{analogicznie dla } \frac{\partial z}{\partial v}.$$

## 6.5. Pochodna kierunkowa raz jeszcze

Dla funkcji różniczkowalnej: $D_{\mathbf{v}}f = \nabla f\cdot\mathbf{v}$ (dla $\|\mathbf v\|=1$). Ponieważ $\nabla f\cdot\mathbf v = \|\nabla f\|\cos\theta$, pochodna kierunkowa jest:
- **największa** (= $\|\nabla f\|$), gdy $\mathbf v$ zgodny z gradientem ($\theta=0$),
- **zero**, gdy $\mathbf v$ prostopadły do gradientu (wzdłuż poziomicy),
- **najmniejsza** ($=-\|\nabla f\|$), gdy $\mathbf v$ przeciwny do gradientu.

---

# 7. Różniczki wyższych rzędów i wzór Taylora

## 7.1. Druga różniczka i macierz Hessego

Druga różniczka funkcji dwóch zmiennych:
$$d^2 f = f_{xx}\,dx^2 + 2 f_{xy}\,dx\,dy + f_{yy}\,dy^2.$$
Zbiera się to w **macierz Hessego** (hesjan):
$$H_f = \begin{pmatrix} f_{xx} & f_{xy} \\ f_{yx} & f_{yy} \end{pmatrix}.$$
Przy ciągłości pochodnych mieszanych (Schwarz) hesjan jest **symetryczny** ($f_{xy}=f_{yx}$). Hesjan gra rolę „drugiej pochodnej" i decyduje o rodzaju ekstremum (rozdz. 8).

## 7.2. Wzór Taylora dla funkcji wielu zmiennych

Rozwinięcie wokół $\mathbf{a}=(x_0,y_0)$ do drugiego rzędu:
$$f(\mathbf{a}+\mathbf{h}) = f(\mathbf{a}) + \underbrace{\nabla f(\mathbf{a})\cdot\mathbf{h}}_{df} + \underbrace{\tfrac12\,\mathbf{h}^{\!\top} H_f(\mathbf{a})\,\mathbf{h}}_{\frac12 d^2 f} + o(\|\mathbf{h}\|^2),$$
gdzie $\mathbf{h}=(h,k)$. Rozpisane:
$$f(x_0+h,y_0+k) = f + f_x h + f_y k + \tfrac12\big(f_{xx}h^2 + 2f_{xy}hk + f_{yy}k^2\big) + \dots$$
Zastosowanie: przybliżenia lokalne i uzasadnienie testu drugiej różniczki dla ekstremów.

---

# 8. Ekstrema funkcji wielu zmiennych

## 8.1. Warunek konieczny (punkty stacjonarne)

Jeśli $f$ ma ekstremum lokalne w punkcie wewnętrznym i jest tam różniczkowalna, to
$$\nabla f = \mathbf{0},\quad\text{czyli}\quad f_x = 0\ \text{ oraz }\ f_y = 0.$$
Punkty spełniające ten układ to **punkty stacjonarne (krytyczne)** — tylko **kandydaci** na ekstrema.

## 8.2. Warunek wystarczający — test macierzy Hessego (2 zmienne)

W punkcie stacjonarnym liczymy wyznacznik hesjanu:
$$D = \det H_f = f_{xx}f_{yy} - (f_{xy})^2.$$
- $D>0$ **i** $f_{xx}>0$ → **minimum lokalne**,
- $D>0$ **i** $f_{xx}<0$ → **maksimum lokalne**,
- $D<0$ → **punkt siodłowy** (brak ekstremum — w jednym kierunku rośnie, w drugim maleje),
- $D=0$ → **test nie rozstrzyga** (trzeba badać inaczej, np. wprost lub wyższymi pochodnymi).

**Przykład.** $f(x,y)=x^2+y^2$: $\nabla f=(2x,2y)=0 \Rightarrow (0,0)$. Hesjan $\begin{pmatrix}2&0\\0&2\end{pmatrix}$, $D=4>0$, $f_{xx}=2>0$ → **minimum** (wartość $0$).
Kontrast: $f(x,y)=x^2-y^2$ ma w $(0,0)$ $D=-4<0$ → **siodło**.

## 8.3. Uogólnienie na $n$ zmiennych (kryterium Sylvestera)

W punkcie stacjonarnym patrzymy na minory główne hesjanu $\Delta_1,\Delta_2,\dots,\Delta_n$:
- wszystkie $\Delta_k>0$ → minimum,
- znaki naprzemienne $\Delta_1<0,\Delta_2>0,\Delta_3<0,\dots$ → maksimum,
- inne (niezerowe) układy znaków → siodło.

## 8.4. Ekstrema warunkowe — metoda mnożników Lagrange'a

Szukamy ekstremum $f(x,y)$ **przy warunku** $g(x,y)=0$ (np. na okręgu, prostej). Tworzymy funkcję Lagrange'a:
$$L(x,y,\lambda) = f(x,y) - \lambda\, g(x,y),$$
i rozwiązujemy układ:
$$L_x = 0,\qquad L_y = 0,\qquad g(x,y)=0.$$
Intuicja geometryczna: w punkcie ekstremum warunkowego gradient $f$ jest **równoległy** do gradientu $g$, czyli $\nabla f = \lambda\nabla g$ — poziomica $f$ jest styczna do krzywej warunku.

## 8.5. Ekstrema globalne na zbiorze domkniętym i ograniczonym

Aby znaleźć wartość najmniejszą/największą na zwartym zbiorze $D$:
1. Znajdź punkty stacjonarne **wewnątrz** $D$.
2. Zbadaj funkcję na **brzegu** $D$ (często parametryzacja brzegu lub Lagrange).
3. Porównaj wartości $f$ we wszystkich kandydatach — największa/najmniejsza wygrywa.

Twierdzenie Weierstrassa gwarantuje, że na zbiorze zwartym minimum i maksimum globalne **istnieją**.

---

# 9. Całka Riemanna funkcji wielu zmiennych

## 9.1. Intuicja

Całka podwójna $\iint_D f(x,y)\,dA$ to „objętość pod powierzchnią" $z=f(x,y)$ nad obszarem $D$ (ze znakiem). Konstrukcja jest analogiczna do jednowymiarowej: dzielimy obszar na kawałki, mnożymy wartość przez pole kawałka, sumujemy i przechodzimy do granicy.

## 9.2. Definicja przez sumy Riemanna (na prostokącie)

Dzielimy prostokąt $R=[a,b]\times[c,d]$ na małe prostokąty o polach $\Delta A_{ij}$, wybieramy punkt $(\xi_{ij},\eta_{ij})$ w każdym i tworzymy sumę:
$$S = \sum_{i,j} f(\xi_{ij},\eta_{ij})\,\Delta A_{ij}.$$
Gdy drobność podziału $\to 0$ i suma dąży do wspólnej granicy, funkcja jest **całkowalna**, a granicę oznaczamy $\iint_R f\,dA$.

## 9.3. Własności (jak w 1D)

- **liniowość:** $\iint (\alpha f + \beta g) = \alpha\iint f + \beta\iint g$,
- **addytywność:** $\iint_{D_1\cup D_2} f = \iint_{D_1} f + \iint_{D_2} f$ (gdy $D_1,D_2$ nie nachodzą na siebie),
- **monotoniczność:** $f\le g \Rightarrow \iint f\le\iint g$,
- $\iint_D 1\,dA = \text{pole}(D)$; dla całki potrójnej $\iiint_V 1\,dV = \text{objętość}(V)$.

Funkcja ciągła na obszarze domkniętym i ograniczonym jest całkowalna.

---

# 10. Twierdzenie Fubiniego w obszarze normalnym

## 10.1. Idea

Całkę wielokrotną liczymy jako **całki iterowane** — całkujemy „po jednej zmiennej na raz". Twierdzenie Fubiniego mówi, kiedy to wolno robić i że kolejność (przy odpowiednich założeniach) można zamienić.

## 10.2. Obszary normalne

**Obszar normalny względem osi $OX$ (typ I):**
$$D = \{(x,y): a\le x\le b,\ \varphi_1(x)\le y\le\varphi_2(x)\}.$$
**Obszar normalny względem osi $OY$ (typ II):**
$$D = \{(x,y): c\le y\le d,\ \psi_1(y)\le x\le\psi_2(y)\}.$$
Czyli jeden przedział jest stały, a drugie ograniczenia to funkcje.

## 10.3. Twierdzenie Fubiniego

Dla obszaru normalnego typu I:
$$\iint_D f(x,y)\,dA = \int_a^b\left(\int_{\varphi_1(x)}^{\varphi_2(x)} f(x,y)\,dy\right)dx.$$
Dla typu II:
$$\iint_D f(x,y)\,dA = \int_c^d\left(\int_{\psi_1(y)}^{\psi_2(y)} f(x,y)\,dx\right)dy.$$

**Zasada „od środka na zewnątrz":** całka wewnętrzna ma granice **zależne** od zmiennej zewnętrznej (funkcje), całka zewnętrzna ma granice **stałe** (liczby). Wynik całki wewnętrznej nie może zawierać zmiennej, po której właśnie całkowaliśmy.

> **Pułapka:** zmiana kolejności całkowania wymaga **przerysowania obszaru** i wyznaczenia nowych granic — nie wolno po prostu zamienić $dx\,dy$ z granicami. Rysunek obszaru to podstawa!

## 10.4. Całka potrójna

Analogicznie w $\mathbb{R}^3$ dla obszaru normalnego:
$$\iiint_V f\,dV = \int_a^b\int_{\varphi_1(x)}^{\varphi_2(x)}\int_{\psi_1(x,y)}^{\psi_2(x,y)} f(x,y,z)\,dz\,dy\,dx.$$
Całkujemy „od najgłębszej" ($z$) na zewnątrz.

---

# 11. Twierdzenie o zmianie zmiennych w całce

## 11.1. Idea i jakobian

Czasem obszar (koło, pierścień, kula) jest trudny w prostokątnych współrzędnych, ale prosty w innych (biegunowe, sferyczne). Zmieniamy zmienne — ale przy tym „element pola/objętości" się skaluje. Współczynnik skalowania to **jakobian** — wyznacznik macierzy pochodnych cząstkowych przekształcenia.

Dla przekształcenia $x=x(u,v)$, $y=y(u,v)$:
$$J = \frac{\partial(x,y)}{\partial(u,v)} = \det\begin{pmatrix} \dfrac{\partial x}{\partial u} & \dfrac{\partial x}{\partial v} \\[2mm] \dfrac{\partial y}{\partial u} & \dfrac{\partial y}{\partial v} \end{pmatrix}.$$

**Wzór na zmianę zmiennych:**
$$\iint_D f(x,y)\,dx\,dy = \iint_{D'} f\big(x(u,v),y(u,v)\big)\,|J|\,du\,dv.$$
Uwaga: bierzemy **wartość bezwzględną** jakobianu, a obszar $D$ przechodzi na nowy obszar $D'$ w nowych zmiennych.

## 11.2. Współrzędne biegunowe (płaszczyzna)

$$x = r\cos\varphi,\quad y = r\sin\varphi,\qquad |J| = r.$$
$$\iint_D f\,dx\,dy = \iint_{D'} f(r\cos\varphi, r\sin\varphi)\, r\,dr\,d\varphi.$$
> **Nie zapomnij o „$r$"!** To najczęstszy błąd. Idealne do kół, pierścieni, wycinków ($x^2+y^2\le R^2$).

Przykład: pole koła promienia $R$: $\iint_{x^2+y^2\le R^2} 1\,dA = \int_0^{2\pi}\int_0^R r\,dr\,d\varphi = 2\pi\cdot\frac{R^2}{2} = \pi R^2$.

## 11.3. Współrzędne walcowe (przestrzeń)

$$x=r\cos\varphi,\quad y=r\sin\varphi,\quad z=z,\qquad |J| = r.$$
$$\iiint_V f\,dV = \iiint f\, r\,dr\,d\varphi\,dz.$$
Idealne do walców, stożków (symetria względem osi $z$).

## 11.4. Współrzędne sferyczne (przestrzeń)

$$x=\rho\sin\theta\cos\varphi,\quad y=\rho\sin\theta\sin\varphi,\quad z=\rho\cos\theta,\qquad |J| = \rho^2\sin\theta,$$
gdzie $\rho\ge 0$ — odległość od początku, $\theta\in[0,\pi]$ — kąt od osi $z$ (biegunowy), $\varphi\in[0,2\pi)$ — kąt azymutalny.
$$\iiint_V f\,dV = \iiint f\,\rho^2\sin\theta\,d\rho\,d\theta\,d\varphi.$$
> **Element objętości $\rho^2\sin\theta$** — zapamiętaj na pamięć. Idealne do kul i obszarów o symetrii sferycznej.

Przykład: objętość kuli promienia $R$: $\int_0^{2\pi}\int_0^\pi\int_0^R \rho^2\sin\theta\,d\rho\,d\theta\,d\varphi = 2\pi\cdot 2\cdot\frac{R^3}{3} = \frac{4}{3}\pi R^3$.

---

# 12. Zastosowania całek funkcji wielu zmiennych

## 12.1. Pole obszaru płaskiego

$$\text{Pole}(D) = \iint_D 1\,dA.$$

## 12.2. Objętość bryły

$$\text{Objętość}(V) = \iiint_V 1\,dV,$$
albo jako całka podwójna „pola pod powierzchnią": objętość między $z=f(x,y)\ge 0$ a płaszczyzną $z=0$ nad $D$ to $\iint_D f\,dA$. Objętość między dwiema powierzchniami $g\le z\le f$: $\iint_D (f-g)\,dA$.

## 12.3. Masa i środek masy

Dla płytki o gęstości powierzchniowej $\rho(x,y)$:
$$m = \iint_D \rho\,dA,\qquad x_c = \frac{1}{m}\iint_D x\,\rho\,dA,\qquad y_c = \frac{1}{m}\iint_D y\,\rho\,dA.$$
Dla jednorodnej płytki ($\rho=\text{const}$) środek masy = **środek geometryczny (centroid)**. Analogicznie w 3D z $\rho(x,y,z)$ i $dV$.

## 12.4. Momenty bezwładności

Względem osi (np. osi $z$ dla płytki w płaszczyźnie):
$$I_z = \iint_D (x^2+y^2)\,\rho\,dA,\qquad I_x = \iint_D y^2\rho\,dA,\qquad I_y = \iint_D x^2\rho\,dA.$$

## 12.5. Wartość średnia funkcji

$$\bar f = \frac{1}{\text{pole}(D)}\iint_D f\,dA.$$

## 12.6. Schemat rozwiązywania zadania z całki wielokrotnej

1. **Narysuj obszar** całkowania — to podstawa.
2. Wybierz układ współrzędnych (prostokątne / biegunowe / sferyczne / walcowe) dopasowany do kształtu obszaru i funkcji.
3. Wyznacz granice całkowania (dla obszaru normalnego — funkcje wewnątrz, stałe na zewnątrz).
4. Nie zapomnij o **jakobianie** ($r$, $r$, $\rho^2\sin\theta$).
5. Całkuj „od środka na zewnątrz", pilnując, by wynik całki wewnętrznej nie zawierał już zmiennej, po której całkowałeś.

---

# Dodatek A — Tabela kryteriów zbieżności szeregów

| Kryterium | Kiedy stosować | Warunek zbieżności |
|---|---|---|
| Warunek konieczny | zawsze najpierw | $a_n\not\to 0$ ⟹ **rozbieżny** |
| Geometryczne | $\sum q^n$ | $|q|<1$ |
| Dirichleta ($p$-szereg) | $\sum \frac{1}{n^p}$ | $p>1$ |
| Porównawcze / ilorazowe | iloraz wielomianów, „jak $\frac1{n^p}$" | jak wzorzec |
| d'Alemberta | silnie $n!$, potęgi $a^n$ | $\lim\left|\frac{a_{n+1}}{a_n}\right|<1$ |
| Cauchy'ego (pierwiastkowe) | $n$-te potęgi $(\cdots)^n$ | $\lim\sqrt[n]{|a_n|}<1$ |
| Całkowe | $a_n=f(n)$, $f$ malejąca dodatnia | $\int_1^\infty f$ zbieżna |
| Leibniza | naprzemienne $\sum(-1)^n a_n$ | $a_n\downarrow 0$ |

---

# Dodatek B — Jakobiany najczęstszych zamian zmiennych

| Współrzędne | Podstawienie | $|J|$ |
|---|---|---|
| Biegunowe (2D) | $x=r\cos\varphi,\ y=r\sin\varphi$ | $r$ |
| Walcowe (3D) | $x=r\cos\varphi,\ y=r\sin\varphi,\ z=z$ | $r$ |
| Sferyczne (3D) | $x=\rho\sin\theta\cos\varphi,\ y=\rho\sin\theta\sin\varphi,\ z=\rho\cos\theta$ | $\rho^2\sin\theta$ |

Elementy do zapamiętania: $dA = r\,dr\,d\varphi$, $dV = r\,dr\,d\varphi\,dz$ (walcowe), $dV = \rho^2\sin\theta\,d\rho\,d\theta\,d\varphi$ (sferyczne).

---

# Dodatek C — Najczęstsze błędy egzaminacyjne

- **Całki niewłaściwe:** przeoczenie osobliwości wewnątrz przedziału; mylenie warunku $\frac1{x^p}$ „na $\infty$" ($p>1$) z warunkiem „przy $0$" ($p<1$).
- **Szeregi:** uznanie $a_n\to 0$ za dowód zbieżności (to tylko warunek konieczny!); zapomnienie o zbadaniu **końców** przedziału zbieżności szeregu potęgowego.
- **Granice 2D:** „udowodnienie" istnienia granicy tylko po dwóch drogach (to co najwyżej wskazuje kandydata; do dowodu trzeba oszacowania niezależnego od kierunku, np. biegunowo).
- **Pochodne kierunkowe:** nieznormalizowanie wektora kierunku (musi mieć długość 1).
- **Ekstrema:** pominięcie testu $D<0$ (siodło); uznanie punktu stacjonarnego za ekstremum bez sprawdzenia hesjanu; przy ekstremach globalnych — pominięcie brzegu obszaru.
- **Całki wielokrotne:** brak jakobianu (najczęściej „$r$"); zła kolejność/granice po zamianie kolejności całkowania bez przerysowania obszaru; pozostawienie zmiennej wewnętrznej w wyniku całki zewnętrznej.

---

*Powodzenia na egzaminie! Złota zasada Analizy 2: prawie każde zadanie z całek wielokrotnych zaczyna się od porządnego rysunku obszaru, a prawie każde z ekstremów — od rozwiązania układu $\nabla f = 0$.*
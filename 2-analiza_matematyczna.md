# Analiza Matematyczna 1 — Kompletne notatki egzaminacyjne


## Jak korzystać z tych notatek

Każdy rozdział ma stały układ:
- **Intuicja** — co się tak naprawdę dzieje, „po ludzku".
- **Definicje** — precyzyjnie, tak jak na egzaminie ustnym.
- **Twierdzenia** — z założeniami (założenia są równie ważne jak teza!).
- **Jak liczyć** — przepis krok po kroku + typowe zadania.
- **Pułapki i wyjątki** — miejsca, gdzie studenci tracą punkty.

Symbole: $\forall$ — dla każdego, $\exists$ — istnieje, $\Rightarrow$ — implikuje, $\iff$ — wtedy i tylko wtedy, $\mathbb{N},\mathbb{Z},\mathbb{Q},\mathbb{R}$ — zbiory liczb.

---

# 1. Ciągi liczbowe

## 1.1. Intuicja

Ciąg to **nieskończona, uporządkowana lista liczb**: $a_1, a_2, a_3, \dots$. Interesuje nas przede wszystkim jedno pytanie: **do czego te liczby zmierzają, gdy idziemy coraz dalej?** To „coś", do czego się zbliżają, nazywamy **granicą**.

## 1.2. Definicja ciągu

**Ciąg liczbowy** to funkcja $a:\mathbb{N}\to\mathbb{R}$. Wartość $a(n)$ zapisujemy $a_n$ i nazywamy $n$-tym **wyrazem** ciągu. Cały ciąg oznaczamy $(a_n)_{n=1}^{\infty}$ lub $(a_n)$.

Ciąg można zadać:
- **wzorem ogólnym**: $a_n = \dfrac{n}{n+1}$,
- **rekurencyjnie**: $a_1 = 1,\ a_{n+1} = \sqrt{2 + a_n}$.

## 1.3. Monotoniczność

Ciąg $(a_n)$ jest:
- **rosnący**, gdy $a_{n+1} > a_n$ dla każdego $n$,
- **niemalejący**, gdy $a_{n+1} \ge a_n$,
- **malejący**, gdy $a_{n+1} < a_n$,
- **nierosnący**, gdy $a_{n+1} \le a_n$.

Ciąg **monotoniczny** to ciąg jednego z tych czterech typów.

**Jak badać monotoniczność — dwie metody:**

1. **Metoda różnicy.** Liczymy $a_{n+1}-a_n$ i badamy znak.
   - $a_{n+1}-a_n > 0 \Rightarrow$ rosnący.
   - Przykład: $a_n = n^2 - n$, wtedy $a_{n+1}-a_n = (n+1)^2-(n+1) - (n^2-n) = 2n > 0$ → rosnący.

2. **Metoda ilorazu** (gdy wszystkie wyrazy są dodatnie). Liczymy $\dfrac{a_{n+1}}{a_n}$ i porównujemy z $1$.
   - $\dfrac{a_{n+1}}{a_n} > 1 \Rightarrow$ rosnący.
   - Przykład: $a_n = \dfrac{2^n}{n!}$, wtedy $\dfrac{a_{n+1}}{a_n} = \dfrac{2}{n+1} < 1$ dla $n\ge 2$ → od pewnego miejsca malejący.

> **Pułapka:** ciąg nie musi być monotoniczny! Np. $a_n = (-1)^n$ skacze $-1,1,-1,1,\dots$

## 1.4. Ograniczoność

- **ograniczony z góry**: $\exists M\ \forall n\ a_n \le M$,
- **ograniczony z dołu**: $\exists m\ \forall n\ a_n \ge m$,
- **ograniczony**: ograniczony z góry i z dołu, czyli $\exists M>0\ \forall n\ |a_n|\le M$.

## 1.5. Granica ciągu — definicja $\varepsilon$–$N$ (najważniejsza definicja rozdziału)

Liczba $g$ jest **granicą** ciągu $(a_n)$ (piszemy $\lim_{n\to\infty} a_n = g$), gdy:

$$\forall \varepsilon > 0\ \ \exists N\in\mathbb{N}\ \ \forall n > N:\quad |a_n - g| < \varepsilon.$$

**Czytanie tej definicji:** dla dowolnie małego „pasa tolerancji" $\varepsilon$ wokół $g$, od pewnego miejsca $N$ **wszystkie** dalsze wyrazy ciągu wpadają do tego pasa i już z niego nie wychodzą.

Ciąg mający granicę (skończoną) nazywamy **zbieżnym**. Ciąg, który nie jest zbieżny, jest **rozbieżny**.

**Granice niewłaściwe:**
$$\lim_{n\to\infty} a_n = +\infty \iff \forall M\ \exists N\ \forall n>N:\ a_n > M.$$
Analogicznie dla $-\infty$. Ciąg rozbieżny do $\pm\infty$ jest rozbieżny (nie ma granicy skończonej), ale mówimy, że ma granicę niewłaściwą.

**Dowód z definicji (schemat zadania „pokaż, że $\lim = g$"):**
Chcemy pokazać $\lim \frac{n+1}{n} = 1$. Liczymy $\left|\frac{n+1}{n}-1\right| = \frac{1}{n}$. Chcemy $\frac{1}{n}<\varepsilon$, czyli $n > \frac{1}{\varepsilon}$. Wystarczy wziąć $N = \left\lceil \frac{1}{\varepsilon}\right\rceil$. Dla $n>N$ nierówność zachodzi. ∎

## 1.6. Twierdzenia o granicach (arytmetyka granic)

Jeśli $\lim a_n = a$ oraz $\lim b_n = b$ (obie skończone), to:
- $\lim (a_n \pm b_n) = a \pm b$,
- $\lim (a_n \cdot b_n) = a\cdot b$,
- $\lim \dfrac{a_n}{b_n} = \dfrac{a}{b}$, **o ile** $b\ne 0$,
- $\lim (c\cdot a_n) = c\cdot a$.

> **Kluczowe:** te wzory działają tylko, gdy obie granice istnieją i są skończone. Nie wolno „rozbijać" granicy na sumę, jeśli składniki dążą do $\infty$ i $-\infty$ — to symbol nieoznaczony.

## 1.7. Twierdzenie o trzech ciągach (o dwóch policjantach)

Jeśli od pewnego miejsca $a_n \le b_n \le c_n$ oraz $\lim a_n = \lim c_n = g$, to $\lim b_n = g$.

**Zastosowanie:** świetne do „opakowania" trudnego ciągu.
Przykład: $b_n = \dfrac{\sin n}{n}$. Mamy $-\dfrac{1}{n} \le \dfrac{\sin n}{n} \le \dfrac{1}{n}$, oba brzegi → $0$, więc $\lim b_n = 0$.

## 1.8. Twierdzenie o ciągu monotonicznym i ograniczonym (bardzo ważne)

**Każdy ciąg monotoniczny i ograniczony jest zbieżny.**
- Ciąg niemalejący i ograniczony z góry → zbieżny (do swojego kresu górnego).
- Ciąg nierosnący i ograniczony z dołu → zbieżny (do kresu dolnego).

To twierdzenie jest podstawowym narzędziem do ciągów **rekurencyjnych**: pokazujemy, że ciąg jest monotoniczny i ograniczony ⟹ ma granicę $g$, a potem $g$ znajdujemy, przechodząc do granicy w równaniu rekurencyjnym.

**Przykład (typowe zadanie):** $a_1 = \sqrt{2},\ a_{n+1} = \sqrt{2+a_n}$.
1. Ograniczoność (indukcja): pokazujemy $a_n < 2$ dla każdego $n$.
2. Monotoniczność: $a_{n+1}^2 - a_n^2 = 2 + a_n - a_n^2 = -(a_n-2)(a_n+1) > 0$ dla $0<a_n<2$, więc rosnący.
3. Zbieżny (monotoniczny + ograniczony). Niech $g=\lim a_n$. Przechodzimy do granicy: $g = \sqrt{2+g}$, czyli $g^2 = 2+g$, $g^2-g-2=0$, $g=2$ (odrzucamy $g=-1$).

## 1.9. Liczba $e$

$$e = \lim_{n\to\infty}\left(1 + \frac{1}{n}\right)^n \approx 2{,}71828\ldots$$

Ten ciąg jest rosnący i ograniczony z góry, więc granica istnieje (i tak **definiuje się** $e$). Uogólnienie, bardzo przydatne:
$$\lim_{n\to\infty}\left(1 + \frac{x}{n}\right)^n = e^{x}.$$

## 1.10. Katalog ważnych granic ciągów (do zapamiętania)

$$\lim_{n\to\infty} \frac{1}{n^p} = 0\ (p>0), \qquad \lim_{n\to\infty} q^n = \begin{cases} 0 & |q|<1\\ 1 & q=1\\ +\infty & q>1\\ \text{brak} & q\le -1\end{cases}$$

$$\lim_{n\to\infty} \sqrt[n]{a} = 1\ (a>0), \qquad \lim_{n\to\infty}\sqrt[n]{n} = 1, \qquad \lim_{n\to\infty}\frac{a^n}{n!} = 0, \qquad \lim_{n\to\infty}\frac{n^k}{a^n}=0\ (a>1).$$

**Hierarchia szybkości dążenia do $\infty$** (od najwolniejszego): $\ln n \prec n^p \prec a^n \prec n! \prec n^n$. To pozwala natychmiast rozstrzygać ilorazy — „szybszy" wygrywa.

## 1.11. Symbole nieoznaczone

Wyrażenia, których **nie wolno** obliczać wprost, bo wynik zależy od konkretnych ciągów:
$$\frac{0}{0},\quad \frac{\infty}{\infty},\quad 0\cdot\infty,\quad \infty-\infty,\quad 1^{\infty},\quad 0^0,\quad \infty^0.$$
Symbol nieoznaczony trzeba **przekształcić** (wyłączyć najszybszy wyraz, pomnożyć przez sprzężenie, użyć de l'Hospitala po zamianie na funkcję itp.).

**Metoda „dominującego wyrazu"** dla ilorazu wielomianów/potęg: dzielimy licznik i mianownik przez najwyższą potęgę $n$.
$$\lim \frac{3n^2 - n}{2n^2 + 5} = \lim \frac{3 - \frac{1}{n}}{2 + \frac{5}{n^2}} = \frac{3}{2}.$$

**Sprzężenie** (dla $\infty-\infty$ z pierwiastkami):
$$\lim_{n\to\infty}\left(\sqrt{n^2+n}-n\right) = \lim \frac{(\sqrt{n^2+n}-n)(\sqrt{n^2+n}+n)}{\sqrt{n^2+n}+n} = \lim \frac{n}{\sqrt{n^2+n}+n} = \frac{1}{2}.$$

## 1.12. Podciągi i twierdzenie Bolzano–Weierstrassa

**Podciąg** $(a_{n_k})$ powstaje przez wybranie nieskończenie wielu wyrazów z zachowaniem kolejności ($n_1<n_2<\dots$).

- Jeśli ciąg jest zbieżny do $g$, to **każdy** jego podciąg też jest zbieżny do $g$.
- **Kontra do rozbieżności:** jeśli znajdziemy dwa podciągi o różnych granicach, ciąg jest rozbieżny. (Np. $(-1)^n$: podciąg parzysty → $1$, nieparzysty → $-1$.)

**Twierdzenie Bolzano–Weierstrassa:** z każdego ciągu **ograniczonego** można wybrać podciąg zbieżny.

## 1.13. Warunek Cauchy'ego

Ciąg $(a_n)$ jest **ciągiem Cauchy'ego**, gdy
$$\forall \varepsilon>0\ \exists N\ \forall m,n>N:\ |a_n - a_m| < \varepsilon.$$
W $\mathbb{R}$: **ciąg jest zbieżny wtedy i tylko wtedy, gdy jest ciągiem Cauchy'ego** (zupełność $\mathbb{R}$). Zaleta: pozwala orzec zbieżność bez znajomości granicy.

---

# 2. Granica i ciągłość funkcji

## 2.1. Intuicja

Granica funkcji w punkcie $x_0$ odpowiada na pytanie: **do jakiej wartości zbliżają się wartości $f(x)$, gdy $x$ zbliża się do $x_0$** (ale go nie osiąga). Uwaga: to, co dzieje się *dokładnie* w $x_0$, jest tu bez znaczenia — funkcja może tam być nieokreślona.

## 2.2. Granica funkcji — dwie równoważne definicje

**Definicja Heinego (ciągowa).** $\lim_{x\to x_0} f(x) = g$ wtedy i tylko wtedy, gdy dla **każdego** ciągu $(x_n)$ takiego, że $x_n \to x_0$ i $x_n \ne x_0$, zachodzi $f(x_n) \to g$.

**Definicja Cauchy'ego ($\varepsilon$–$\delta$).**
$$\lim_{x\to x_0} f(x) = g \iff \forall \varepsilon>0\ \exists \delta>0\ \forall x:\ 0<|x-x_0|<\delta \Rightarrow |f(x)-g|<\varepsilon.$$

**Definicja Heinego jest najwygodniejsza do dowodzenia, że granicy NIE MA**: wystarczy wskazać dwa ciągi $x_n \to x_0$, dla których $f(x_n)$ dążą do różnych wartości.
Przykład: $f(x)=\sin\frac{1}{x}$ w $x_0=0$ nie ma granicy — bierzemy $x_n = \frac{1}{n\pi}\to 0$ (wartości $0$) oraz $x_n=\frac{1}{\pi/2 + 2n\pi}\to 0$ (wartości $1$).

## 2.3. Granice jednostronne

- **lewostronna:** $\lim_{x\to x_0^-} f(x)$ — $x$ zbliża się od strony mniejszych wartości.
- **prawostronna:** $\lim_{x\to x_0^+} f(x)$ — od strony większych.

**Kluczowy fakt:** granica (obustronna) istnieje $\iff$ obie granice jednostronne istnieją i są **równe**:
$$\lim_{x\to x_0} f(x) = g \iff \lim_{x\to x_0^-}f(x) = \lim_{x\to x_0^+}f(x) = g.$$

Przykład rozbieżności jednostronnej: $f(x)=\frac{1}{x}$ w $0$: $\lim_{x\to 0^-} = -\infty$, $\lim_{x\to 0^+}=+\infty$.

## 2.4. Granice w nieskończoności i granice niewłaściwe

- $\lim_{x\to +\infty} f(x) = g$: dla dużych $x$ wartości bliskie $g$.
- $\lim_{x\to x_0} f(x) = +\infty$: wartości rosną nieograniczenie (asymptota pionowa).

Arytmetyka granic funkcji jest **taka sama** jak dla ciągów (suma, iloczyn, iloraz przy niezerowym mianowniku). Te same symbole nieoznaczone.

## 2.5. Katalog granic specjalnych (must-know)

$$\boxed{\lim_{x\to 0}\frac{\sin x}{x} = 1}\qquad \boxed{\lim_{x\to 0}\frac{1-\cos x}{x^2} = \frac{1}{2}}\qquad \boxed{\lim_{x\to 0}\frac{\tan x}{x} = 1}$$

$$\lim_{x\to 0}\frac{e^x - 1}{x} = 1,\qquad \lim_{x\to 0}\frac{\ln(1+x)}{x} = 1,\qquad \lim_{x\to 0}\frac{a^x-1}{x}=\ln a,$$

$$\lim_{x\to 0}\frac{(1+x)^\alpha - 1}{x} = \alpha,\qquad \lim_{x\to \pm\infty}\left(1+\frac{1}{x}\right)^x = e,\qquad \lim_{x\to 0}(1+x)^{1/x} = e.$$

To są „cegiełki" — wiele granic sprowadza się do nich przez podstawienie i przekształcenia. Np.
$$\lim_{x\to 0}\frac{\sin 5x}{3x} = \lim_{x\to 0}\frac{\sin 5x}{5x}\cdot\frac{5}{3} = 1\cdot\frac{5}{3} = \frac{5}{3}.$$

## 2.6. Ciągłość funkcji

Funkcja $f$ jest **ciągła w punkcie** $x_0$ (należącym do dziedziny), gdy:
$$\lim_{x\to x_0} f(x) = f(x_0).$$
Rozbite na warunki: (1) $f(x_0)$ jest określone, (2) granica istnieje, (3) są sobie równe.

Funkcja jest **ciągła na zbiorze**, gdy jest ciągła w każdym jego punkcie. Intuicyjnie: wykres „da się narysować bez odrywania ołówka".

**Funkcje elementarne** (wielomiany, wymierne, wykładnicze, logarytmiczne, trygonometryczne, potęgowe, ich złożenia i kombinacje) są **ciągłe w całej swojej dziedzinie**. To pozwala większość granic liczyć przez zwykłe podstawienie — o ile punkt należy do dziedziny.

## 2.7. Rodzaje nieciągłości (na egzaminie klasyfikuje się je)

Niech $x_0$ będzie punktem nieciągłości.
- **Nieciągłość I rodzaju usuwalna:** granice jednostronne istnieją, są równe, ale różne od $f(x_0)$ (lub $f(x_0)$ niezdefiniowane). „Dziura" w wykresie. Przykład: $f(x)=\frac{\sin x}{x}$ w $0$ — dodefiniowując $f(0)=1$ usuwamy nieciągłość.
- **Nieciągłość I rodzaju typu skok:** granice jednostronne istnieją, ale są **różne**. Przykład: funkcja signum w $0$.
- **Nieciągłość II rodzaju:** przynajmniej jedna granica jednostronna nie istnieje lub jest niewłaściwa ($\pm\infty$). Przykład: $\frac{1}{x}$ lub $\sin\frac{1}{x}$ w $0$.

## 2.8. Twierdzenia o funkcjach ciągłych na przedziale domkniętym

Niech $f$ będzie ciągła na $[a,b]$.

**Twierdzenie Weierstrassa (o osiąganiu kresów).** $f$ jest ograniczona na $[a,b]$ **oraz** osiąga swoje kresy — istnieją punkty, w których przyjmuje wartość najmniejszą i największą.
> **Uwaga na założenia:** przedział musi być **domknięty i ograniczony**. Na $(0,1)$ funkcja $\frac{1}{x}$ jest ciągła, lecz nieograniczona — brak domkniętości psuje wszystko.

**Twierdzenie Darboux (własność wartości pośredniej).** Jeśli $f$ jest ciągła na $[a,b]$ i $y$ leży między $f(a)$ a $f(b)$, to istnieje $c\in[a,b]$ z $f(c)=y$.
> **Zastosowanie — istnienie pierwiastka:** jeśli $f$ ciągła i $f(a)\cdot f(b) < 0$ (różne znaki na końcach), to równanie $f(x)=0$ ma pierwiastek w $(a,b)$. Klasyczne zadanie: „pokaż, że $x^5 - 3x + 1 = 0$ ma rozwiązanie w $(0,1)$" — sprawdzamy znaki: $f(0)=1>0$, $f(1)=-1<0$. ∎

## 2.9. Ciągłość jednostajna (pojęcie subtelniejsze)

$f$ jest **jednostajnie ciągła** na zbiorze $A$, gdy
$$\forall\varepsilon>0\ \exists\delta>0\ \forall x,x'\in A:\ |x-x'|<\delta \Rightarrow |f(x)-f(x')|<\varepsilon.$$
Różnica względem zwykłej ciągłości: **$\delta$ zależy tylko od $\varepsilon$, nie od punktu**. 

**Twierdzenie Cantora:** funkcja ciągła na przedziale domkniętym i ograniczonym $[a,b]$ jest na nim jednostajnie ciągła. Na przedziałach otwartych/nieograniczonych już niekoniecznie (np. $\frac{1}{x}$ na $(0,1)$, $x^2$ na $\mathbb{R}$).

---

# 3. Pochodna funkcji jednej zmiennej

## 3.1. Intuicja

Pochodna to **chwilowa szybkość zmian** funkcji, czyli **nachylenie stycznej** do wykresu w danym punkcie. Fizycznie: jeśli $f(t)$ to położenie, to $f'(t)$ to prędkość. Geometrycznie: dużo pochodna dodatnia = funkcja rośnie stromo w górę.

## 3.2. Definicja

Pochodna funkcji $f$ w punkcie $x_0$:
$$f'(x_0) = \lim_{h\to 0}\frac{f(x_0 + h) - f(x_0)}{h} = \lim_{x\to x_0}\frac{f(x)-f(x_0)}{x - x_0},$$
o ile ta granica istnieje i jest skończona. Wtedy $f$ jest **różniczkowalna** w $x_0$.

Iloraz $\frac{f(x_0+h)-f(x_0)}{h}$ to **iloraz różnicowy** — nachylenie siecznej. Granica przy $h\to 0$ to nachylenie stycznej.

**Równanie stycznej** w punkcie $(x_0, f(x_0))$:
$$y = f(x_0) + f'(x_0)(x - x_0).$$

## 3.3. Różniczkowalność a ciągłość

**Twierdzenie:** jeśli $f$ jest różniczkowalna w $x_0$, to jest ciągła w $x_0$.
**Odwrotnie NIE zachodzi!** Klasyczny kontrprzykład: $f(x)=|x|$ jest ciągła w $0$, ale nieróżniczkowalna — pochodna lewostronna $=-1$, prawostronna $=+1$, nie są równe (wykres ma „ostry dziób"). Inne przykłady braku pochodnej: punkty załamania, styczna pionowa (np. $\sqrt[3]{x}$ w $0$).

## 3.4. Reguły różniczkowania

Dla $f,g$ różniczkowalnych:
$$(f\pm g)' = f' \pm g' \qquad (c\cdot f)' = c\cdot f'$$
$$(f\cdot g)' = f'g + fg' \quad\text{(reguła iloczynu)}$$
$$\left(\frac{f}{g}\right)' = \frac{f'g - fg'}{g^2}\quad (g\ne 0)\quad\text{(reguła ilorazu)}$$

**Reguła łańcuchowa (pochodna złożenia)** — najważniejsza:
$$\big(f(g(x))\big)' = f'(g(x))\cdot g'(x).$$
Czytanie: „pochodna zewnętrznej (w punkcie wewnętrznej) razy pochodna wewnętrznej".
Przykład: $\big(\sin(x^2)\big)' = \cos(x^2)\cdot 2x$.

**Pochodna funkcji odwrotnej:** jeśli $y=f(x)$ ma odwrotną $x=f^{-1}(y)$, to
$$\big(f^{-1}\big)'(y) = \frac{1}{f'(x)},\quad x=f^{-1}(y).$$

## 3.5. Tabela pochodnych (do zapamiętania w całości)

| $f(x)$ | $f'(x)$ |
|---|---|
| $c$ | $0$ |
| $x^n$ | $n x^{n-1}$ |
| $\sqrt{x}$ | $\dfrac{1}{2\sqrt{x}}$ |
| $\dfrac{1}{x}$ | $-\dfrac{1}{x^2}$ |
| $e^x$ | $e^x$ |
| $a^x$ | $a^x \ln a$ |
| $\ln x$ | $\dfrac{1}{x}$ |
| $\log_a x$ | $\dfrac{1}{x\ln a}$ |
| $\sin x$ | $\cos x$ |
| $\cos x$ | $-\sin x$ |
| $\tan x$ | $\dfrac{1}{\cos^2 x}=\sec^2 x$ |
| $\cot x$ | $-\dfrac{1}{\sin^2 x}$ |
| $\arcsin x$ | $\dfrac{1}{\sqrt{1-x^2}}$ |
| $\arccos x$ | $-\dfrac{1}{\sqrt{1-x^2}}$ |
| $\arctan x$ | $\dfrac{1}{1+x^2}$ |

## 3.6. Pochodna logarytmiczna (trick na $f(x)^{g(x)}$)

Dla wyrażeń typu $x^x$ czy $(\sin x)^{x}$ logarytmujemy przed różniczkowaniem:
$$y = x^x \Rightarrow \ln y = x\ln x \Rightarrow \frac{y'}{y} = \ln x + 1 \Rightarrow y' = x^x(\ln x + 1).$$

## 3.7. Pochodne wyższych rzędów i różniczka

- $f'' = (f')'$, $f''' $, ... , $f^{(n)}$ — pochodne kolejnych rzędów.
- Interpretacja $f''$: przyspieszenie; znak $f''$ mówi o **wypukłości** (rozdz. 7).
- **Różniczka:** $df = f'(x)\,dx$ — przybliżenie przyrostu funkcji: $f(x_0 + \Delta x)\approx f(x_0) + f'(x_0)\Delta x$. Używana do szacowań (np. $\sqrt{4{,}1}\approx 2 + \frac{1}{4}\cdot 0{,}1 = 2{,}025$).

---

# 4. Twierdzenia o wartości średniej

Te twierdzenia to „silnik" całego rachunku różniczkowego — łączą lokalną informację (pochodna) z globalnym zachowaniem funkcji.

## 4.1. Twierdzenie Fermata (warunek konieczny ekstremum)

Jeśli $f$ ma **ekstremum lokalne** w punkcie wewnętrznym $x_0$ i jest tam różniczkowalna, to $f'(x_0)=0$.
> Punkty, w których $f'=0$, nazywamy **stacjonarnymi** (krytycznymi). To tylko **kandydaci** na ekstrema — nie każdy punkt stacjonarny jest ekstremum! Kontrprzykład: $f(x)=x^3$, $f'(0)=0$, ale w $0$ nie ma ekstremum (punkt przegięcia).

## 4.2. Twierdzenie Rolle'a

Założenia: $f$ ciągła na $[a,b]$, różniczkowalna na $(a,b)$, $f(a)=f(b)$.
Teza: $\exists c\in(a,b):\ f'(c)=0$.
Intuicja: jeśli funkcja wraca do tej samej wartości, to gdzieś po drodze „się odwróciła" — styczna była pozioma.

## 4.3. Twierdzenie Lagrange'a (o wartości średniej) — najważniejsze

Założenia: $f$ ciągła na $[a,b]$, różniczkowalna na $(a,b)$.
Teza:
$$\exists c\in(a,b):\quad f'(c) = \frac{f(b)-f(a)}{b - a}.$$
Intuicja: gdzieś nachylenie stycznej równa się średniemu nachyleniu (siecznej) na całym odcinku. Kierowca, który jechał ze średnią 100 km/h, w pewnym momencie miał chwilową prędkość dokładnie 100 km/h.

**Fundamentalny wniosek (monotoniczność z pochodnej):** na przedziale
- $f'(x) > 0 \Rightarrow f$ rosnąca,
- $f'(x) < 0 \Rightarrow f$ malejąca,
- $f'(x) = 0$ na całym przedziale $\Rightarrow f$ stała.

To jest podstawa badania przebiegu zmienności (rozdz. 7).

**Wniosek — dowodzenie nierówności:** wiele nierówności dowodzi się przez wprowadzenie funkcji pomocniczej i zbadanie jej monotoniczności. Przykład: pokaż $e^x \ge 1+x$. Bierzemy $g(x)=e^x - 1 - x$, $g'(x)=e^x-1$, która jest $<0$ dla $x<0$ i $>0$ dla $x>0$, więc minimum w $0$: $g(0)=0$, zatem $g(x)\ge 0$. ∎

## 4.4. Twierdzenie Cauchy'ego (uogólnione)

Założenia: $f,g$ ciągłe na $[a,b]$, różniczkowalne na $(a,b)$, $g'\ne 0$ na $(a,b)$.
Teza:
$$\exists c\in(a,b):\quad \frac{f'(c)}{g'(c)} = \frac{f(b)-f(a)}{g(b)-g(a)}.$$
To uogólnienie Lagrange'a (dla $g(x)=x$ dostajemy Lagrange'a) i baza dowodu reguły de l'Hospitala.

---

# 5. Twierdzenie (reguła) de l'Hospitala

## 5.1. Kiedy stosować

Reguła służy do liczenia granic dających symbole nieoznaczone $\dfrac{0}{0}$ lub $\dfrac{\infty}{\infty}$.

## 5.2. Treść twierdzenia

Jeśli $\lim_{x\to x_0}\dfrac{f(x)}{g(x)}$ jest symbolem $\frac{0}{0}$ lub $\frac{\infty}{\infty}$, funkcje są różniczkowalne w otoczeniu $x_0$ (poza być może $x_0$), $g'\ne 0$, oraz **istnieje** granica $\lim_{x\to x_0}\dfrac{f'(x)}{g'(x)}$, to:
$$\lim_{x\to x_0}\frac{f(x)}{g(x)} = \lim_{x\to x_0}\frac{f'(x)}{g'(x)}.$$
Działa też dla $x_0=\pm\infty$ i dla granic jednostronnych.

**Przykład:** $\displaystyle\lim_{x\to 0}\frac{e^x - 1 - x}{x^2} \overset{H}{=} \lim_{x\to 0}\frac{e^x - 1}{2x} \overset{H}{=} \lim_{x\to 0}\frac{e^x}{2} = \frac{1}{2}.$ (Zastosowano dwukrotnie — po pierwszym różniczkowaniu wciąż $\frac{0}{0}$.)

## 5.3. Sprowadzanie pozostałych symboli do $\frac{0}{0}$ lub $\frac{\infty}{\infty}$

- **$0\cdot\infty$:** zapisz $f\cdot g = \dfrac{f}{1/g}$. Przykład: $\lim_{x\to 0^+} x\ln x = \lim \dfrac{\ln x}{1/x} = \dfrac{-\infty}{\infty}\overset{H}{=}\lim\dfrac{1/x}{-1/x^2}=\lim(-x)=0.$
- **$\infty-\infty$:** sprowadź do wspólnego mianownika lub użyj sprzężenia.
- **$1^\infty,\ 0^0,\ \infty^0$:** zlogarytmuj. Dla $y = f^g$ liczymy $\ln y = g\ln f$ (to daje $0\cdot\infty$), znajdujemy $\lim \ln y = L$, a wynik to $e^L$.
  Przykład: $\lim_{x\to 0^+} x^x$: $\ln y = x\ln x \to 0$, więc $\lim x^x = e^0 = 1$.

## 5.4. Pułapki (częste błędy egzaminacyjne)

1. **Nie różniczkujemy jak iloraz!** Liczymy $\frac{f'}{g'}$, a NIE $\left(\frac{f}{g}\right)'$.
2. **Sprawdź symbol PRZED zastosowaniem.** Jeśli to nie $\frac{0}{0}$ ani $\frac{\infty}{\infty}$, reguła nie obowiązuje (dostaniesz błędny wynik).
3. **Reguła może nie dać wyniku**, choć granica istnieje. Np. $\lim_{x\to\infty}\frac{x+\sin x}{x}$: de l'Hospital daje $\lim(1+\cos x)$ — brak granicy, a właściwa granica to $1$ (podziel przez $x$). Wtedy metoda zawodzi — trzeba inaczej.
4. Czasem prościej użyć **rozwinięcia Taylora** (rozdz. 6) niż wielokrotnie różniczkować.

---

# 6. Wzór Taylora

## 6.1. Intuicja

Chcemy **przybliżyć dowolną (gładką) funkcję wielomianem** w otoczeniu punktu $x_0$. Im wyższy stopień wielomianu, tym lepsze przybliżenie. Styczna (rozdz. 3) to przybliżenie stopnia 1 — Taylor to jego uogólnienie.

## 6.2. Wielomian Taylora

Wielomian Taylora stopnia $n$ funkcji $f$ w punkcie $x_0$:
$$P_n(x) = \sum_{k=0}^{n}\frac{f^{(k)}(x_0)}{k!}(x - x_0)^k = f(x_0) + f'(x_0)(x-x_0) + \frac{f''(x_0)}{2!}(x-x_0)^2 + \dots + \frac{f^{(n)}(x_0)}{n!}(x-x_0)^n.$$

## 6.3. Wzór Taylora z resztą

$$f(x) = P_n(x) + R_n(x),$$
gdzie $R_n$ to **reszta** (błąd przybliżenia). Dwie najważniejsze postacie:

- **Reszta Lagrange'a** (do szacowania błędu): istnieje $c$ między $x_0$ a $x$ takie, że
$$R_n(x) = \frac{f^{(n+1)}(c)}{(n+1)!}(x - x_0)^{n+1}.$$
- **Reszta Peano** (do granic): $R_n(x) = o\big((x-x_0)^n\big)$, czyli reszta dąży do zera szybciej niż $(x-x_0)^n$.

## 6.4. Wzór Maclaurina

To wzór Taylora dla $x_0 = 0$:
$$f(x) = f(0) + f'(0)x + \frac{f''(0)}{2!}x^2 + \dots + \frac{f^{(n)}(0)}{n!}x^n + R_n(x).$$

## 6.5. Rozwinięcia Maclaurina (do zapamiętania!)

$$e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \dots = \sum_{k=0}^{\infty}\frac{x^k}{k!}$$

$$\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \dots = \sum_{k=0}^{\infty}\frac{(-1)^k x^{2k+1}}{(2k+1)!}$$

$$\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dots = \sum_{k=0}^{\infty}\frac{(-1)^k x^{2k}}{(2k)!}$$

$$\ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \dots\quad (-1<x\le 1)$$

$$(1+x)^\alpha = 1 + \alpha x + \frac{\alpha(\alpha-1)}{2!}x^2 + \dots\quad (|x|<1)$$

$$\frac{1}{1-x} = 1 + x + x^2 + x^3 + \dots\quad (|x|<1)$$

## 6.6. Zastosowania

**(a) Obliczanie granic** — często szybsze niż de l'Hospital. Podstawiamy rozwinięcia i patrzymy na najniższą potęgę.
$$\lim_{x\to 0}\frac{\sin x - x}{x^3} = \lim_{x\to 0}\frac{\left(x - \frac{x^3}{6} + o(x^3)\right) - x}{x^3} = \lim_{x\to 0}\frac{-\frac{x^3}{6}+o(x^3)}{x^3} = -\frac{1}{6}.$$

**(b) Przybliżanie wartości** funkcji z szacowaniem błędu resztą Lagrange'a. Np. $e \approx 1 + 1 + \frac{1}{2} + \frac{1}{6} + \dots$

**(c) Badanie ekstremów wyższymi pochodnymi.** Jeśli $f'(x_0)=\dots=f^{(n-1)}(x_0)=0$ i $f^{(n)}(x_0)\ne 0$:
- $n$ parzyste → ekstremum ($f^{(n)}>0$ minimum, $<0$ maksimum),
- $n$ nieparzyste → brak ekstremum (punkt przegięcia z poziomą styczną).

---

# 7. Badanie przebiegu zmienności funkcji

To „zadanie zbiorcze" łączące wszystkie wcześniejsze narzędzia. Trzeba je umieć zrobić schematycznie.

## 7.1. Pełny schemat (kolejność kroków)

**1. Dziedzina** $D_f$ — gdzie funkcja jest określona (mianownik $\ne 0$, argument $\ln > 0$, argument $\sqrt{\ }\ge 0$ itd.).

**2. Własności wstępne:**
- **parzystość** ($f(-x)=f(x)$, wykres symetryczny względem osi $OY$) / **nieparzystość** ($f(-x)=-f(x)$, symetria względem $O$);
- **okresowość** (dla funkcji trygonometrycznych);
- **miejsca zerowe** ($f(x)=0$) i **punkt przecięcia z osią $OY$** ($f(0)$);
- **znak funkcji** (gdzie dodatnia/ujemna).

**3. Granice na krańcach dziedziny** i **asymptoty:**
- **pionowa** $x=a$: gdy $\lim_{x\to a^\pm} f(x)=\pm\infty$ (szukać w punktach wyłączonych z dziedziny);
- **pozioma** $y=b$: gdy $\lim_{x\to\pm\infty} f(x)=b$ (skończone);
- **ukośna** $y=mx+q$: gdy $m=\lim_{x\to\pm\infty}\frac{f(x)}{x}$ istnieje skończone i niezerowe, oraz $q=\lim_{x\to\pm\infty}\big(f(x)-mx\big)$ istnieje skończone. (Pozioma to szczególny przypadek ukośnej z $m=0$.)

**4. Pierwsza pochodna $f'$ — monotoniczność i ekstrema:**
- liczymy $f'$, znajdujemy punkty stacjonarne ($f'=0$) i punkty nieróżniczkowalności;
- badamy znak $f'$ na przedziałach: $f'>0$ → rośnie, $f'<0$ → maleje;
- **warunek wystarczający ekstremum:** jeśli $f'$ zmienia znak z $+$ na $-$ w $x_0$ → **maksimum lokalne**; z $-$ na $+$ → **minimum lokalne**; brak zmiany znaku → brak ekstremum.

**5. Druga pochodna $f''$ — wypukłość i punkty przegięcia:**
- $f''>0$ → funkcja **wypukła** (wygięta w górę, „miska", $\smile$);
- $f''<0$ → funkcja **wklęsła** (wygięta w dół, „kopuła", $\frown$);
- **punkt przegięcia:** punkt, w którym $f''$ zmienia znak (zmiana wypukłości na wklęsłość lub odwrotnie).

**6. Tabela przebiegu zmienności** — zbiera znaki $f'$, $f''$ i zachowanie $f$ w wierszach.

**7. Szkic wykresu** na podstawie tabeli.

## 7.2. Warunki na ekstremum — podsumowanie

- **Konieczny** (Fermat): $f'(x_0)=0$ (lub pochodna nie istnieje).
- **Wystarczający I (zmiana znaku $f'$):** patrz wyżej.
- **Wystarczający II (druga pochodna):** jeśli $f'(x_0)=0$ i $f''(x_0)>0$ → minimum; $f''(x_0)<0$ → maksimum. Gdy $f''(x_0)=0$ — test nie rozstrzyga, wracamy do zmiany znaku lub wyższych pochodnych (rozdz. 6.6).

## 7.3. Rozróżnienie ekstremum lokalnego i globalnego

- **lokalne** — najmniejsza/największa wartość w pewnym otoczeniu punktu;
- **globalne (absolutne)** na przedziale — najmniejsza/największa wartość w całej dziedzinie. Na $[a,b]$ szukamy jej wśród punktów stacjonarnych, punktów nieróżniczkowalności **i końców przedziału** $a,b$ (to częsty błąd — pominięcie końców).

---

# 8. Całka nieoznaczona

## 8.1. Intuicja

Całkowanie nieoznaczone to **odwrotność różniczkowania**: szukamy funkcji, której pochodną jest dana funkcja. To jak pytanie „co zróżniczkowane daje $f$?".

## 8.2. Funkcja pierwotna i całka nieoznaczona

Funkcja $F$ jest **funkcją pierwotną** funkcji $f$ na przedziale, gdy $F'(x)=f(x)$.

**Całka nieoznaczona** to zbiór wszystkich funkcji pierwotnych:
$$\int f(x)\,dx = F(x) + C,$$
gdzie $C$ to dowolna **stała całkowania**. Dlaczego $+C$? Bo jeśli $F'=f$, to i $(F+C)'=f$ — pierwotnych jest nieskończenie wiele, różnią się o stałą.

> **Nie zapominaj o $+C$** — to typowa strata punktów!

## 8.3. Liniowość

$$\int \big(af(x) + bg(x)\big)\,dx = a\int f(x)\,dx + b\int g(x)\,dx.$$
> Uwaga: **nie ma** wzoru na całkę iloczynu ani ilorazu jako iloczynu/ilorazu całek. To zupełnie inna sytuacja niż pochodne.

## 8.4. Tabela całek podstawowych (do zapamiętania)

$$\int x^n\,dx = \frac{x^{n+1}}{n+1} + C\ (n\ne -1),\qquad \int \frac{1}{x}\,dx = \ln|x| + C$$

$$\int e^x\,dx = e^x + C,\qquad \int a^x\,dx = \frac{a^x}{\ln a} + C$$

$$\int \sin x\,dx = -\cos x + C,\qquad \int \cos x\,dx = \sin x + C$$

$$\int \frac{1}{\cos^2 x}\,dx = \tan x + C,\qquad \int \frac{1}{\sin^2 x}\,dx = -\cot x + C$$

$$\int \frac{1}{1+x^2}\,dx = \arctan x + C,\qquad \int \frac{1}{\sqrt{1-x^2}}\,dx = \arcsin x + C$$

## 8.5. Metoda I — całkowanie przez podstawianie (zamiana zmiennej)

Wynika z reguły łańcuchowej „na odwrót":
$$\int f(g(x))\,g'(x)\,dx = \int f(t)\,dt,\quad t = g(x),\ dt = g'(x)\,dx.$$
**Przepis:** wypatrz w całce „funkcję i jej pochodną". Podstaw $t=g(x)$, policz $dt$, zamień całą całkę na zmienną $t$.

Przykład: $\displaystyle\int 2x\cos(x^2)\,dx$. Podstaw $t=x^2$, $dt=2x\,dx$: $\int\cos t\,dt = \sin t + C = \sin(x^2)+C$.

Szczególne przydatne wzory:
$$\int \frac{g'(x)}{g(x)}\,dx = \ln|g(x)| + C,\qquad \int g'(x)\,e^{g(x)}\,dx = e^{g(x)}+C.$$

## 8.6. Metoda II — całkowanie przez części

Wynika z reguły iloczynu „na odwrót":
$$\int u\,dv = uv - \int v\,du,\quad\text{czyli}\quad \int u(x)v'(x)\,dx = u(x)v(x) - \int u'(x)v(x)\,dx.$$
**Kiedy stosować:** iloczyn dwóch „różnych typów" funkcji, np. wielomian × wykładnicza/trygonometryczna, lub gdy pojawia się $\ln x$, $\arctan x$ itp.

**Reguła wyboru $u$ (schemat LIATE)** — na $u$ wybieramy funkcję z wcześniejszej kategorii:
**L**ogarytmiczna → **I**nverse (cyklometryczna) → **A**lgebraiczna (wielomian) → **T**rygonometryczna → **E**xponential (wykładnicza).

Przykład: $\displaystyle\int x e^x\,dx$. Bierzemy $u=x$ ($du=dx$), $dv=e^x dx$ ($v=e^x$): $= xe^x - \int e^x\,dx = xe^x - e^x + C$.

Przykład z „trickiem": $\displaystyle\int \ln x\,dx$. $u=\ln x$, $dv=dx$: $= x\ln x - \int x\cdot\frac{1}{x}\,dx = x\ln x - x + C$.

## 8.7. Metoda III — całkowanie funkcji wymiernych (rozkład na ułamki proste)

Aby scałkować $\dfrac{W(x)}{P(x)}$ (wielomiany):
1. Jeśli $\deg W \ge \deg P$ — najpierw **podziel z resztą** (wyodrębnij wielomian).
2. Rozłóż mianownik na czynniki liniowe i nierozkładalne kwadratowe.
3. Rozłóż ułamek na **ułamki proste**:
   - czynnik $(x-a)$ → składnik $\dfrac{A}{x-a}$,
   - czynnik $(x-a)^k$ → składniki $\dfrac{A_1}{x-a}+\dots+\dfrac{A_k}{(x-a)^k}$,
   - czynnik nierozkładalny $x^2+px+q$ → składnik $\dfrac{Bx+C}{x^2+px+q}$.
4. Scałkuj każdy składnik ($\ln$, $\arctan$, potęgi).

Przykład: $\displaystyle\int \frac{1}{x^2-1}\,dx = \int\left(\frac{1/2}{x-1} - \frac{1/2}{x+1}\right)dx = \frac{1}{2}\ln\left|\frac{x-1}{x+1}\right| + C$.

## 8.8. Podstawienia trygonometryczne

Dla wyrażeń z pierwiastkami:
- $\sqrt{a^2 - x^2}$ → $x = a\sin t$,
- $\sqrt{a^2 + x^2}$ → $x = a\tan t$,
- $\sqrt{x^2 - a^2}$ → $x = \dfrac{a}{\cos t}$.

## 8.9. Ważne ostrzeżenie

Nie każda funkcja elementarna ma pierwotną w postaci elementarnej. Klasyczne przykłady „nieelementarnych" całek: $\int e^{-x^2}\,dx$, $\int \frac{\sin x}{x}\,dx$, $\int \frac{1}{\ln x}\,dx$. Istnieją, ale nie da się ich zapisać wzorem elementarnym.

---

# 9. Całka oznaczona. Całka Riemanna

## 9.1. Intuicja

Całka oznaczona $\int_a^b f(x)\,dx$ to **pole pod wykresem** funkcji nad przedziałem $[a,b]$ (z uwzględnieniem znaku: pole nad osią liczymy na plus, pod osią na minus).

## 9.2. Konstrukcja Riemanna

Dzielimy $[a,b]$ na $n$ podprzedziałów punktami $a=x_0<x_1<\dots<x_n=b$. W każdym wybieramy punkt $\xi_i\in[x_{i-1},x_i]$ i tworzymy **sumę Riemanna**:
$$S = \sum_{i=1}^{n} f(\xi_i)\,\Delta x_i,\qquad \Delta x_i = x_i - x_{i-1}.$$
Każdy składnik to pole prostokąta. Gdy „drobność" podziału dąży do zera i suma dąży do wspólnej granicy niezależnie od wyborów, funkcję nazywamy **całkowalną w sensie Riemanna**, a granicę oznaczamy:
$$\int_a^b f(x)\,dx = \lim_{\text{drobność}\to 0}\sum_{i=1}^n f(\xi_i)\Delta x_i.$$

## 9.3. Warunki całkowalności

- Każda funkcja **ciągła** na $[a,b]$ jest całkowalna.
- Każda funkcja **monotoniczna** i ograniczona na $[a,b]$ jest całkowalna.
- Funkcja z **skończoną liczbą punktów nieciągłości** (ograniczona) jest całkowalna.
- Funkcja nieograniczona na $[a,b]$ **nie** jest całkowalna w sensie Riemanna (potrzeba całki niewłaściwej).

## 9.4. Własności całki oznaczonej

$$\int_a^b (\alpha f + \beta g) = \alpha\int_a^b f + \beta\int_a^b g\quad\text{(liniowość)}$$
$$\int_a^b f = \int_a^c f + \int_c^b f\quad\text{(addytywność względem przedziału)}$$
$$\int_a^a f = 0,\qquad \int_a^b f = -\int_b^a f$$
$$f\le g\ \text{na}\ [a,b]\ \Rightarrow\ \int_a^b f \le \int_a^b g\quad\text{(monotoniczność)}$$
$$\left|\int_a^b f\right| \le \int_a^b |f|$$

## 9.5. Twierdzenie o wartości średniej dla całek

Jeśli $f$ jest ciągła na $[a,b]$, to istnieje $c\in[a,b]$ takie, że
$$\int_a^b f(x)\,dx = f(c)\cdot(b-a).$$
Wartość $\frac{1}{b-a}\int_a^b f$ to **średnia wartość funkcji** na przedziale.

## 9.6. Podstawowe twierdzenie rachunku całkowego (Newtona–Leibniza) — SERCE ROZDZIAŁU

**Część I (funkcja górnej granicy).** Jeśli $f$ ciągła, to funkcja $\Phi(x)=\int_a^x f(t)\,dt$ jest różniczkowalna i $\Phi'(x)=f(x)$. Czyli całkowanie i różniczkowanie są operacjami odwrotnymi.

**Część II (wzór Newtona–Leibniza).** Jeśli $F$ jest dowolną funkcją pierwotną $f$ (ciągłej), to:
$$\int_a^b f(x)\,dx = F(b) - F(a) = \big[F(x)\big]_a^b.$$
To **łączy** całkę oznaczoną (pole, granica sum) z nieoznaczoną (pierwotna). Dzięki temu pola liczymy, znajdując pierwotną.

Przykład: $\displaystyle\int_0^1 x^2\,dx = \left[\frac{x^3}{3}\right]_0^1 = \frac{1}{3} - 0 = \frac{1}{3}.$

**Pochodna całki ze zmienną granicą (z regułą łańcuchową):**
$$\frac{d}{dx}\int_{a}^{g(x)} f(t)\,dt = f(g(x))\cdot g'(x).$$

## 9.7. Metody w całce oznaczonej

**Przez części:** $\displaystyle\int_a^b u\,dv = \big[uv\big]_a^b - \int_a^b v\,du.$

**Przez podstawianie** — pamiętaj o **zmianie granic** całkowania (albo wróć do zmiennej $x$ przed podstawieniem granic):
$$\int_a^b f(g(x))g'(x)\,dx = \int_{g(a)}^{g(b)} f(t)\,dt.$$

**Symetria (skrót):** jeśli $f$ nieparzysta, $\int_{-a}^{a} f = 0$; jeśli parzysta, $\int_{-a}^{a} f = 2\int_0^a f$.

## 9.8. Całki niewłaściwe

Gdy przedział jest nieograniczony lub funkcja nieograniczona — definiujemy przez granicę:
$$\int_a^{\infty} f(x)\,dx = \lim_{T\to\infty}\int_a^T f(x)\,dx,\qquad \int_a^b f\,(\text{osobliwość w }b) = \lim_{\varepsilon\to 0^+}\int_a^{b-\varepsilon} f.$$
Jeśli granica jest skończona — całka **zbieżna**, w przeciwnym razie **rozbieżna**.
Ważny wzorzec: $\displaystyle\int_1^\infty \frac{dx}{x^p}$ zbieżna $\iff p>1$; $\displaystyle\int_0^1 \frac{dx}{x^p}$ zbieżna $\iff p<1$.

---

# 10. Zastosowania całki funkcji jednej zmiennej

## 10.1. Pole pod wykresem

Pole obszaru między wykresem $f\ge 0$ a osią $OX$ na $[a,b]$:
$$P = \int_a^b f(x)\,dx.$$
Gdy funkcja zmienia znak — pole liczymy z wartością bezwzględną (rozbijając na kawałki): $P=\int_a^b |f(x)|\,dx$.

## 10.2. Pole między dwiema krzywymi

Dla $f(x)\ge g(x)$ na $[a,b]$:
$$P = \int_a^b \big(f(x) - g(x)\big)\,dx\quad(\text{„górna minus dolna"}).$$
Najpierw znajdź punkty przecięcia (rozwiązując $f=g$) — to granice całkowania.

## 10.3. Długość łuku krzywej

Dla wykresu $y=f(x)$ na $[a,b]$:
$$L = \int_a^b \sqrt{1 + \big(f'(x)\big)^2}\,dx.$$
Intuicja: sumujemy maleńkie odcinki $\sqrt{dx^2 + dy^2} = \sqrt{1+(y')^2}\,dx$ (twierdzenie Pitagorasa dla nieskończenie małych przyrostów).

## 10.4. Objętość bryły obrotowej

Obracamy wykres $y=f(x)$, $x\in[a,b]$, wokół **osi $OX$**:
$$V = \pi\int_a^b \big(f(x)\big)^2\,dx.$$
Intuicja: każdy przekrój to krążek o promieniu $f(x)$ i polu $\pi f(x)^2$; sumujemy „plasterki" o grubości $dx$.

Obrót wokół **osi $OY$** (metoda powłok, dla $f\ge 0$ na $[a,b]$, $a\ge 0$):
$$V = 2\pi\int_a^b x\,f(x)\,dx.$$

## 10.5. Pole powierzchni bryły obrotowej (wokół osi $OX$)

$$S = 2\pi\int_a^b f(x)\sqrt{1 + \big(f'(x)\big)^2}\,dx.$$

## 10.6. Przykład kompleksowy

Obszar pod $y=\sqrt{x}$ na $[0,4]$, obracany wokół $OX$:
- Pole: $\int_0^4 \sqrt{x}\,dx = \left[\frac{2}{3}x^{3/2}\right]_0^4 = \frac{2}{3}\cdot 8 = \frac{16}{3}$.
- Objętość: $\pi\int_0^4 (\sqrt{x})^2\,dx = \pi\int_0^4 x\,dx = \pi\left[\frac{x^2}{2}\right]_0^4 = 8\pi$.

---

# Dodatek A — Najczęstsze błędy egzaminacyjne (checklist)

- **Ciągi:** rozbijanie granicy typu $\infty-\infty$ na dwie granice; zapominanie, że arytmetyka granic wymaga skończoności.
- **Granice funkcji:** liczenie granicy przez podstawienie w punkcie spoza dziedziny; mylenie granic jednostronnych.
- **Pochodne:** błąd w regule łańcuchowej (pominięcie pochodnej wewnętrznej); traktowanie $f'(x_0)=0$ jako gwarancji ekstremum.
- **de l'Hospital:** stosowanie bez sprawdzenia symbolu; różniczkowanie jako iloraz $\left(\frac{f}{g}\right)'$ zamiast $\frac{f'}{g'}$.
- **Taylor:** pomijanie reszty $o(\cdot)$ przy granicach; złe zapamiętane rozwinięcia (znaki w $\sin/\cos$).
- **Przebieg zmienności:** pominięcie asymptot ukośnych; szukanie ekstremum globalnego bez sprawdzenia końców przedziału.
- **Całka nieoznaczona:** brak stałej $+C$; próba „całki iloczynu = iloczyn całek".
- **Całka oznaczona:** przy podstawianiu niezmienienie granic; mylenie pola (zawsze $\ge 0$, z $|f|$) z całką (może być ujemna).

---

# Dodatek B — Zbiorcza tabela pochodnych i całek

| Funkcja | Pochodna | Całka $\int(\cdot)dx$ |
|---|---|---|
| $x^n$ | $nx^{n-1}$ | $\frac{x^{n+1}}{n+1}\ (n\ne -1)$ |
| $\frac1x$ | $-\frac{1}{x^2}$ | $\ln|x|$ |
| $e^x$ | $e^x$ | $e^x$ |
| $a^x$ | $a^x\ln a$ | $\frac{a^x}{\ln a}$ |
| $\ln x$ | $\frac1x$ | $x\ln x - x$ |
| $\sin x$ | $\cos x$ | $-\cos x$ |
| $\cos x$ | $-\sin x$ | $\sin x$ |
| $\tan x$ | $\frac{1}{\cos^2 x}$ | $-\ln|\cos x|$ |
| $\frac{1}{1+x^2}$ | — | $\arctan x$ |
| $\frac{1}{\sqrt{1-x^2}}$ | — | $\arcsin x$ |

---

# Dodatek C — Trzy podstawowe wzory całkowe do zapamiętania na pamięć

$$\int u\,dv = uv - \int v\,du\qquad\text{(przez części)}$$
$$\int f(g(x))g'(x)\,dx = \int f(t)\,dt,\ t=g(x)\qquad\text{(podstawianie)}$$
$$\int_a^b f(x)\,dx = F(b)-F(a),\ F'=f\qquad\text{(Newton–Leibniz)}$$

---

# Dodatek D — Mapa powiązań (jak rozdziały łączą się w całość)

1. **Ciągi** dają aparat granicy → 2. **Granica funkcji** buduje się na granicy ciągów (def. Heinego) → **Ciągłość** to granica równa wartości.
3. **Pochodna** to szczególna granica (ilorazu różnicowego) → 4. **Twierdzenia o wartości średniej** wiążą pochodną z monotonicznością → 5. **de l'Hospital** i 6. **Taylor** to narzędzia obliczeniowe oparte na pochodnych → 7. **Przebieg zmienności** to synteza rozdziałów 3–6.
8. **Całka nieoznaczona** to odwrotność pochodnej → 9. **Całka Riemanna** to pole (granica sum), a twierdzenie Newtona–Leibniza spina ją z pierwotną → 10. **Zastosowania** (pole, długość, objętość) to całka oznaczona w akcji.

Wszystko stoi na jednym filarze: **granicy**.

---

*Powodzenia na egzaminie! Ucz się nie tylko wzorów, ale i założeń twierdzeń — egzaminatorzy często pytają „co się stanie, gdy usuniemy dane założenie".*
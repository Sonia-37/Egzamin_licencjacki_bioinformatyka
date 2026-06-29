# Fizyka — mechanika: kompletne notatki na zaliczenie

## Spis treści

1. [Matematyka w fizyce: wektory i skalary](#1-wektory-i-skalary)
2. [Kinematyka i ruch względny](#2-kinematyka)
3. [Ruch w 2D: rzuty i ruch po okręgu](#3-ruch-w-2d)
4. [Zasady dynamiki Newtona i siły](#4-dynamika-newtona)
5. [Dynamika: równia, układy ciał](#5-rownia-uklady-cial)
6. [Pęd, praca, moc](#6-ped-praca-moc)
7. [Energia i zasada zachowania energii](#7-energia)
8. [Ruch obrotowy: moment bezwładności, siły, pędu](#8-ruch-obrotowy)
9. [Ruch harmoniczny i wahadło](#9-ruch-harmoniczny)
10. [Ściąga — wzory i stałe](#10-sciaga)

---

## 1. Wektory i skalary

### 1.1. Skalary kontra wektory

- **Skalar** — wielkość określona **tylko liczbą** (z jednostką): masa, czas, temperatura, droga, energia, praca, moc.
- **Wektor** — wielkość mająca **wartość, kierunek i zwrot**: przemieszczenie, prędkość, przyspieszenie, siła, pęd. Oznaczamy strzałką $\vec{v}$ lub pogrubieniem.

> **Pułapka pojęciowa:** **droga** (skalar, zawsze $\ge0$) ≠ **przemieszczenie** (wektor od początku do końca). Np. po pełnym okrążeniu droga = obwód, przemieszczenie = 0. Podobnie **szybkość** (skalar) ≠ **prędkość** (wektor).

### 1.2. Składowe wektora

Wektor na płaszczyźnie rozkładamy na składowe wzdłuż osi:
$$v_x = v\cos\alpha,\qquad v_y = v\sin\alpha,$$
gdzie $\alpha$ — kąt z osią $x$. Wartość (długość) wektora:
$$v = |\vec v| = \sqrt{v_x^2 + v_y^2},\qquad \tan\alpha = \frac{v_y}{v_x}.$$

Rozkład na składowe to **podstawowa technika** rozwiązywania zadań — zamieniamy jeden problem 2D na dwa niezależne problemy 1D (osobno $x$, osobno $y$).

### 1.3. Działania na wektorach

**Dodawanie** — metodą równoległoboku albo "koniec do początku"; w składowych:
$$\vec a + \vec b = (a_x+b_x,\; a_y+b_y).$$
**Mnożenie przez skalar** $k\vec a = (ka_x, ka_y)$ — zmienia długość (i zwrot, gdy $k<0$).

**Iloczyn skalarny** (wynik = liczba):
$$\vec a \cdot \vec b = a_x b_x + a_y b_y = |\vec a|\,|\vec b|\cos\theta.$$
Zastosowanie: praca $W=\vec F\cdot\vec s$. Gdy $\vec a\perp\vec b$, iloczyn skalarny = 0.

**Iloczyn wektorowy** (wynik = wektor prostopadły do obu):
$$|\vec a \times \vec b| = |\vec a|\,|\vec b|\sin\theta.$$
Zastosowanie: moment siły $\vec M=\vec r\times\vec F$, moment pędu.

### 1.4. Jednostki SI (układ podstawowy)

| Wielkość | Jednostka | Symbol |
|---|---|---|
| długość | metr | m |
| masa | kilogram | kg |
| czas | sekunda | s |
| prędkość | metr na sekundę | m/s |
| przyspieszenie | | m/s² |
| siła | niuton | N = kg·m/s² |
| energia, praca | dżul | J = N·m |
| moc | wat | W = J/s |

> **Zasada na kolokwium:** **zawsze przeliczaj na SI** przed liczeniem (km/h → m/s przez podzielenie przez 3,6; gramy → kg; cm → m). Większość błędów to błędy jednostek. Warto sprawdzać wynik **analizą wymiarową**.

---

## 2. Kinematyka

### 2.1. Podstawowe wielkości

- **Położenie** $x(t)$ — gdzie jest ciało.
- **Przemieszczenie** $\Delta x = x_2 - x_1$ (wektor).
- **Prędkość średnia** $v_{śr} = \dfrac{\Delta x}{\Delta t}$; **prędkość chwilowa** $v = \dfrac{dx}{dt}$ (pochodna położenia).
- **Przyspieszenie** $a = \dfrac{\Delta v}{\Delta t} = \dfrac{dv}{dt}$ (tempo zmiany prędkości).

### 2.2. Ruch jednostajny prostoliniowy ($a=0$)

Prędkość stała: $\boxed{x = x_0 + vt}$. Wykres $x(t)$ — linia prosta; wykres $v(t)$ — pozioma; **droga = pole pod wykresem $v(t)$**.

### 2.3. Ruch jednostajnie zmienny ($a=\text{const}$)

Trzy kluczowe wzory (do zapamiętania!):
$$v = v_0 + at,$$
$$x = x_0 + v_0 t + \tfrac{1}{2}a t^2,$$
$$v^2 = v_0^2 + 2a\,\Delta x \quad(\text{wzór bez czasu — bardzo przydatny!}).$$

- przyspieszony: $a>0$ (zwrot $a$ zgodny z $v$),
- opóźniony: $a<0$ (zwrot $a$ przeciwny do $v$) — uwaga na znaki!

> **Strategia:** wypisz dane ($v_0, v, a, t, \Delta x$), zobacz czego brakuje i co masz, dobierz wzór, w którym występuje tylko jedna niewiadoma. Wzór $v^2=v_0^2+2a\Delta x$ stosuj, gdy **nie ma/nie potrzeba czasu**.

### 2.4. Spadek swobodny i rzut pionowy

To ruch jednostajnie zmienny z $a=g\approx 9{,}81\ \text{m/s}^2$ (często przyjmujemy $g\approx 10$ dla uproszczenia), skierowanym w **dół**.

- **Spadek swobodny** (bez prędkości początkowej): $v=gt$, $h=\tfrac12 g t^2$, $v=\sqrt{2gh}$.
- **Rzut pionowy w górę:** ciało zwalnia ($a=-g$), na szczycie $v=0$, wraca. Czas wznoszenia $t=\tfrac{v_0}{g}$, maksymalna wysokość $h_{max}=\dfrac{v_0^2}{2g}$.

> **Pułapka znaków:** ustal dodatni kierunek osi (np. w górę "+") i konsekwentnie go trzymaj — wtedy $g$ jest ujemne. Najczęstszy błąd to mieszanie znaków.

### 2.5. Ruch względny (układy odniesienia)

Prędkość ciała zależy od **układu odniesienia**. Składanie prędkości (Galileusz):
$$\vec v_{ciała/ziemi} = \vec v_{ciała/pojazdu} + \vec v_{pojazdu/ziemi}.$$

> **Przykład.** Człowiek idzie $2\ \text{m/s}$ do przodu w pociągu jadącym $30\ \text{m/s}$ → względem ziemi $32\ \text{m/s}$. Idąc do tyłu → $28\ \text{m/s}$. Gdy prędkości są pod kątem (np. łódka i prąd rzeki) — **dodaj wektorowo** (rozkład na składowe!).

---

## 3. Ruch w 2D

### 3.1. Zasada niezależności ruchów

Kluczowa idea wszystkich rzutów: ruch w poziomie ($x$) i w pionie ($y$) są **niezależne**. W poziomie zwykle ruch jednostajny ($a_x=0$), w pionie — jednostajnie zmienny z $g$. Rozwiązujemy osobno każdą oś, łączymy przez wspólny czas $t$.

### 3.2. Rzut poziomy

Ciało wyrzucone poziomo z prędkością $v_0$ z wysokości $h$:

| Oś | Ruch | Wzory |
|---|---|---|
| poziomo $x$ | jednostajny | $x = v_0 t$ |
| pionowo $y$ | spadek swobodny | $y = \tfrac12 g t^2$, $v_y = gt$ |

- **Czas lotu** (z równania na $h$): $t = \sqrt{\dfrac{2h}{g}}$ — taki sam jak przy zwykłym spadku!
- **Zasięg** (donośność): $z = v_0\sqrt{\dfrac{2h}{g}}$.
- Tor ruchu: **parabola**. Prędkość w danej chwili: $v=\sqrt{v_0^2 + (gt)^2}$.

### 3.3. Rzut ukośny (pod kątem $\alpha$)

Prędkość początkowa $v_0$ pod kątem $\alpha$: składowe $v_{0x}=v_0\cos\alpha$, $v_{0y}=v_0\sin\alpha$.

| Wielkość | Wzór |
|---|---|
| czas wznoszenia | $t_w = \dfrac{v_0\sin\alpha}{g}$ |
| całkowity czas lotu | $t_c = \dfrac{2v_0\sin\alpha}{g}$ |
| maksymalna wysokość | $H = \dfrac{v_0^2\sin^2\alpha}{2g}$ |
| zasięg (na tym samym poziomie) | $Z = \dfrac{v_0^2\sin 2\alpha}{g}$ |

> **Fakt egzaminacyjny:** maksymalny zasięg daje kąt $\alpha=45°$ (bo $\sin 2\alpha=1$). Kąty dopełniające (np. 30° i 60°) dają **ten sam zasięg**.

### 3.4. Ruch po okręgu (jednostajny)

Ciało porusza się po okręgu o promieniu $r$ ze stałą szybkością.

**Wielkości kątowe:**
- **Okres** $T$ — czas jednego obiegu [s].
- **Częstotliwość** $f = \dfrac{1}{T}$ [Hz].
- **Prędkość kątowa** $\omega = \dfrac{2\pi}{T} = 2\pi f$ [rad/s].

**Związki liniowo-kątowe:**
$$v = \omega r \quad(\text{prędkość liniowa, styczna do okręgu}).$$

**Przyspieszenie dośrodkowe** — choć szybkość stała, kierunek prędkości się zmienia, więc jest przyspieszenie skierowane **do środka**:
$$a_d = \frac{v^2}{r} = \omega^2 r.$$

**Siła dośrodkowa** (przyczyna ruchu po okręgu, skierowana do środka):
$$F_d = m a_d = \frac{mv^2}{r} = m\omega^2 r.$$

> **Najważniejsza pułapka:** siła dośrodkowa to **nie** nowy rodzaj siły — to **wypadkowa** istniejących sił (grawitacji, naprężenia, tarcia, reakcji), która "zakręca" ciało. "Siła odśrodkowa" pojawia się tylko w nieinercjalnym układzie obracającym się — w zadaniach maturalnych zwykle jej nie używamy.

---

## 4. Dynamika Newtona

### 4.1. Trzy zasady dynamiki

**I zasada (bezwładności):** jeśli na ciało nie działa siła wypadkowa (lub jest zerowa), to ciało pozostaje w spoczynku albo porusza się ruchem jednostajnym prostoliniowym. Definiuje **układy inercjalne**.

**II zasada (podstawowe równanie dynamiki):**
$$\vec F_{wyp} = m\vec a \qquad\Longleftrightarrow\qquad \vec a = \frac{\vec F_{wyp}}{m}.$$
Przyspieszenie jest proporcjonalne do siły wypadkowej i odwrotnie proporcjonalne do masy. **To najważniejszy wzór całej mechaniki.**

**III zasada (akcji i reakcji):** gdy ciało A działa na B siłą $\vec F$, to B działa na A siłą $-\vec F$ (równa co do wartości, przeciwny zwrot). **Uwaga:** te siły działają na **różne ciała**, więc się **nie** równoważą.

### 4.2. Najważniejsze siły

| Siła | Wzór | Uwagi |
|---|---|---|
| ciężar (grawitacji) | $F_g = mg$ | skierowana pionowo w dół |
| siła reakcji podłoża (normalna) | $N$ | prostopadła do powierzchni |
| tarcie | $T = \mu N$ | przeciwne do ruchu/tendencji ruchu |
| sprężystości (Hooke) | $F = -kx$ | proporcjonalna do wydłużenia |
| grawitacji powszechnej | $F = G\dfrac{m_1 m_2}{r^2}$ | między masami |

**Tarcie:** statyczne (do granicy $T_{max}=\mu_s N$, póki ciało stoi) i kinetyczne ($T=\mu_k N$, gdy się ślizga), zwykle $\mu_s>\mu_k$. Tarcie **nie zależy** od pola powierzchni styku (w modelu uproszczonym), zależy od $N$ i rodzaju powierzchni.

### 4.3. Metoda rozwiązywania zadań z dynamiki (PRZEPIS)

1. **Narysuj wszystkie siły** działające na ciało (diagram sił / "ciało swobodne").
2. **Wybierz układ współrzędnych** (często jedna oś wzdłuż ruchu).
3. **Rozłóż siły na składowe** w tym układzie.
4. **Zapisz II zasadę** dla każdej osi osobno: $\sum F_x = ma_x$, $\sum F_y = ma_y$.
5. **Rozwiąż układ równań** względem szukanej wielkości.

> Pamiętaj: w kierunku **bez** przyspieszenia (np. pion przy ruchu poziomym) siły się **równoważą** ($\sum F=0$).

---

## 5. Równia, układy ciał

### 5.1. Równia pochyła

Ciało na równi nachylonej pod kątem $\alpha$. Ciężar $mg$ rozkładamy na składowe **wzdłuż** i **prostopadle** do równi (to klucz do wszystkich zadań z równią):

- składowa **zsuwająca** (wzdłuż równi, w dół): $F_\parallel = mg\sin\alpha$,
- składowa **dociskająca** (prostopadła): $F_\perp = mg\cos\alpha$.

Siła reakcji podłoża $N = mg\cos\alpha$. Siła tarcia $T = \mu N = \mu mg\cos\alpha$.

**Przyspieszenie zsuwania** (bez tarcia): $a = g\sin\alpha$.
**Z tarciem** (ciało zjeżdża): $a = g(\sin\alpha - \mu\cos\alpha)$.

> **Warunek spoczynku na równi:** ciało nie zsunie się, gdy $\tan\alpha \le \mu_s$ (siła zsuwająca nie przekracza maksymalnego tarcia statycznego). Kąt graniczny: $\tan\alpha_{gr}=\mu_s$.

> **Pułapka:** to $\sin\alpha$ odpowiada za zsuwanie, a $\cos\alpha$ za docisk — łatwo pomylić. Sprawdź skrajne przypadki: dla $\alpha=0°$ (płasko) zsuwanie $=0$ → musi być $\sin$; dla $\alpha=90°$ (pionowo) docisk $=0$ → musi być $\cos$.

### 5.2. Układy ciał (klocki, bloczki)

Gdy ciała są połączone (nitką, stykają się), poruszają się z **tym samym** przyspieszeniem (jeśli nić nierozciągliwa). Dwie metody:

**Metoda 1 — układ jako całość:** $a = \dfrac{\text{siła napędzająca cały układ}}{\text{masa całkowita}}$.

**Metoda 2 — każde ciało osobno:** zapisz II zasadę dla każdego ciała (z siłą naprężenia nici $N$ jako niewiadomą), rozwiąż układ równań.

> **Przykład (dwa klocki $m_1, m_2$ ciągnięte siłą $F$ po gładkim stole):**
> Całość: $a = \dfrac{F}{m_1+m_2}$. Naprężenie między nimi: $N = m_2 a = \dfrac{m_2 F}{m_1+m_2}$.

**Maszyna Atwooda** (dwie masy na bloczku): $a = \dfrac{(m_1-m_2)g}{m_1+m_2}$, naprężenie $N=\dfrac{2m_1 m_2 g}{m_1+m_2}$.

---

## 6. Pęd, praca, moc

### 6.1. Pęd

**Pęd** to wektor: $\vec p = m\vec v$ [kg·m/s]. Mówi o "ilości ruchu" ciała.

**II zasada w postaci pędowej:** $\vec F = \dfrac{\Delta \vec p}{\Delta t}$ — siła to tempo zmiany pędu.

**Popęd siły (impuls):** $\vec F\,\Delta t = \Delta \vec p$ — działanie siły przez czas zmienia pęd.

### 6.2. Zasada zachowania pędu

**W układzie izolowanym** (brak sił zewnętrznych) całkowity pęd jest **stały**:
$$\sum \vec p_{przed} = \sum \vec p_{po}.$$

To podstawa zadań o **zderzeniach** i **odrzucie**:

| Typ zderzenia | Zachowany pęd | Zachowana energia kinetyczna |
|---|---|---|
| **sprężyste (idealnie)** | tak | **tak** |
| **niesprężyste** | tak | nie (część → ciepło/deformacja) |
| **doskonale niesprężyste** (ciała się łączą) | tak | nie (maks. strata) |

> **Zderzenie doskonale niesprężyste:** $m_1 v_1 + m_2 v_2 = (m_1+m_2)v$ → $v = \dfrac{m_1 v_1 + m_2 v_2}{m_1+m_2}$.

> **Pułapka:** pęd to **wektor** — w zderzeniach 1D pamiętaj o **znakach** (kierunki przeciwne = przeciwne znaki). W 2D rozkładaj na składowe.

### 6.3. Praca

**Praca** siły stałej:
$$W = F s \cos\alpha = \vec F\cdot\vec s \quad[\text{J}],$$
gdzie $\alpha$ — kąt między siłą a przemieszczeniem.

- Siła wzdłuż ruchu ($\alpha=0$): $W=Fs$ (maksymalna, dodatnia).
- Siła prostopadła ($\alpha=90°$): $W=0$ (np. siła dośrodkowa nie wykonuje pracy! reakcja podłoża też nie).
- Siła przeciwna ($\alpha=180°$): $W=-Fs$ (np. praca tarcia jest ujemna).

Dla siły zmiennej: praca = **pole pod wykresem $F(x)$**.

### 6.4. Moc

**Moc** — tempo wykonywania pracy:
$$P = \frac{W}{t} \quad[\text{W}],\qquad P = Fv \ (\text{dla stałej siły i prędkości}).$$

> **Jednostki:** $1\ \text{W}=1\ \text{J/s}$. Uwaga na konia mechanicznego ($1\ \text{KM}\approx 735\ \text{W}$) i kilowatogodzinę ($1\ \text{kWh}=3{,}6\ \text{MJ}$ — to jednostka **energii**, nie mocy!).

---

## 7. Energia

### 7.1. Rodzaje energii mechanicznej

**Energia kinetyczna** (ruchu):
$$E_k = \frac{1}{2}mv^2.$$

**Energia potencjalna grawitacji** (położenia, względem poziomu odniesienia):
$$E_p = mgh.$$

**Energia potencjalna sprężystości** (ściśnięta/rozciągnięta sprężyna):
$$E_{sp} = \frac{1}{2}kx^2.$$

### 7.2. Twierdzenie o pracy i energii

Praca siły wypadkowej = zmiana energii kinetycznej:
$$W_{wyp} = \Delta E_k = \frac{1}{2}mv^2 - \frac{1}{2}mv_0^2.$$

### 7.3. Zasada zachowania energii mechanicznej

**Gdy działają tylko siły zachowawcze** (grawitacja, sprężystość — bez tarcia, oporu), całkowita energia mechaniczna jest stała:
$$E_k + E_p = \text{const} \qquad\Longleftrightarrow\qquad \frac{1}{2}mv_1^2 + mgh_1 = \frac{1}{2}mv_2^2 + mgh_2.$$

To **najpotężniejsze narzędzie** w zadaniach — pozwala znaleźć prędkość lub wysokość **bez** liczenia sił i czasu.

> **Przykłady zastosowania:**
> - Ciało spada z wysokości $h$: $mgh=\tfrac12 mv^2 \Rightarrow v=\sqrt{2gh}$ (masa się skraca!).
> - Wahadło: na dole cała energia jest kinetyczna, na górze cała potencjalna.

### 7.4. Gdy jest tarcie (siły niezachowawcze)

Energia mechaniczna **nie** jest zachowana — część zamienia się w ciepło:
$$E_{mech,\,pocz} = E_{mech,\,końc} + W_{tarcia},$$
gdzie $W_{tarcia}=T\cdot s=\mu N s$ to "stracona" energia (zamieniona w ciepło). Energia **całkowita** zawsze się zachowuje — tylko zmienia formę.

> **Pułapka:** zasadę zachowania energii **mechanicznej** stosuj tylko bez tarcia/oporów. Z tarciem dodaj bilans z pracą tarcia.

---

## 8. Ruch obrotowy

### 8.1. Analogie ruch postępowy ↔ obrotowy

Ruch obrotowy opisujemy "obrotowymi odpowiednikami" wielkości liniowych:

| Postępowy | Obrotowy | Związek |
|---|---|---|
| droga $s$ | kąt $\varphi$ [rad] | $s=\varphi r$ |
| prędkość $v$ | prędkość kątowa $\omega$ | $v=\omega r$ |
| przyspieszenie $a$ | przyspieszenie kątowe $\varepsilon$ | $a=\varepsilon r$ |
| masa $m$ | moment bezwładności $I$ | — |
| siła $F$ | moment siły $M$ | $M=Fr$ |
| pęd $p=mv$ | moment pędu $L=I\omega$ | — |
| $F=ma$ | $M=I\varepsilon$ | II zasada dla obrotów |
| $E_k=\tfrac12 mv^2$ | $E_k=\tfrac12 I\omega^2$ | energia obrotowa |

### 8.2. Moment siły (moment obrotowy)

$$M = F\,r\sin\alpha = F\,d,$$
gdzie $r$ — odległość od osi, $\alpha$ — kąt między $\vec F$ a ramieniem, $d=r\sin\alpha$ — **ramię siły** (prostopadła odległość osi od linii działania siły).

> **Warunek równowagi** ciała (ważne w statyce): suma sił = 0 **oraz** suma momentów sił = 0 (momenty "w lewo" = momenty "w prawo"). To podstawa zadań z dźwignią i belką.

### 8.3. Moment bezwładności

$I$ to "obrotowa masa" — opór przeciw zmianie ruchu obrotowego. Zależy od masy **i jej rozkładu** względem osi. Dla punktu materialnego $I=mr^2$. Dla brył (z tablic):

| Bryła (oś przez środek) | Moment bezwładności |
|---|---|
| obręcz/cienki pierścień | $I=mr^2$ |
| walec/krążek pełny | $I=\tfrac12 mr^2$ |
| kula pełna | $I=\tfrac25 mr^2$ |
| pręt (oś przez środek, prostopadle) | $I=\tfrac{1}{12}ml^2$ |

> Im dalej masa od osi, tym większy $I$ → trudniej rozkręcić/zatrzymać.

### 8.4. Zasada zachowania momentu pędu

W układzie bez zewnętrznego momentu siły moment pędu jest stały:
$$L = I\omega = \text{const} \quad\Longrightarrow\quad I_1\omega_1 = I_2\omega_2.$$

> **Klasyczny przykład:** łyżwiarka przyciąga ręce → zmniejsza $I$ → rośnie $\omega$ (kręci się szybciej). Zachowany jest $L$, nie $\omega$.

---

## 9. Ruch harmoniczny

### 9.1. Definicja i wielkości

**Ruch harmoniczny** to drgania, w których siła jest proporcjonalna do wychylenia i skierowana do położenia równowagi ($F=-kx$). Opis:
$$x(t) = A\sin(\omega t + \varphi_0),$$
gdzie $A$ — **amplituda** (maks. wychylenie), $\omega$ — częstość kołowa, $\varphi_0$ — faza początkowa.

- **Okres** $T=\dfrac{2\pi}{\omega}$, **częstotliwość** $f=\dfrac1T$.
- **Prędkość:** $v(t)=A\omega\cos(\omega t+\varphi_0)$, maks. $v_{max}=A\omega$ (w położeniu równowagi).
- **Przyspieszenie:** $a(t)=-A\omega^2\sin(\omega t+\varphi_0)=-\omega^2 x$, maks. $a_{max}=A\omega^2$ (w skrajnych wychyleniach).

> **Charakterystyczne:** w położeniu równowagi $v$ maksymalne, $a=0$; w skrajnym wychyleniu $v=0$, $a$ maksymalne. Energia ciągle przechodzi $E_k\leftrightarrow E_p$, suma stała: $E=\tfrac12 kA^2$.

### 9.2. Drgania ciężarka na sprężynie

$$T = 2\pi\sqrt{\frac{m}{k}},$$
gdzie $k$ — stała sprężystości. Okres rośnie z masą, maleje ze sztywnością sprężyny. **Nie zależy** od amplitudy.

### 9.3. Wahadło matematyczne

Punktowa masa na nieważkiej nici długości $l$. Dla **małych** wychyleń:
$$T = 2\pi\sqrt{\frac{l}{g}}.$$

> **Ważne fakty (częste pytania):**
> - Okres **nie zależy** od masy ani (dla małych kątów) od amplitudy — izochronizm wahadła.
> - Zależy od długości $l$ i przyspieszenia $g$ (na Księżycu wahadło chodzi wolniej).
> - Wzór jest przybliżeniem dla małych kątów (do ~10°), gdzie $\sin\varphi\approx\varphi$.

---

## 10. Ściąga

### Kinematyka
- Ruch jednostajny: $x=x_0+vt$.
- Jednostajnie zmienny: $v=v_0+at$; $x=x_0+v_0t+\tfrac12 at^2$; $v^2=v_0^2+2a\Delta x$.
- Spadek: $v=\sqrt{2gh}$, $h=\tfrac12 gt^2$.
- Rzut ukośny: $H=\dfrac{v_0^2\sin^2\alpha}{2g}$, $Z=\dfrac{v_0^2\sin 2\alpha}{g}$ (maks. dla 45°).

### Ruch po okręgu
- $\omega=\dfrac{2\pi}{T}=2\pi f$; $v=\omega r$; $a_d=\dfrac{v^2}{r}=\omega^2 r$; $F_d=\dfrac{mv^2}{r}$.

### Dynamika
- II zasada: $\vec F_{wyp}=m\vec a$. Tarcie: $T=\mu N$.
- Równia: $F_\parallel=mg\sin\alpha$, $N=mg\cos\alpha$, $a=g(\sin\alpha-\mu\cos\alpha)$.
- Atwood: $a=\dfrac{(m_1-m_2)g}{m_1+m_2}$.

### Pęd, praca, moc, energia
- $p=mv$; popęd $F\Delta t=\Delta p$; zachowanie pędu w układzie izolowanym.
- $W=Fs\cos\alpha$; $P=\dfrac{W}{t}=Fv$.
- $E_k=\tfrac12 mv^2$; $E_p=mgh$; $E_{sp}=\tfrac12 kx^2$.
- Zachowanie energii mechanicznej (bez tarcia): $\tfrac12 mv_1^2+mgh_1=\tfrac12 mv_2^2+mgh_2$.

### Ruch obrotowy
- $M=Fr\sin\alpha=Fd$; $L=I\omega$; $M=I\varepsilon$; $E_k=\tfrac12 I\omega^2$.
- Zachowanie momentu pędu: $I_1\omega_1=I_2\omega_2$.

### Ruch harmoniczny
- $x=A\sin(\omega t+\varphi_0)$; $v_{max}=A\omega$; $a_{max}=A\omega^2$.
- Sprężyna: $T=2\pi\sqrt{m/k}$; wahadło: $T=2\pi\sqrt{l/g}$.

### Stałe
- $g\approx 9{,}81\ \text{m/s}^2$ (często $\approx 10$); $G=6{,}67\cdot10^{-11}\ \text{N·m}^2/\text{kg}^2$.

### Strategia na kolokwium
1. **Przeliczaj na SI** od razu (km/h ÷ 3,6 → m/s).
2. **Rysuj siły** — diagram ciała swobodnego to połowa sukcesu w dynamice.
3. **Rozkładaj na składowe** (osobno poziom i pion, osobno wzdłuż i w poprzek równi).
4. **Najpierw szukaj zasad zachowania** (energii, pędu, momentu pędu) — często szybsze niż liczenie sił.
5. **Sprawdzaj jednostki i sens wyniku** (rząd wielkości, znak, przypadki skrajne).
6. **Pilnuj znaków** — ustal dodatni kierunek osi i trzymaj się go.
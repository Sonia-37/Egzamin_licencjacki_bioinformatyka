# Podstawy chemii — kompletne notatki na egzamin

## Spis treści

**Chemia ogólna i budowa materii**
1. [Budowa atomu](#1-budowa-atomu)
2. [Wiązania chemiczne i budowa cząsteczek](#2-wiazania-chemiczne)

**Chemia fizyczna**
3. [Termodynamika (I i II zasada)](#3-termodynamika)
4. [Równowaga chemiczna i fazowa](#4-rownowaga-chemiczna)
5. [Kinetyka chemiczna](#5-kinetyka)
6. [Roztwory elektrolitów i elektrochemia](#6-elektrochemia)
7. [Gazy, oddziaływania międzycząsteczkowe, koloidy](#7-gazy-koloidy)

**Chemia organiczna**
8. [Budowa związków organicznych i stereochemia](#8-budowa-organiczna-stereochemia)
9. [Efekty elektronowe, rezonans, aromatyczność](#9-efekty-elektronowe)
10. [Grupy funkcyjne i klasy związków](#10-grupy-funkcyjne)
11. [Typy i mechanizmy reakcji organicznych](#11-mechanizmy-reakcji)
12. [Biocząsteczki](#12-bioczasteczki)
13. [Ściąga zbiorcza](#13-sciaga)

---

## 1. Budowa atomu

### 1.1. Dualizm korpuskularno-falowy

Elektron zachowuje się **jednocześnie jak cząstka i jak fala**. Podstawowe fakty:
- **Hipoteza de Broglie'a:** każdej cząstce o pędzie $p$ odpowiada fala o długości $\lambda = \dfrac{h}{p}=\dfrac{h}{mv}$ ($h$ — stała Plancka).
- **Zasada nieoznaczoności Heisenberga:** nie można jednocześnie dokładnie znać położenia i pędu elektronu ($\Delta x\cdot\Delta p\ge\tfrac{\hbar}{2}$). Dlatego mówimy o **prawdopodobieństwie** znalezienia elektronu, a nie o orbicie.
- **Orbital** — obszar przestrzeni, w którym prawdopodobieństwo znalezienia elektronu jest duże (~90%). To "chmura", nie tor.

### 1.2. Liczby kwantowe (opisują stan elektronu)

| Liczba | Symbol | Wartości | Opis |
|---|---|---|---|
| główna | $n$ | $1,2,3,\dots$ | powłoka, energia, rozmiar |
| poboczna (azymutalna) | $l$ | $0,\dots,n-1$ | podpowłoka, kształt ($l=0$→s, 1→p, 2→d, 3→f) |
| magnetyczna | $m_l$ | $-l,\dots,0,\dots,+l$ | orientacja orbitalu w przestrzeni |
| spinowa | $m_s$ | $+\tfrac12$ lub $-\tfrac12$ | spin elektronu |

Liczba orbitali w podpowłoce: s→1, p→3, d→5, f→7 (każdy mieści 2 elektrony o przeciwnych spinach).

### 1.3. Konfiguracja elektronowa — trzy reguły

1. **Zasada (reguła) Aufbau (rozbudowy):** elektrony zajmują orbitale od najniższej energii. Kolejność: 1s, 2s, 2p, 3s, 3p, 4s, 3d, 4p, 5s, 4d... (uwaga: 4s zapełnia się przed 3d!).
2. **Zakaz Pauliego:** w atomie nie ma dwóch elektronów o identycznych czterech liczbach kwantowych (max 2 elektrony na orbital, przeciwne spiny).
3. **Reguła Hunda:** w obrębie podpowłoki elektrony najpierw zajmują **pojedynczo** wszystkie orbitale (równoległe spiny), zanim zaczną się parować.

> **Przykład.** Tlen ($Z=8$): $1s^2\,2s^2\,2p^4$. Żelazo ($Z=26$): $1s^2 2s^2 2p^6 3s^2 3p^6 4s^2 3d^6$ lub skrótowo $[\mathrm{Ar}]4s^2 3d^6$.

> **Pułapki/wyjątki:** chrom ($[\mathrm{Ar}]4s^1 3d^5$) i miedź ($[\mathrm{Ar}]4s^1 3d^{10}$) — przeskok elektronu daje stabilniejszą połówkowo/całkowicie zapełnioną podpowłokę d.

### 1.4. Powiązanie z układem okresowym

Numer okresu = najwyższe $n$. Numer grupy ≈ liczba elektronów walencyjnych. Bloki s, p, d, f odpowiadają zapełnianej podpowłoce. **Elektrony walencyjne** (na zewnętrznej powłoce) decydują o własnościach chemicznych.

---

## 2. Wiązania chemiczne

### 2.1. Reguła oktetu i typy wiązań

Atomy dążą do uzyskania **oktetu** (8 elektronów walencyjnych, konfiguracja gazu szlachetnego). Sposoby:

| Wiązanie | Mechanizm | Przykład |
|---|---|---|
| **jonowe** | przekazanie elektronów (kation + anion) | NaCl |
| **kowalencyjne (atomowe)** | wspólna para elektronowa | H₂, Cl₂ |
| **kowalencyjne spolaryzowane** | wspólna para przesunięta ku bardziej elektroujemnemu | HCl, H₂O |
| **koordynacyjne (donorowo-akceptorowe)** | para od jednego atomu | NH₄⁺ |
| **metaliczne** | "morze" elektronów swobodnych | metale |

**Elektroujemność** rośnie w prawo i w górę układu okresowego. Różnica elektroujemności decyduje o typie wiązania: mała → kowalencyjne, duża (>~1,7) → jonowe.

### 2.2. Wiązania σ i π

- **Wiązanie σ (sigma):** nakładanie orbitali "czołowe", wzdłuż osi łączącej jądra. Pojedyncze wiązanie to zawsze σ.
- **Wiązanie π (pi):** nakładanie "boczne" orbitali p. Wiązanie podwójne = 1σ + 1π; potrójne = 1σ + 2π.

Wiązania π są słabsze i bardziej reaktywne (stąd reaktywność alkenów/alkinów).

### 2.3. Hybrydyzacja orbitali

Mieszanie orbitali atomowych daje **orbitale zhybrydyzowane** o jednakowej energii i odpowiedniej geometrii (model wyjaśniający kształty cząsteczek):

| Hybrydyzacja | Geometria | Kąt | Przykład |
|---|---|---|---|
| **sp** | liniowa | 180° | BeCl₂, alkiny (C≡C), CO₂ |
| **sp²** | trygonalna płaska | 120° | BF₃, alkeny (C=C), benzen |
| **sp³** | tetraedryczna | 109,5° | CH₄, alkany, NH₃, H₂O |

> **Jak ustalić hybrydyzację atomu:** policz "kierunki" wokół atomu = wiązania σ + wolne pary elektronowe. 2 → sp, 3 → sp², 4 → sp³.
> Przykład: w metanie C ma 4 wiązania → sp³; w etenie każdy C ma 3 kierunki → sp².

### 2.4. Geometria cząsteczek (VSEPR)

Teoria **VSEPR**: pary elektronowe (wiążące i wolne) odpychają się i ustawiają możliwie daleko od siebie. **Wolne pary** zajmują więcej miejsca i ściskają kąty:
- CH₄ — 109,5° (tetraedr),
- NH₃ — ~107° (1 wolna para, piramida),
- H₂O — ~104,5° (2 wolne pary, kątowa).

### 2.5. Oddziaływania międzycząsteczkowe (słabsze niż wiązania)

| Oddziaływanie | Siła | Gdzie |
|---|---|---|
| siły dyspersyjne (Londona) | najsłabsze | wszystkie cząsteczki (chwilowe dipole) |
| dipol-dipol | średnie | cząsteczki polarne |
| **wiązanie wodorowe** | najsilniejsze z międzycząsteczkowych | H związany z F, O, N (np. woda, DNA, białka) |

> **Znaczenie biologiczne:** wiązania wodorowe trzymają podwójną helisę DNA i strukturę przestrzenną białek. To dlatego woda ma anomalnie wysoką temperaturę wrzenia.

---

## 3. Termodynamika

### 3.1. Pojęcia podstawowe

- **Układ** — fragment świata, który badamy; **otoczenie** — reszta. Układ **izolowany** (brak wymiany materii i energii), **zamknięty** (wymiana energii, nie materii), **otwarty** (jedno i drugie).
- **Parametry stanu** — wielkości opisujące stan układu: $p$ (ciśnienie), $V$ (objętość), $T$ (temperatura), $n$ (liczba moli).
- **Funkcja stanu** — zależy tylko od stanu, nie od drogi przejścia: energia wewnętrzna $U$, entalpia $H$, entropia $S$, energia swobodna $G$. **Praca i ciepło NIE są funkcjami stanu** (zależą od drogi).

### 3.2. I zasada termodynamiki (zasada zachowania energii)

$$\Delta U = Q + W,$$
gdzie $\Delta U$ — zmiana energii wewnętrznej, $Q$ — ciepło dostarczone do układu, $W$ — praca wykonana **nad** układem. (W konwencji "fizycznej" bywa $\Delta U=Q-W$ — zawsze sprawdź, co oznacza $W$!).

Energia nie powstaje ani nie znika — tylko przechodzi między ciepłem, pracą i energią wewnętrzną.

### 3.3. Entalpia i efekty cieplne reakcji

**Entalpia** $H = U + pV$. Przy stałym ciśnieniu zmiana entalpii = ciepło reakcji:
$$\Delta H = Q_p.$$

- $\Delta H < 0$ — reakcja **egzotermiczna** (wydziela ciepło),
- $\Delta H > 0$ — reakcja **endotermiczna** (pochłania ciepło).

**Standardowa entalpia tworzenia** $\Delta H_f^\circ$ — entalpia powstania 1 mola związku z pierwiastków w stanie standardowym (dla pierwiastków = 0).

### 3.4. Prawo Hessa (kluczowe do zadań!)

**Efekt cieplny reakcji zależy tylko od stanu początkowego i końcowego, nie od drogi** (bo $H$ to funkcja stanu). Stąd:
$$\Delta H_{reakcji} = \sum \Delta H_f^\circ(\text{produkty}) - \sum \Delta H_f^\circ(\text{substraty}).$$

> **Metoda:** można dodawać/odejmować równania reakcji (i ich entalpie) jak równania algebraiczne, by otrzymać równanie szukane. Odwrócenie reakcji zmienia znak $\Delta H$; pomnożenie reakcji przez współczynnik mnoży $\Delta H$.

### 3.5. II zasada termodynamiki i entropia

**Entropia** $S$ — miara nieuporządkowania (liczby mikrostanów). Jednostka J/(mol·K).

**II zasada:** w układzie izolowanym procesy samorzutne przebiegają tak, że **entropia całkowita rośnie**:
$$\Delta S_{całk} = \Delta S_{układ} + \Delta S_{otoczenie} > 0.$$

Entropia rośnie np. przy: topnieniu, parowaniu, rozpuszczaniu, wzroście liczby cząsteczek gazu.

### 3.6. Energia swobodna Gibbsa — kryterium samorzutności

**Entalpia swobodna (energia Gibbsa):**
$$G = H - TS \qquad\Longrightarrow\qquad \Delta G = \Delta H - T\Delta S.$$

**Kryterium (przy stałych $T$ i $p$):**

| $\Delta G$ | Proces |
|---|---|
| $< 0$ | **samorzutny** (egzergoniczny) |
| $= 0$ | **równowaga** |
| $> 0$ | niesamorzutny (wymaga dostarczenia energii) |

> **Analiza znaków** $\Delta H$ i $\Delta S$ (częste zadanie):
> - $\Delta H<0,\ \Delta S>0$: zawsze samorzutny,
> - $\Delta H>0,\ \Delta S<0$: nigdy samorzutny,
> - pozostałe przypadki: zależy od **temperatury** (czynnik $T\Delta S$ decyduje).

**Potencjał chemiczny** $\mu$ — energia Gibbsa przypadająca na 1 mol składnika; substancje "płyną" od wyższego do niższego potencjału chemicznego, równowaga gdy potencjały się wyrównają.

---

## 4. Równowaga chemiczna

### 4.1. Równowaga dynamiczna

W reakcji odwracalnej $aA + bB \rightleftharpoons cC + dD$ po pewnym czasie szybkość reakcji "w prawo" zrównuje się z szybkością "w lewo" — stężenia przestają się zmieniać, choć reakcje wciąż zachodzą (**równowaga dynamiczna**).

### 4.2. Prawo działania mas

**Stała równowagi:**
$$K = \frac{[C]^c [D]^d}{[A]^a [B]^b}.$$

- $K \gg 1$ — równowaga przesunięta w prawo (dużo produktów),
- $K \ll 1$ — w lewo (dużo substratów).

Ciał stałych i czystych cieczy (rozpuszczalnika) nie wpisujemy do wyrażenia na $K$. Związek z termodynamiką: $\Delta G^\circ = -RT\ln K$.

### 4.3. Reguła przekory (Le Chateliera-Brauna)

**Jeśli na układ w równowadze zadziałamy bodźcem, równowaga przesunie się tak, by ten bodziec osłabić.** Czynniki:

| Zmiana | Efekt |
|---|---|
| ↑ stężenia substratu | równowaga → w prawo (więcej produktów) |
| ↑ ciśnienia (gazy) | → w stronę **mniejszej** liczby moli gazu |
| ↑ temperatury | → w stronę reakcji **endotermicznej** |
| katalizator | **nie przesuwa** równowagi (tylko przyspiesza jej osiągnięcie!) |

> **Pułapka:** katalizator zmienia szybkość, ale **nie** wartość $K$ ani położenie równowagi.

### 4.4. Równowagi fazowe i reguła faz Gibbsa

**Faza** — jednorodny fizycznie obszar (np. lód, woda, para to 3 fazy wody). **Reguła faz Gibbsa:**
$$F = C - P + 2,$$
gdzie $F$ — liczba stopni swobody, $C$ — liczba składników, $P$ — liczba faz (2 = parametry $p$ i $T$).

### 4.5. Diagramy fazowe

Wykres $p$–$T$ pokazujący, która faza jest trwała. Charakterystyczne elementy:
- **krzywe równowagi** (topnienia, parowania, sublimacji) — wzdłuż nich współistnieją dwie fazy,
- **punkt potrójny** — współistnieją trzy fazy (jeden punkt, $F=0$),
- **punkt krytyczny** — koniec krzywej parowania; powyżej istnieje faza nadkrytyczna.

> **Anomalia wody:** krzywa topnienia wody ma **ujemne** nachylenie (lód pływa — lód jest mniej gęsty od wody). Większość substancji ma nachylenie dodatnie.

---

## 5. Kinetyka

### 5.1. Szybkość reakcji

**Szybkość reakcji** = zmiana stężenia w czasie: $v = \dfrac{\Delta[\,]}{\Delta t}$ [mol/(dm³·s)]. Maleje w czasie (substraty się wyczerpują).

### 5.2. Równanie kinetyczne i rząd reakcji

$$v = k\,[A]^m [B]^n,$$
gdzie $k$ — stała szybkości, a wykładniki $m, n$ to **rzędy** względem reagentów. **Rząd całkowity** = $m+n$. Rzędy wyznacza się **doświadczalnie** (nie ze współczynników stechiometrycznych!).

| Rząd | Równanie zaniku | Zależność $[A]$ od $t$ | Czas połowicznego rozkładu $t_{1/2}$ |
|---|---|---|---|
| 0 | $v=k$ | $[A]=[A]_0 - kt$ (liniowa) | $\dfrac{[A]_0}{2k}$ (zależy od $[A]_0$) |
| 1 | $v=k[A]$ | $\ln[A]=\ln[A]_0 - kt$ | $\dfrac{\ln 2}{k}$ (**stały!**) |
| 2 | $v=k[A]^2$ | $\dfrac{1}{[A]}=\dfrac{1}{[A]_0}+kt$ | $\dfrac{1}{k[A]_0}$ |

> **Cecha rozpoznawcza I rzędu:** stały czas połowicznego rozkładu (jak rozpad promieniotwórczy). Wykres $\ln[A]$ od $t$ to linia prosta.

### 5.3. Teoria zderzeń aktywnych

Reakcja zachodzi, gdy cząsteczki **zderzą się** z wystarczającą energią (≥ energia aktywacji $E_a$) i **odpowiednią orientacją**. Stąd nie każde zderzenie prowadzi do reakcji.

**Energia aktywacji** $E_a$ — bariera energetyczna, którą trzeba pokonać. **Kompleks aktywny (stan przejściowy)** to szczyt bariery.

### 5.4. Równanie Arrheniusa

$$k = A\,e^{-E_a/(RT)},$$
gdzie $A$ — czynnik przedwykładniczy, $R$ — stała gazowa, $T$ — temperatura. Wnioski:
- ↑ temperatura → ↑ $k$ → szybsza reakcja (reguła praktyczna: +10 K ≈ 2–4× szybciej),
- ↑ $E_a$ → wolniejsza reakcja,
- **katalizator obniża $E_a$** (otwiera łatwiejszą drogę reakcji), nie zmieniając $\Delta H$ ani położenia równowagi.

Postać logarytmiczna (do wyznaczania $E_a$ z wykresu): $\ln k = \ln A - \dfrac{E_a}{R}\cdot\dfrac{1}{T}$ — prosta o nachyleniu $-E_a/R$.

---

## 6. Elektrochemia

### 6.1. Elektrolity i dysocjacja

**Elektrolit** — substancja przewodząca prąd po rozpuszczeniu (rozpada się na jony). **Dysocjacja:** np. $\mathrm{NaCl}\to\mathrm{Na^+}+\mathrm{Cl^-}$. **Stopień dysocjacji** $\alpha$ — ułamek cząsteczek zdysocjowanych (mocne elektrolity α≈1, słabe α≪1).

### 6.2. Równowagi w roztworach — pH

**Iloczyn jonowy wody:** $K_w=[\mathrm{H^+}][\mathrm{OH^-}]=10^{-14}$ (w 25 °C).

$$\mathrm{pH}=-\log[\mathrm{H^+}],\qquad \mathrm{pOH}=-\log[\mathrm{OH^-}],\qquad \mathrm{pH+pOH}=14.$$

- pH < 7 kwaśny, = 7 obojętny, > 7 zasadowy.
- **Mocne kwasy/zasady** — pełna dysocjacja (pH liczymy wprost ze stężenia). **Słabe** — używamy stałej $K_a$/$K_b$.

> **Przykład.** 0,01 M HCl (mocny kwas): $[\mathrm{H^+}]=10^{-2}$ → pH = 2.

### 6.3. Ogniwa galwaniczne

**Ogniwo galwaniczne** zamienia energię reakcji **redoks** na energię elektryczną (samorzutnie, $\Delta G<0$).
- **Anoda (−)** — zachodzi **utlenianie** (oddawanie elektronów),
- **Katoda (+)** — zachodzi **redukcja** (przyjmowanie elektronów),
- elektrony płyną przez przewodnik od anody do katody; klucz elektrolityczny zamyka obwód.

**Siła elektromotoryczna (SEM):** $E_{ogniwa}=E_{katody}-E_{anody}$ (z potencjałów standardowych). $E>0$ oznacza reakcję samorzutną; związek: $\Delta G = -nFE$.

> **Mnemotechnika:** anoda = **u**tlenianie (oba z grupy "oddawanie"), katoda = **re**dukcja.

### 6.4. Elektroliza i prawa Faradaya

**Elektroliza** — wymuszenie reakcji **niesamorzutnej** prądem z zewnątrz (odwrotność ogniwa). Na katodzie redukcja, na anodzie utlenianie (ale teraz katoda jest „−", anoda „+").

**I prawo Faradaya:** masa wydzielona na elektrodzie jest proporcjonalna do ładunku:
$$m = \frac{M}{nF}\,q = \frac{M\,I\,t}{nF},$$
gdzie $M$ — masa molowa, $n$ — liczba elektronów, $F\approx 96500$ C/mol, $I$ — prąd, $t$ — czas.

**II prawo Faradaya:** przy tym samym ładunku masy różnych substancji są proporcjonalne do ich równoważników chemicznych ($M/n$).

> **Kolejność rozładowania (wodne roztwory):** na katodzie łatwiej redukują się kationy metali mniej aktywnych (i H⁺); kationy metali aktywnych (Na, K, Ca) "ustępują" wydzielaniu wodoru.

---

## 7. Gazy, koloidy

### 7.1. Gaz doskonały — równanie stanu

Model: cząsteczki punktowe, bez oddziaływań, zderzenia sprężyste. **Równanie stanu gazu doskonałego (Clapeyrona):**
$$pV = nRT,$$
gdzie $R=8{,}314\ \text{J/(mol·K)}$. Wynikają z niego prawa szczegółowe: Boyle'a ($pV=$const przy $T$=const), Charlesa, Gay-Lussaca, Avogadra (równe objętości gazów w tych samych warunkach mają tyle samo cząsteczek).

> **Warunki normalne** (0 °C, 1013 hPa): 1 mol gazu zajmuje **22,4 dm³**.

### 7.2. Interpretacja temperatury i rozkład prędkości

Temperatura to miara **średniej energii kinetycznej** cząsteczek:
$$\bar{E}_k = \frac{3}{2}kT \quad(k\text{ — stała Boltzmanna}).$$
Cząsteczki mają różne prędkości — opisuje je **rozkład Maxwella-Boltzmanna** (krzywa z maksimum). Wyższa $T$ → krzywa przesunięta ku wyższym prędkościom i bardziej "rozmyta".

### 7.3. Gazy rzeczywiste — równanie Van der Waalsa

Realne gazy odbiegają od modelu (cząsteczki mają objętość i oddziałują). Poprawka Van der Waalsa:
$$\left(p + \frac{a n^2}{V^2}\right)(V - nb) = nRT,$$
gdzie $a$ — poprawka na **przyciąganie** międzycząsteczkowe, $b$ — na **objętość własną** cząsteczek. Odstępstwa największe przy wysokim ciśnieniu i niskiej temperaturze.

### 7.4. Napięcie powierzchniowe i substancje powierzchniowo czynne

**Napięcie powierzchniowe** — cząsteczki na powierzchni cieczy są przyciągane do wnętrza (niezrównoważone siły), powierzchnia "kurczy się" jak błona. Stąd krople są kuliste.

**Substancje powierzchniowo czynne (surfaktanty)** — mają część **hydrofilową** (lubiącą wodę) i **hydrofobową** (tłuszczolubną); gromadzą się na powierzchni, obniżają napięcie powierzchniowe. To podstawa działania mydeł i detergentów (tworzą **micele** otaczające tłuszcz). Biologicznie: budują błony komórkowe (fosfolipidy).

### 7.5. Układy koloidalne

**Koloid** — układ z cząstkami rozproszonymi o rozmiarach 1–1000 nm (między roztworem właściwym a zawiesiną). Klasyfikacja wg stanu skupienia fazy rozproszonej i ośrodka:

| Typ | Przykład |
|---|---|
| aerozol (ciecz/gaz) | mgła |
| piana (gaz/ciecz) | piana mydlana |
| emulsja (ciecz/ciecz) | mleko |
| zol (ciało stałe/ciecz) | farby |
| żel | galaretka |

Cecha rozpoznawcza: **efekt Tyndalla** — koloid rozprasza światło (smuga światła widoczna), roztwór właściwy nie.

---

## 8. Budowa organiczna, stereochemia

### 8.1. Trzy poziomy opisu cząsteczki

- **Konstytucja** — które atomy są z którymi połączone (kolejność wiązań). Różną konstytucję mają **izomery konstytucyjne** (strukturalne), np. butan i izobutan.
- **Konfiguracja** — przestrzenne rozmieszczenie atomów, którego **nie da się zmienić bez zerwania wiązań** (np. cis/trans, R/S).
- **Konformacja** — chwilowy układ przestrzenny powstający przez **obrót wokół wiązań pojedynczych** (bez zrywania), np. konformacja naprzeciwległa i naprzemianległa etanu.

### 8.2. Izomeria — przegląd

```
Izomery (ten sam wzór sumaryczny)
├── konstytucyjne (różne połączenia atomów)
└── stereoizomery (te same połączenia, różne ułożenie w przestrzeni)
    ├── konfiguracyjne
    │   ├── enancjomery (lustrzane odbicia, nienakładalne)
    │   └── diastereoizomery (nie-lustrzane; w tym cis/trans)
    └── konformacyjne (obrót wokół wiązań)
```

### 8.3. Chiralność, enancjomery, diastereoizomery

- **Centrum stereogeniczne (asymetryczny atom C)** — atom węgla z **czterema różnymi** podstawnikami.
- **Cząsteczka chiralna** — nienakładalna na swoje lustrzane odbicie (jak lewa i prawa dłoń).
- **Enancjomery** — para lustrzanych odbić; mają **identyczne** właściwości fizyczne (temp. topnienia itp.), różnią się tylko skręcaniem płaszczyzny światła spolaryzowanego (**aktywność optyczna**) i reakcjami z innymi cząsteczkami chiralnymi.
- **Diastereoizomery** — stereoizomery, które **nie** są lustrzanymi odbiciami; mają **różne** właściwości fizyczne. Należą tu izomery **cis/trans** (geometryczne) przy wiązaniu podwójnym lub pierścieniu.
- **Mieszanina racemiczna** — 50/50 enancjomerów, optycznie nieczynna.

> **Znaczenie biologiczne:** organizmy rozróżniają enancjomery (np. tylko L-aminokwasy i D-cukry są "biologiczne"). Lek może być leczniczy w jednej formie, a szkodliwy w drugiej (tragedia talidomidu).

### 8.4. Notacje wzorów organicznych

- **sumaryczny** (C₂H₆O), **strukturalny** (wszystkie wiązania), **półstrukturalny** (CH₃CH₂OH), **szkieletowy/kreskowy** (linie = wiązania C-C, wierzchołki = atomy C, H przy C pomijane).
- Wzór szkieletowy to standard w chemii organicznej — szybki i czytelny.

---

## 9. Efekty elektronowe

### 9.1. Rezonans (mezomeria)

Gdy struktury cząsteczki nie da się opisać jednym wzorem, rysujemy kilka **struktur rezonansowych** (granicznych) połączonych strzałką ↔. Rzeczywista cząsteczka to ich "hybryda" — elektrony są **zdelokalizowane**.

> **Uwaga:** struktury rezonansowe **nie** są realnymi, przeskakującymi formami — to nasz sposób opisu jednej, uśrednionej struktury. Delokalizacja **stabilizuje** cząsteczkę/jon.

### 9.2. Efekt indukcyjny i mezomeryczny (rezonansowy)

- **Efekt indukcyjny (I)** — przesunięcie elektronów **przez wiązania σ** wskutek różnic elektroujemności; zanika z odległością. Grupy elektronoakceptorowe (−I): −F, −Cl, −NO₂; elektronodonorowe (+I): grupy alkilowe.
- **Efekt mezomeryczny (M, rezonansowy)** — przesunięcie elektronów **przez układ π** (sprzężone wiązania); przenosi się na duże odległości. Grupy −M (akceptorowe): −NO₂, −C=O; +M (donorowe): −OH, −NH₂, −OR.

### 9.3. Wpływ na kwasowość i zasadowość

Stabilizacja powstającego jonu decyduje o kwasowości/zasadowości:
- Grupy **elektronoakceptorowe** stabilizują **anion** (sprzężoną zasadę) → **zwiększają kwasowość**. Dlatego kwas trichlorooctowy jest mocniejszy od octowego.
- Stabilizacja rezonansowa anionu (np. karboksylanowego, fenolanowego) tłumaczy, czemu kwasy karboksylowe i fenole są kwaśne, a alkohole praktycznie nie.

### 9.4. Aromatyczność

Związek jest **aromatyczny**, gdy spełnia warunki:
1. cykliczny i **płaski**,
2. pełne **sprzężenie** (układ ciągły orbitali p, każdy atom pierścienia),
3. **reguła Hückla:** $4n+2$ elektronów π ($n=0,1,2,\dots$ → 2, 6, 10... elektronów).

Benzen (6 elektronów π) to wzorzec. Aromatyczność daje dużą **stabilność** i specyficzną reaktywność (substytucja zamiast addycji).

---

## 10. Grupy funkcyjne

### 10.1. Najważniejsze grupy funkcyjne (rozpoznawanie — U1)

| Klasa | Grupa funkcyjna | Wzór ogólny | Przyrostek/przedrostek |
|---|---|---|---|
| alkany | (brak, tylko C–C, C–H) | $C_nH_{2n+2}$ | -an |
| alkeny | C=C | $C_nH_{2n}$ | -en |
| alkiny | C≡C | $C_nH_{2n-2}$ | -yn |
| chlorowcopochodne | −X (F, Cl, Br, I) | R−X | chloro-, bromo- |
| alkohole | −OH | R−OH | -ol |
| etery | −O− | R−O−R′ | -oksy- |
| aldehydy | −CHO | R−CHO | -al |
| ketony | −CO− (wewnątrz) | R−CO−R′ | -on |
| kwasy karboksylowe | −COOH | R−COOH | kwas ...owy |
| estry | −COO− | R−COO−R′ | -an ...lu |
| aminy | −NH₂ | R−NH₂ | -amina |
| amidy | −CONH₂ | R−CONH₂ | -amid |

### 10.2. Zasady nazewnictwa IUPAC (skrót)

1. Znajdź **najdłuższy łańcuch** zawierający grupę główną → rdzeń nazwy.
2. Ponumeruj tak, by grupa funkcyjna / podstawniki miały **najniższe** lokanty.
3. Dodaj podstawniki (przedrostki alfabetycznie) z numerami i przyrostek grupy głównej.

> **Przykład.** $CH_3-CH(OH)-CH_3$ → propan-2-ol.

### 10.3. Otrzymywanie i reaktywność (skrótowo)

- **Alkany:** mało reaktywne; substytucja rodnikowa z halogenami (światło).
- **Alkeny/alkiny:** reaktywne wiązanie π → addycja (H₂, HX, H₂O, X₂); reguła Markownikowa (wodór do węgla z większą liczbą wodorów).
- **Alkohole:** utlenianie (I-rzęd → aldehyd → kwas; II-rzęd → keton; III-rzęd odporny), reakcje z kwasami → estry.
- **Aldehydy/ketony:** addycja nukleofilowa do C=O; aldehydy łatwo się utleniają (próba Tollensa, Trommera) — ketony nie.
- **Kwasy karboksylowe:** kwasowe (sole), tworzą estry (estryfikacja), amidy.
- **Aminy:** zasadowe (wolna para na N), tworzą sole z kwasami.
- **Areny (benzen):** substytucja elektrofilowa aromatyczna (nitrowanie, sulfonowanie, halogenowanie, alkilowanie).

### 10.4. Polimery

**Polimer** — wielka cząsteczka z powtarzających się merów. Powstają przez:
- **polimeryzację** (addycja monomerów z wiązaniem podwójnym, np. polietylen z etenu),
- **polikondensację** (łączenie z wydzieleniem małej cząsteczki, np. wody — poliestry, poliamidy/nylon).

---

## 11. Mechanizmy reakcji

### 11.1. Cztery główne typy reakcji organicznych

| Typ | Co się dzieje | Przykład |
|---|---|---|
| **substytucja** | podstawnik zastępuje inny | alkan + Cl₂ → chloroalkan |
| **addycja** | dwie cząsteczki łączą się w jedną (rozpada się wiązanie π) | alken + H₂ → alkan |
| **eliminacja** | odejście fragmentu, powstaje wiązanie π | alkohol → alken + H₂O |
| **redoks** | zmiana stopni utlenienia | utlenianie alkoholu do aldehydu |

> Addycja i eliminacja to procesy **przeciwne**. Stopień utlenienia węgla rośnie w szeregu: alkan → alkohol → aldehyd → kwas.

### 11.2. Rodzaje czynników i rozpadu wiązań

- **Rozpad homolityczny** → dwa **rodniki** (każdy bierze 1 elektron); inicjowany światłem/temperaturą.
- **Rozpad heterolityczny** → **jony** (jeden atom bierze oba elektrony): powstaje kation lub anion.
- **Elektrofil** (E⁺) — "lubi elektrony", atakuje miejsca bogate w elektrony.
- **Nukleofil** (Nu⁻) — "lubi jądra", ma wolną parę, atakuje miejsca ubogie w elektrony (dodatnie).

### 11.3. Główne mechanizmy

**Substytucja rodnikowa (SR)** — alkany + halogeny, światło. Etapy: inicjacja (powstają rodniki), propagacja (łańcuch), terminacja.

**Substytucja nukleofilowa:**
- **SN2** — jednoetapowa, atak nukleofila "od tyłu" → **inwersja** konfiguracji (parasol na wietrze); szybkość zależy od stężenia obu reagentów ($v=k[\text{substrat}][\text{Nu}]$); sprzyjają jej substraty I-rzędowe.
- **SN1** — dwuetapowa przez **karbokation** (najpierw odejście grupy, potem atak); $v=k[\text{substrat}]$; sprzyjają jej substraty III-rzędowe (stabilny karbokation); daje **racemizację**.

**Eliminacja (E1, E2)** — analogicznie; konkuruje z substytucją. E2 jednoetapowa, E1 przez karbokation. Reguła Zajcewa: powstaje głównie alken bardziej podstawiony (stabilniejszy).

**Addycja elektrofilowa** — do alkenów/alkinów; elektrofil atakuje wiązanie π (np. addycja HBr — reguła Markownikowa).

**Substytucja elektrofilowa aromatyczna** — w benzenie; zachowuje aromatyczność (nitrowanie, halogenowanie itd.). Podstawniki kierują kolejny podstawnik w pozycje orto/para (donory) lub meta (akceptory).

**Reakcja uzgodniona (pericykliczna)** — wiązania zrywają się i tworzą **jednocześnie** w cyklicznym stanie przejściowym (np. Dielsa-Aldera), bez jonów ani rodników.

---

## 12. Biocząsteczki

### 12.1. Cukry (sacharydy)

Polihydroksyaldehydy/ketony. Podział: **monosacharydy** (glukoza, fruktoza — C₆H₁₂O₆), **disacharydy** (sacharoza, laktoza — łączone wiązaniem glikozydowym), **polisacharydy** (skrobia, glikogen, celuloza). W roztworze cukry tworzą formy pierścieniowe (piranozy/furanozy). Naturalne cukry to szereg **D**.

### 12.2. Lipidy

Związki hydrofobowe. **Tłuszcze** = estry glicerolu i kwasów tłuszczowych (nasycone — stałe; nienasycone — ciekłe). **Fosfolipidy** (część polarna + dwa "ogony") budują **dwuwarstwę** błon komórkowych — fundament biologii komórki.

### 12.3. Aminokwasy i peptydy

**Aminokwas** ma grupę aminową (−NH₂) i karboksylową (−COOH) przy tym samym węglu (α). Jest **amfoteryczny** (reaguje z kwasami i zasadami); w roztworze istnieje jako **jon obojnaczy (zwitterion)**. Białkowych aminokwasów jest 20, wszystkie szeregu **L**.

**Wiązanie peptydowe** — amidowe (−CO−NH−) między grupą −COOH jednego aminokwasu a −NH₂ drugiego, z wydzieleniem wody. Łańcuch aminokwasów = **peptyd/białko**. Poziomy struktury białka: I-rzędowa (sekwencja), II (helisa α, harmonijka β — wiązania wodorowe), III (przestrzenna), IV (kilka podjednostek).

### 12.4. Kwasy nukleinowe

**Nukleotyd** = zasada azotowa + cukier (deoksyryboza/ryboza) + reszta fosforanowa. **DNA** — podwójna helisa, zasady: A, T, G, C (komplementarność A–T, G–C przez wiązania wodorowe). **RNA** — jednoniciowy, U zamiast T, ryboza zamiast deoksyrybozy. Przechowują i przekazują informację genetyczną.

---

## 13. Ściąga

### Budowa atomu i wiązania
- Liczby kwantowe: $n$ (powłoka), $l$ (0..n−1, s/p/d/f), $m_l$ (−l..+l), $m_s$ (±½).
- Reguły: Aufbau (od najniższej energii, 4s przed 3d), Pauli (max 2 e/orbital), Hund (najpierw pojedynczo).
- Hybrydyzacja: sp (180°, liniowa), sp² (120°, płaska), sp³ (109,5°, tetraedr).
- Wiązanie wodorowe: H z F/O/N — najsilniejsze międzycząsteczkowe.

### Termodynamika
- I zasada: $\Delta U = Q + W$. Entalpia $\Delta H=Q_p$ ($<0$ egzo, $>0$ endo).
- Prawo Hessa: $\Delta H=\sum H_f(\text{prod})-\sum H_f(\text{subs})$.
- Gibbs: $\Delta G=\Delta H - T\Delta S$; $\Delta G<0$ samorzutny, $=0$ równowaga.

### Równowaga i kinetyka
- $K=\dfrac{[\text{prod}]^{...}}{[\text{subs}]^{...}}$; Le Chatelier (układ osłabia bodziec); katalizator NIE zmienia $K$.
- Reguła faz: $F=C-P+2$.
- $v=k[A]^m[B]^n$; I rząd ma stały $t_{1/2}=\ln2/k$.
- Arrhenius: $k=A\,e^{-E_a/RT}$; katalizator obniża $E_a$.

### Elektrochemia
- pH$=-\log[\mathrm H^+]$; pH+pOH=14; $K_w=10^{-14}$.
- Ogniwo: anoda(−) utlenianie, katoda(+) redukcja; $E=E_{kat}-E_{an}$.
- Faraday: $m=\dfrac{MIt}{nF}$, $F\approx96500$ C/mol.

### Gazy
- $pV=nRT$, $R=8{,}314$ J/(mol·K); 1 mol w warunkach normalnych = 22,4 dm³.
- $T$ ∝ średnia energia kinetyczna; Van der Waalsa — poprawki $a$ (przyciąganie), $b$ (objętość).

### Organiczna
- Konstytucja / konfiguracja / konformacja.
- Enancjomery (lustrzane, te same wł. fizyczne) vs diastereoizomery (różne wł.).
- Aromatyczność: cykliczny, płaski, sprzężony, $4n+2$ elektronów π (Hückel).
- Reakcje: substytucja, addycja, eliminacja, redoks; mechanizmy SN1/SN2, E1/E2, rodnikowy, elektrofilowy, nukleofilowy, uzgodniony.
- Wiązanie peptydowe = amidowe; DNA: A–T, G–C.

### Strategia na egzamin
1. **Konfiguracje elektronowe** — ćwicz wraz z wyjątkami (Cr, Cu).
2. **Zadania z prawa Hessa i Gibbsa** — pilnuj znaków $\Delta H$, $\Delta S$.
3. **pH i prawa Faradaya** — pewne punkty rachunkowe, znaj wzory na pamięć.
4. **Rozpoznawanie grup funkcyjnych** ze wzoru — kluczowe dla części organicznej.
5. **Stereochemia** — odróżniaj typy izomerii; rozpoznawaj centrum chiralne (4 różne podstawniki).
6. **Mechanizmy** — kojarz typ substratu z mechanizmem (III-rzęd → SN1/E1, I-rzęd → SN2/E2).
7. **Le Chatelier i Arrhenius** — pamiętaj, że katalizator nie rusza równowagi, tylko ją przyspiesza.
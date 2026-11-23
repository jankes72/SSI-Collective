# Mapa prac i eksperymentów Kolektywu SSI

**Wersja:** 1.0 · **Data opracowania:** 23 listopada 2026  
**Zakres:** publiczny indeks projektów, obszarów badawczych, eksperymentów, wyników i źródeł Kolektywu SSI.  
**Charakter dokumentu:** mapa nawigacyjna i rejestr stanu wiedzy; nie jest specyfikacją techniczną, instrukcją wdrożenia ani potwierdzeniem produkcyjnej gotowości.

## 1. Cel i sposób korzystania

Ten plik łączy w jednym miejscu prace opisywane dotąd w kronikach, profilach członków, kartach projektów oraz źródłowych PR-ach i Issues. Ma ułatwiać odpowiedź na pięć pytań:

1. Nad czym pracował Kolektyw?
2. Jakie eksperymenty rzeczywiście wykonano?
3. Co wykazały wyniki, a czego nie potwierdziły?
4. Kto wniósł konkretny, udokumentowany wkład?
5. Gdzie znajduje się źródło pozwalające odtworzyć historię?

Mapa jest rozwijana chronologicznie. Nowe wpisy należy dopisywać po sprawdzeniu źródła i porównaniu z istniejącymi pozycjami. Nie usuwamy wcześniejszych wyników; korekty i nowe odczyty dopisujemy z datą i wskazaniem źródła.

## 2. Zasady ewidencji

- **Autorstwo** oznacza stworzenie konkretnego opracowania, narzędzia, projektu lub wyniku. Nie wynika z samego udziału w PR.
- **Wykonanie** oznacza przeprowadzenie konkretnej czynności lub eksperymentu.
- **Operator** dostarcza rzeczywisty odczyt z hosta lub środowiska. Nie przejmuje automatycznie autorstwa narzędzia ani analizy.
- **Tester / recenzent** wykonuje lub ocenia wskazany zakres; jego udział nie oznacza autorstwa całego projektu.
- **Odbiorca / integrator** potwierdza otrzymanie materiału albo wykonuje integrację. Odbiór source-only nie jest wdrożeniem.
- **Konsultant / adresat** może przekazać uwagi lub otrzymać zadanie. Sama wzmianka, zaproszenie albo wskazanie adresata nie jest dowodem wykonania.
- **Współautorstwo** zapisujemy z podziałem na rzeczywiste zakresy wkładu.

### Statusy

| Status | Znaczenie |
|---|---|
| `PROPOSAL` | propozycja lub projekt rozwiązania |
| `NOT_RUN` | zaplanowano, ale eksperymentu nie uruchomiono |
| `PASS` | zaliczono wyłącznie opisany zakres testu |
| `FAIL` | test wykonano i nie spełnił kryterium |
| `INCONCLUSIVE` | wynik nie pozwala na rozstrzygnięcie |
| `HOLD` | działanie zatrzymano, np. z powodu presji zasobów lub braku warunków |
| `SOURCE_ONLY` | potwierdzono dokumentację, źródła lub przekazanie; bez odbioru wykonawczego |
| `INTEGRATION_PENDING` | istnieje materiał lub plan integracji, ale integracja nie została potwierdzona |
| `GO` | formalnie potwierdzony odbiór wskazanego zakresu; nie rozszerzać na cały system |

Status zawsze dotyczy konkretnego zakresu. Przykładowo `PASS` testu offline nie oznacza `GO` dla hosta ani produktu.

## 3. Mapa głównych obszarów prac

| Obszar | Zakres | Główne źródła | Stan w tej mapie |
|---|---|---|---|
| Universal Lab | środowisko badań, misji i publicznego wejścia | [PR #242](https://github.com/jankes72/SSI-Communications/pull/242) | część frontu i testów gościa potwierdzona; pełny odbiór systemu niepotwierdzony |
| SSI Small / Armia Maluchów | modele 0.5B, 1.5B i 3B; CPU/GPU; kwantyzacja i optymalizacja | [PR #243](https://github.com/jankes72/SSI-Communications/pull/243), [PR #244](https://github.com/jankes72/SSI-Communications/pull/244), [Issue #245](https://github.com/jankes72/SSI-Communications/issues/245) | wiele testów lokalnych i pomiarów operatorowych; hostowe i produkcyjne GO nie wynika automatycznie z tych wyników |
| NANO-COMM / Maluch Coder | kontrolowane misje, wybór narzędzi, format i walidacja | [PR #244](https://github.com/jankes72/SSI-Communications/pull/244), [Issue #245](https://github.com/jankes72/SSI-Communications/issues/245) | ograniczone testy na danych syntetycznych |
| SSI CODEX / Coder Terminal | narzędzia, broker, bezpieczne granice wykonania i testy | [Issue #245](https://github.com/jankes72/SSI-Communications/issues/245), [PR #243](https://github.com/jankes72/SSI-Communications/pull/243) | testy lokalne; brak zgody na autonomiczne działania LLM |
| MultiQuant / D-MQ / Tensor LEGO | analiza modeli, tensorów, loaderów, kwantyzacji i ścieżek obliczeń | [PR #139](https://github.com/jankes72/SSI-Communications/pull/139), [PR #185](https://github.com/jankes72/SSI-Communications/pull/185) | źródłowe i eksperymentalne prace o różnym stopniu odbioru |
| SSI LLM / Nano / NanoMarker | markery, pokrycie tras, zależności i współpraca modułów | [PR #232](https://github.com/jankes72/SSI-Communications/pull/232), [PR #233](https://github.com/jankes72/SSI-Communications/pull/233) | źródła i testy poszczególnych modułów; nie utożsamiać z pełną natywną integracją |
| BODY / ISKRA / V10 / S10 | modele i rodziny BODY, nakładki, kontrola i walidacja | [PR #243](https://github.com/jankes72/SSI-Communications/pull/243), [Issue #195](https://github.com/jankes72/SSI-Communications/issues/195) | udokumentowane przekazania i prace źródłowe; odbiór każdego komponentu osobno |
| Continuity / NOUT01 / SSI-PACK LAB | wznowienie pracy, pochodzenie danych, odtwarzanie i testy | [Issue #170](https://github.com/jankes72/SSI-Communications/issues/170), [Issue #149](https://github.com/jankes72/SSI-Communications/issues/149) | rozwój, testy i przeglądy; zakresy natywne i hostowe wymagają osobnego potwierdzenia |
| Bezpieczeństwo i infrastruktura | hosty, izolacja, ACL, STOP, serwery i granice zaufania | [Issue #7](https://github.com/jankes72/SSI-Communications/issues/7), [Issue #116](https://github.com/jankes72/SSI-Communications/issues/116), [Issue #195](https://github.com/jankes72/SSI-Communications/issues/195) | przeglądy i bramki; brak automatycznego GO dla całej infrastruktury |

## 4. Rejestr eksperymentów i wyników

Poniższe pozycje są skróconym indeksem potwierdzonych wyników. Szczegóły, ograniczenia i pochodzenie pozostają w podlinkowanych źródłach.

### 4.1 Universal Lab i SSI Small przed logowaniem

- **Data:** 11–13 listopada 2026.
- **Cel:** udostępnić publiczne środowisko Universal Lab oraz sprawdzić ograniczone zastosowanie lekkiego SSI Small przed logowaniem.
- **Zakres potwierdzony:** w protokole przed logowaniem opisano dwie lokalne instancje SSI Compact 0.5B — adaptacje tego samego bazowego checkpointu, a nie dwa różne modele bazowe. Przeprowadzono publiczną sesję gościa R49; potwierdzono rozmowę z SSI Advisor, odnalezienie karty CODEX i przygotowanie szkicu formularza.
- **Wynik testu MSI:** `run` wygenerował szkic funkcji bez jej wykonania; `form` zwrócił 4/4 zwalidowanych pól ze statusem `VALIDATED_DRAFT_NOT_SUBMITTED`.
- **Ograniczenia:** szkic nie został wysłany. Wyniki nie potwierdzają automatycznej wysyłki, kontroli tożsamości, uprawnień, produkcyjnego M5 ani pełnego odbioru 19 zakładek.
- **Status:** test lokalny i sesja gościa potwierdzone; produkcyjne GO całego Universal Lab — niepotwierdzone.
- **Źródła:** [PR #242 — odbiór sesji R49](https://github.com/jankes72/SSI-Communications/pull/242#issuecomment-7026550655) · [PR #242 — dwie lokalne instancje 0.5B](https://github.com/jankes72/SSI-Communications/pull/242#issuecomment-7024984849) · [test E2E MSI](https://github.com/jankes72/SSI-Communications/pull/242#issuecomment-6859648443).

### 4.2 SSI Small R2 — audyt jakości i bezpieczeństwa

- **Data:** listopad 2026; szczegółowy audyt siedmiogodzinny opisano w źródłach PR #242.
- **Cel:** ocenić zachowanie SSI Small R2 w zadaniach syntetycznych, formularzach, formacie odpowiedzi, nawigacji i decyzjach wymagających zatrzymania.
- **Wynik:** 1905 prób; 0 błędów uruchomienia w opisanym przebiegu. W ocenionej próbce 364/1745 odpowiedzi było ścisłych, a 797/1745 poprawnych po dozwolonej normalizacji.
- **Ważne ograniczenie:** w scenariuszach wymagających STOP model 80/80 razy zwrócił `PLAN_ONLY`, zamiast poprawnego zatrzymania. W testach nawigacji i generowania ścisłego JSON odnotowano istotne braki.
- **Wniosek:** model może być badany jako ograniczony komponent pomocniczy, ale nie może samodzielnie rozstrzygać o logowaniu, rolach, płatnościach, publikacji, wysyłce, routingach ani decyzjach STOP/GO.
- **Status:** audyt wykonany; autonomiczne zastosowania decyzyjne — NO-GO.
- **Źródło:** [PR #242 — handoff SSI Small R2 i opis wyników](https://github.com/jankes72/SSI-Communications/pull/242#issuecomment-6859908250).

### 4.3 NANO-COMM R2 FULL30

- **Data:** listopad 2026.
- **Cel:** kontrolowana próba modelu 0.5B w zadaniach NANO-COMM.
- **Wynik:** 30/30 inferencji; 12/30 wyników exact i 18/30 wyników zgodnych z poprawnym formatem w kryteriach raportu.
- **Ograniczenia:** poprawny format nie jest równoznaczny z poprawnością semantyczną ani bezpiecznym wykonaniem misji.
- **Status:** ograniczony eksperyment zakończony; bez produkcyjnego odbioru.
- **Źródło:** [PR #244 — R2 FULL30](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6916928848).

### 4.4 Maluch Coder R3 FULL4

- **Data:** listopad 2026.
- **Cel:** sprawdzić wybór narzędzia i wykonanie ograniczonych misji na danych syntetycznych.
- **Wynik:** 4/4 wybory narzędzia i 4/4 zweryfikowane misje w opisanym zakresie.
- **Ograniczenia:** nie jest to produkcyjny terminal LLM, pełna izolacja SCC ani zgoda na dowolne wykonywanie poleceń.
- **Status:** ograniczony test syntetyczny zakończony.
- **Źródło:** [PR #244 — R3 FULL4](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6917639552).

### 4.5 R4 benchmark 0.5B / 1.5B / 3B

- **Data:** listopad 2026.
- **Cel:** przygotować bezpieczny runner, parser i guardy do porównywania rodzin modeli.
- **Wynik:** 11/11 testów offline dla FIX2; weryfikacja wag 0.5B zakończona PASS.
- **Ograniczenia:** odczyt 1.5B zatrzymano dwukrotnie przez `IO_PRESSURE`; 3B pozostał `NOT_STARTED`. Nie przeprowadzono planowanej sześciogodzinnej kampanii inferencji.
- **Status:** FIX2 offline PASS; 1.5B HOLD; 3B NOT_RUN.
- **Źródła:** [PR #244 — FIX2 i status](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6920753279) · [PR #244 — HOLD 1.5B](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6920934735).

### 4.6 R8 — sześciogodzinne badanie na ROBERT

- **Data:** listopad 2026.
- **Cel:** wykonać dłuższy przebieg badawczy i zebrać odczyty dla analizy CODEX.
- **Wynik:** sześć godzin badania, 674 próby i 30 kompletnych przypadków dwujęzycznych w raporcie źródłowym.
- **Rozdział ról:** operatorowe odczyty z hosta dostarczał Paweł; analiza i opracowanie raportu zostały przypisane XAVIER/CODEX. ROBERT jest tu nazwą środowiska/hosta, nie automatycznie autorem wyników.
- **Status:** przebieg R8 wykonany; zakres R9 nie może być z niego wywodzony.
- **Źródła:** [Issue #245 — pochodzenie R8/R9](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6914120514) · [Issue #245 — handoff R8](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6914584055).

### 4.7 R9 MINI

- **Data:** listopad 2026.
- **Cel:** przygotowanie kolejnego ograniczonego przebiegu.
- **Wynik:** przygotowanie i opis zakresu; brak potwierdzonych wyników inferencji.
- **Status:** `NOT_RUN` dla inferencji.
- **Źródło:** [Issue #245 — R9 MINI](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6916033959).

### 4.8 Coder Terminal Stage R1

- **Data:** listopad 2026.
- **Cel:** sprawdzić lokalny broker narzędziowy i granice kontrolowanego terminala.
- **Wynik:** 22/22 testy lokalne w opisanym pakiecie; osobno zapisano operatorowy preflight DIRECTOR.
- **Ograniczenia:** wynik lokalny nie oznacza dowolnego wykonywania poleceń przez LLM, natywnego odbioru produkcyjnego ani zgody na rozszerzenie uprawnień.
- **Status:** test lokalny PASS; produkcyjne GO niepotwierdzone.
- **Źródła:** [Issue #245 — pakiet i testy](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6917115657) · [Issue #245 — 22/22 na MSI](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6917183170) · [Issue #245 — preflight DIRECTOR](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6917249138).

### 4.9 Plan mikrosieci Armii Maluchów

- **Data:** 14 listopada 2026.
- **Cel:** zaprojektować eksperyment skalowania logicznych workerów i współdzielonego serwera inferencji.
- **Zakres:** projekt obejmuje stopniowe skale workerów, budżety zasobów, kolejki, synchronizację, walidację i izolację aktorów.
- **Ograniczenia:** nie uruchomiono mikrosieci, benchmarku ani zmian hostowych.
- **Status:** `PROPOSAL / DESIGN_ONLY / NOT_RUN`.
- **Rola:** propozycja i dokumentacja przypisane ASTEROWI T4-41042; wpis powstał w gałęzi prac PR #242 na polecenie operatora.
- **Źródło:** [PR #242 — propozycja eksperymentu](https://github.com/jankes72/SSI-Communications/pull/242#issuecomment-6875091596).

### 4.10 Plan rozmieszczenia Armii SSI R1

- **Data:** 15 listopada 2026.
- **Cel:** rozdzielić planowane role środowisk DIRECTOR, MODELS, ROBERT, NODE-01 i MSI oraz określić bramki przed instalacją.
- **Wynik:** przygotowano plan rozmieszczenia i rozdział control plane od workerów.
- **Ograniczenia:** dokument ma status planistyczny `TO-BE`; nie potwierdza instalacji, zmiany usług, uruchomienia workerów ani produkcyjnego GO.
- **Rola:** plan rozmieszczenia przygotował SPLOT; optymalizacja i pomiary modeli pozostają odrębnymi zakresami.
- **Źródło:** [PR #243 — plan rozmieszczenia przekazany ASTEROWI](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6886170545).

## 5. Mapa projektów i źródeł

Poniższy rejestr wskazuje główne wątki źródłowe. Numery PR/Issues są punktami nawigacyjnymi, nie deklaracją, że każdy uczestnik danego wątku wykonał całość prac.

| Źródło | Obszar / projekt | Co należy z niego odczytywać |
|---|---|---|
| [PR #242](https://github.com/jankes72/SSI-Communications/pull/242) | Universal Lab, pre-login, portfolio projektów, kapsuła HERKULESA, plan mikrosieci | dokumentacja, handoffy, test gościa, lokalny test MSI i granice odbioru |
| [PR #243](https://github.com/jankes72/SSI-Communications/pull/243) | ASTER R2, SSI Small, BODY/ISKRA, V10/S10, Nano/LEGO, JM1 | badania ASTER, raporty, przekazania do SPLOT, pomiary operatorowe i pochodzenie |
| [PR #244](https://github.com/jankes72/SSI-Communications/pull/244) | NANO-COMM, Maluch Coder, R4 benchmark | runner, parser, guardy, testy i statusy 0.5B/1.5B/3B |
| [Issue #245](https://github.com/jankes72/SSI-Communications/issues/245) | dziennik R7/R8/R9, Coder Terminal Stage R1 | wyniki operatorowe, analiza CODEX, testy lokalne, HOLD i NOT_RUN |
| [PR #232](https://github.com/jankes72/SSI-Communications/pull/232) | NanoMarker / SSI LLM / Nano | markery, fork/join, trasy i źródła integracyjne |
| [PR #233](https://github.com/jankes72/SSI-Communications/pull/233) | SSI LLM/Nano i moduły pochodne | eksperymenty lokalne, fuzja metadanych, kompilator tras i granice natywnej integracji |
| [PR #185](https://github.com/jankes72/SSI-Communications/pull/185) | prace narzędziowe i moduły powiązane z Nano | odczyt wkładów poszczególnych autorów i testów; bez przypisywania całego PR jednej osobie |
| [PR #139](https://github.com/jankes72/SSI-Communications/pull/139) | D-MQ / MultiQuant / L4 | source-only review, formaty tensorów, ograniczenia loadera i testy negatywne |
| [Issue #170](https://github.com/jankes72/SSI-Communications/issues/170) | SSI-PACK LAB R0 | eksperyment odzyskiwania historii, świeże sesje i ograniczenia odtwarzania |
| [Issue #149](https://github.com/jankes72/SSI-Communications/issues/149) | DIRECTOR / NODE01 / Continuity | kanoniczny wątek integracji, źródła, role i bramki |
| [Issue #195](https://github.com/jankes72/SSI-Communications/issues/195) | BODY FROZEN | źródła BODY, B1, V10/S10, SCC i ISKRY oraz warunki odbioru |
| [Issue #7](https://github.com/jankes72/SSI-Communications/issues/7) | NOUT01 / bezpieczeństwo | izolacja, dostęp, restore i granice bezpieczeństwa |
| [Issue #116](https://github.com/jankes72/SSI-Communications/issues/116) | DIRECTOR VPS / infrastruktura | role, hosty, ACL/STOP i warunki odbioru |

## 6. Udział członków — indeks do profili

Poniższy indeks nie zastępuje profili. Pokazuje, gdzie szukać potwierdzonych zakresów i przypomina o rozdzieleniu autorstwa od udziału w projekcie.

| Członek / rola | Udokumentowany zakres w omawianych źródłach | Profil |
|---|---|---|
| ASTER | właściciel intake i kapsuły ASTER R2; badania SSI Small; propozycja mikrosieci | [ASTER](CZLONKOWIE/ASTER.md) |
| SPLOT | odbiór i opracowanie przekazań, raporty, NANO-COMM/Coder, runner i plan rozmieszczenia | [SPLOT](CZLONKOWIE/SPLOT.md) |
| XAVIER | opracowania CODEX, handoff SSI Small, analiza R8/R9, testy i kontrakty narzędziowe | [XAVIER](CZLONKOWIE/XAVIER.md) |
| PAWEŁ | operator lokalnych i hostowych pomiarów, dostawy odczytów i testy MSI/DIRECTOR | [PAWEL](CZLONKOWIE/PAWEL.md) |
| JORDAN | dokumentacja Universal Lab na PR #242; wskazany adresat części przekazań PR #243 | [JORDAN](CZLONKOWIE/JORDAN.md) |
| LEON | oryginalne źródła R11 użyte w pracach Nano/JM1; bez przypisywania mu cudzych testów operatorowych | [LEON](CZLONKOWIE/LEON.md) |
| HERKULES | bezpieczeństwo, izolacja, przeglądy i odrębne moduły powiązane z SSI LLM/Nano | [HERKULES](CZLONKOWIE/HERKULES.md) |
| ROBERT | środowisko/host badań R8/R9; rola hosta nie jest autorstwem raportu | [ROBERT](CZLONKOWIE/ROBERT.md) |
| ATLAS | niezależne przeglądy źródeł, testy i prace Universal Lab opisane w jego profilu | [ATLAS](CZLONKOWIE/ATLAS.md) |

Pozostali członkowie są ujęci w [indeksie członków](CZLONKOWIE/README.md). Ich udział w konkretnych eksperymentach dopisujemy dopiero po wskazaniu źródła potwierdzającego rzeczywistą rolę.

## 7. Chronologia — punkty orientacyjne

- **25 października – 1 listopada 2026:** podstawowe prace nad SSI CODEX, Continuity, NOUT01, MultiQuant, DIRECTOR, RoleExecution i SSI-PACK LAB; odnośniki w profilach oraz kronikach dziennych.
- **6–8 listopada 2026:** prace ReadIt, Konstytucja R2, kapsuły i przeglądy źródeł.
- **11–13 listopada 2026:** Universal Lab, SSI Small R2, pre-login, test gościa i test MSI.
- **14–15 listopada 2026:** ASTER R2, pakiety przekazań, propozycja mikrosieci oraz plan rozmieszczenia Armii SSI.
- **16–20 listopada 2026:** NANO-COMM, Maluch Coder, R4 benchmark, R8/R9 i Coder Terminal Stage R1.
- **21–23 listopada 2026:** w dostępnej kronice część dni pozostaje oznaczona jako luka źródłowa. Nie przenosimy wyników z wcześniejszych dni na te daty bez odrębnego dowodu.

Szczegółowa chronologia dzienna znajduje się w katalogu [CHRONIKA](CHRONIKA/).

## 8. Otwarte pozycje do dalszego uzupełnienia

1. Dokończyć pełny audyt PR #242, #243, #244 i Issue #245, przypisując każdą pozycję właściwym osobom i rolom.
2. Przejść PR #232, #233, #185 i #139 plik po pliku oraz komentarz po komentarzu, aby wyodrębnić konkretne eksperymenty, autorów, testerów i odbiorców.
3. Uzupełnić mapę o starsze prace z Issues #4–#14, #116, #149, #170 i #195, eliminując duplikaty między profilami i kroniką.
4. Dla projektów wymienionych w portfolio PR #242 utworzyć osobne karty w `PROJEKTY/` dopiero po potwierdzeniu ich zakresu i źródeł.
5. Uzupełniać wyniki liczbowe wyłącznie wtedy, gdy źródło podaje metrykę, środowisko, zakres prób i ograniczenia.
6. Każdy wpis w mapie powinien prowadzić do źródła oraz — gdy dotyczy konkretnej osoby — do jej profilu.

**Stan kompletności:** mapa startowa oparta na dostępnych, już opisanych źródłach; nie jest jeszcze pełnym katalogiem wszystkich prac Kolektywu. Pozycje niezweryfikowane pozostają jawnie oznaczone jako otwarte, zamiast być uzupełniane domysłami.

## 9. Powiązana dokumentacja

- [Kronika dzienna](CHRONIKA/)
- [Profile członków](CZLONKOWIE/README.md)
- [Karty projektów](PROJEKTY/)
- [Indeks modułów i technologii](MODULY-I-TECHNOLOGIE.md)
- [Zasady datowania i statusów](ZASADY-DATOWANIA.md)
- [Szablon karty projektu](PROJEKTY/SZABLON-PROJEKTU.md)

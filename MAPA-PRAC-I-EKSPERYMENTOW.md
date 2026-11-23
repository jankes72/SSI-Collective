# Mapa prac i eksperymentów Kolektywu SSI

**Wersja:** 2.0 · **Aktualizacja:** 24 listopada 2026  
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


### 4.11 SSI Small 0.5B — TEST20 i MicroLEGO

- **TEST20:** raport zbiorczy ASTER podaje **17/20 zadań** i **56/61 kontroli**. To wynik konkretnego banku i wersji testu, nie ogólna miara inteligencji modelu.
- **MicroLEGO A/B:** raw **2/5 vs 1/5**, a dokładny JSON **3/5 vs 0/5** w raportowanym wariancie. Nie wykazano natywnego wykonania skilli.
- **Status:** eksperymenty lokalne zakończone w podanym zakresie; natywne wykonanie narzędzi i produkcyjny odbiór — niepotwierdzone.
- **Źródło:** [PR #243 — zbiorczy raport R1–R3](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6881847134).

### 4.12 SSI Small 0.5B — V10 single-field contrast R1–R3

- **Cel:** sprawdzić kopiowanie i wybór pojedynczej wartości w kontrastowych parach danych.
- **Wynik R3:** 24/24 procesy zakończyły się RC=0; P5 4/12, P6 6/12, ale w obu wariantach **0/6 par** miało jednocześnie poprawne obie strony. P5 wielokrotnie kopiował samą etykietę pola.
- **Wniosek:** poprawne zakończenie procesu lub przejście walidatora nie jest poprawnością semantyczną modelu. Nie kwalifikować 0.5B do autonomicznego sterowania V10.
- **Status:** pomiar zakończony; wynik negatywny dla autonomicznego sterowania.
- **Źródło:** [PR #243 — R3 single-field contrast](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6880080660).

### 4.13 SSI Small 1.5B — NanoMath R1–R4

- **R1:** 110/120 (91,7%) po niezależnym reaudytcie.
- **R2:** 60/80 (75%); PL 28/40, EN 32/40.
- **R3 held-out:** PL_RAW 13/20, EN_RAW 18/20, PL_ASC 13/20, EN_ASC 18/20. Zmiana formy zapisu naprawiała część przypadków, ale sortowanie samo w sobie nie podniosło wyniku.
- **R4 FULL 300:** 300/300 wyników polityk obejmowało 242 rzeczywiste wywołania GPU i 58 ponownych użyć odpowiedzi dla identycznych promptów. 1.5B uzyskał **116/150 (77,3%)** po ręcznym rozstrzygnięciu odpowiedzi REVIEW jako błędnej; 3B uzyskał **114/150 (76,0%)** w tym samym zestawie. Mianowniki obejmują skorelowane warianty, a nie niezależne losowania.
- **Ograniczenia:** w 1.5B wystąpiły błędy mnożenia i logiki, zwłaszcza po polsku; 3B miał lepszy wynik w angielskiej logice, ale słabsze wyniki części działań. Nie utożsamiać PASS procesu z CORRECT.
- **Status:** kampania R4 FULL opisana; wynik ograniczony do konkretnego banku i protokołu.
- **Źródła:** [PR #243 — karta 1.5B R1–R4](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6882188932) · [PR #243 — pełny R4 300](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6882576801).

### 4.14 SSI Small 3B — NanoMath R1–R4 i dostawa modelu

- **Wyniki:** R1 96/120 (80%); R2 70/80 (87,5%); R3 PL_RAW 14/20, EN_RAW 19/20, PL_ASC 11/20, EN_ASC 20/20; R4 FULL 114/150 (76%).
- **Dostawa:** opublikowano 67/67 części modelu 3B oraz manifest; suma części 1 672 007 680 B. To potwierdzenie obecności części i zgodności metadanych, nie niezależny fresh-clone restore.
- **Ograniczenia:** w R4 model uzyskał 6/10 dla mnożenia i 6/10 dla dzielenia; nie traktować wyniku jako autonomicznej kompetencji matematycznej.
- **Status:** binary parts published; fresh download/restore i runtime odbiór wymagały odrębnego potwierdzenia.
- **Źródła:** [PR #243 — karta wyników 3B](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883103064) · [PR #243 — dostawa 67/67](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883250313).

### 4.15 SSI 1.5B CPU R2 — optymalizacja AVX2 i A/B

- **Preflight numeryczny:** rzeczywiste fragmenty Q4/Q8 16×1536 przeszły porównanie; maksymalny błąd bezwzględny wyniósł odpowiednio około 1,31×10⁻⁶ i 5,36×10⁻⁷. Na tym etapie nie uruchomiono generowania tokenów.
- **Pierwszy A/B serial:** kandydat uzyskał 0,475× przepustowości baseline i był około 2,105× wolniejszy w opisanej próbie 16-tokenowej.
- **OpenMP 2 threads:** kolejny wariant uzyskał 0,9566× baseline, nadal regresja o 4,34%.
- **R2.1 AVX2:** późniejsze testy A/B raportowały poprawę, w tym powtarzalność 1,4379× i test 32-tokenowy 1,8192×.
- **R2.2:** osobne przebiegi 64-tokenowe raportowały 2,4446×, a 128-tokenowa sekwencja A/B/B/A — 3,0457× dla mediany generate_s oraz około 4,9431× dla mediany sumy kolejnych forward. To wynik konkretnego promptu, hosta i backendu; nie uogólniać na wszystkie warstwy, modele ani obciążenia.
- **Wniosek:** historia zawiera zarówno regresje, jak i późniejsze poprawy. Należy zachować wszystkie etapy, a nie przedstawiać wyłącznie najlepszego wyniku.
- **Status:** eksperymentalne A/B na MSI; wdrożenie na VPS i produkcyjny odbiór — niepotwierdzone.
- **Źródła:** [numeric preflight](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883433941) · [regresja serial](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883487256) · [R2.1 AVX2](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883639365) · [powtarzalność R2.1](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883685226) · [R2.2 64-token](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883864324) · [R2.2 128-token](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883957119).

### 4.16 GPU R1/R2/R3 — mechanizmy akceleracji i porównanie

- **Zakres:** GPU R2 obejmuje fused packed GEMV dla decode; GPU R3 dodaje eksperymentalny batched Q4 GEMM dla wybranych dużych macierzy i wielu tokenów prefill. To mechanizmy wykonawcze, nie nowy model, router ani scheduler.
- **Pokrycie potwierdzone w przytoczonym preflight:** Q4 i Q8; nie jest to dowód pełnej zgodności wszystkich formatów.
- **Porównanie:** raport 1.5B podaje 20/20 identycznych par odpowiedzi dla GPU R2 i R3.1 w określonym teście; zgodność wyjścia nie oznacza naprawy błędów rozumowania ani ogólnego przyspieszenia.
- **Port CPU:** kandydat CPU był badany oddzielnie w punkcie 4.15. Nie przenosić wyników GPU na CPU.
- **Status:** badania i porównania wariantów; pełna macierz A/B GPU oraz generalny speedup wymagają osobnych źródeł.
- **Źródła:** [PR #243 — techniczny intake GPU R1–R3](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6875385560) · [PR #243 — karta 1.5B i porównanie GPU](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6882188932).

### 4.17 Armia Maluchów R1 — sterownik czterech slotów

- **Cel:** przygotować kontrolowany sterownik czterech logicznych slotów laboratoryjnych na istniejącym SSI Small 0.5B CPU.
- **Wynik źródłowy:** 14/14 testów offline PASS, 6/6 selftest PASS, cztery sloty w stanie PLAN_ONLY; pliki źródłowe i receipty zostały opublikowane.
- **Ograniczenia:** właściwy pilot run-offline-llm nie był jeszcze wykonany w tym źródłowym wpisie. Nie było natywnego klastra agentów, VPS backendu ani aktywnego uruchomienia BODY/ISKRA.
- **Status:** kod i testy offline PASS; modelowy pilot NOT_RUN w tym punkcie historii.
- **Źródło:** [PR #243 — Armia Maluchów R1](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6882419940).

### 4.18 Armia Maluchów S1 — staging i shadow na ROBERT

- **Cel:** sprawdzić przygotowany pakiet S1 i syntetyczny kod na starym hoście ROBERT.
- **Wynik:** operator potwierdził rzeczywisty SSH preflight i późniejszy staging/shadow syntetycznego kodu.
- **Ograniczenia:** nie był to test inferencji LLM ani natywne uruchomienie BODY; brak potwierdzenia pełnego modelowego runtime i aktywnej armii workerów.
- **Status:** hostowy staging/shadow syntetyczny; model inference i produkcyjny GO — niepotwierdzone.
- **Źródła:** [PR #243 — preflight S1 na ROBERT](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6990157603) · [PR #243 — staging/shadow S1](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6990435643).

### 4.19 NANO-COMM R2 — 0.5B na DIRECTOR

- **Cel:** sprawdzić zadania COPY, MARKER i MEANING na rzeczywistym modelu 0.5B AVX2 R4.
- **Wynik:** R2 FULL30: **30/30 inferencji**, 12/30 exact, 18/30 poprawnego formatu; L1 COPY 10/10, L2 MARKER 0/10, L3 MEANING 2/10.
- **Wniosek:** format odpowiedzi był znacznie częściej poprawny niż treść semantyczna; MARKER nie przeszedł w tej próbie.
- **Status:** rzeczywisty ograniczony test modelu; bez produkcyjnego GO.
- **Źródło:** [PR #244 — R2 FULL30](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6916928848).

### 4.20 Maluch Coder R3 — kontrolowane misje narzędziowe

- **Cel:** sprawdzić wybór dwóch dozwolonych statycznych narzędzi i wykonanie zadań na syntetycznym JSON.
- **Wynik FULL4:** 4/4 właściwe ID narzędzi, 4/4 misje EXECUTED_VERIFIED, 4/4 poprawne baseline'y deterministyczne, 6/6 odmów bez niepożądanego procesu. Odczyt receipt potwierdził exit=0, puste stderr i zgodne stdout.
- **Koszt:** średnio około 6,33 s generowania modelu i 0,102 s wykonania statycznego programu; to osobne fazy, nie pomiar pełnego wall-clock ani dowód przyspieszenia.
- **Ograniczenia:** tylko dwie intencje semantyczne w dwóch wariantach promptu; guided zawierał nazwy narzędzi. Nie potwierdzono Pocket Micro, BIT/Nano, SCC ACL ani izolacji systemowej per misja.
- **Status:** ograniczony real-model pilot na DIRECTOR; autonomiczny terminal i produkcyjny GO — NO-GO.
- **Źródła:** [PR #244 — R3 FULL4](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6917639552) · [receipt readback i czasy](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6917886107) · [Issue #245 — szczegółowy wynik](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6917887936).

### 4.21 R4 — sześciogodzinny benchmark specjalizacji 0.5B / 1.5B / 3B

- **Plan:** sparowany PL/EN benchmark dziewięciu specjalizacji: COPY, MARKER, TOOL, MATH, LOGIC, MEM, CODEOP, JM1 i HOLD; ten sam bank case_id, rotowana kolejność, scorer i guardy zasobów.
- **Preflight:** 7/7 testów offline, w tym symulowane wywołania fake CLI; te testy nie wykonywały inferencji modeli.
- **Inwentaryzacja:** na MSI znaleziono fizyczne wagi trzech modeli. Pełny SHA 0.5B zakończył się PASS; odczyt 1.5B został dwukrotnie przerwany przez IO_PRESSURE przy 7,59% i 6,40% I/O; 3B pozostał NOT_STARTED.
- **FIX1/FIX2:** parser i runner poprawiono; 9/9, następnie 11/11 testów offline PASS. Próby PILOT_COMPLETE z fake CLI były symulacją, nie realnym pilotem. FIX2 dodał guardy w trakcie czytania SHA.
- **Wniosek:** nie uruchomiono sześciogodzinnej kampanii R4 na trzech modelach. Nie wolno obniżać progu I/O ani powtarzać zatrzymanych odczytów bez nowej diagnostyki.
- **Status:** plan i runner przygotowane; 0.5B SHA PASS; 1.5B HOLD; 3B NOT_STARTED; R4 6H NOT_RUN.
- **Źródła:** [PR #244 — plan 6H](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6918455499) · [preflight](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6918872499) · [3 modele na MSI](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6919026010) · [0.5B PASS / 1.5B HOLD / 3B NOT_STARTED](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6920492407) · [FIX2 11/11](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6920753279) · [drugi HOLD 1.5B](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6920934735).

### 4.22 CODEX R8 i R9 MINI — badania na ROBERT

- **R8:** sześciogodzinny przebieg na ROBERT; 674 wywołania, 30 kompletnych dwujęzycznych przypadków. W zestawie protokołu raportowano wyniki S05 8/60, S15 31/60, S3 37/60 i HMIX_3 40/60. Mianownik 60 oznacza 30 zadań × dwa języki, nie 60 niezależnych zadań.
- **R9 MINI:** 50/50 wywołań w pięciu zadaniach EN/PL, z dalszą analizą MOD. Zachować rozróżnienie wariantów i dokładnych zadań; nie przenosić wyniku na cały model.
- **Role:** Paweł wykonywał próby operatorskie na ROBERT i przekazywał odczyty; XAVIER/CODEX opracował analizę i raport. ROBERT jest nazwą hosta, nie autorem wyników.
- **Status:** R8 i R9 MINI wykonane w ograniczonym protokole; brak ogólnego GO.
- **Źródła:** [Issue #245 — R8/R9 i pochodzenie](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6914120514) · [R8 handoff](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6914584055) · [R9 MINI](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6916033959).

### 4.23 Coder Terminal Stage R1 — broker i ograniczone narzędzie

- **Test lokalny:** 22/22 testy jednostkowe PASS na MSI.
- **Test hostowy:** ograniczony krok id -u na DIRECTOR zakończył się exit_code=0, zwrócił UID 1001; test nie wywołał modelu.
- **Granica:** nie potwierdzono SCC issuer, Pocket Micro, BIT loadera ani pełnego bindingu misji. Nie jest to dowód autonomicznego działania Malucha Codera.
- **Status:** lokalny pakiet i pojedynczy ograniczony tool step PASS; pełna misja HOLD_UNBOUND_NOT_DONE, produkcyjne GO — NO-GO.
- **Źródła:** [Issue #245 — 22/22 testów](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6917183170) · [Issue #245 — operatorowy preflight](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6917249138) · [Issue #245 — rzeczywisty krok narzędzia](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6917336093).

### 4.24 EDU-A1 — pierwsza linia CODER + CAPSULE na 0.5B

- **Cel:** badać model 0.5B jako ograniczony komponent pierwszej linii CODER oraz oddzielnie oceniać odczyt kart/kapsuł; wagi pozostały zamrożone.
- **MSI:** pierwsze zadania CAL ujawniły błędne odpowiedzi HOLD i CHECK_ACL; po wznowieniu BODY_CODE_01 uzyskał poprawny wynik. W pierwszych trzech rzeczywistych przypadkach CAL były więc **1/3** poprawne. Przebieg zatrzymał się na HOLD_HOST_RESOURCE_PRESSURE; nie był to ukończony test 60 zadań.
- **ROBERT:** pierwszy smoke wygenerował HOLD (3 tokeny) — poprawny technicznie format, ale nie odpowiedź oczekiwana dla tego testu. Pierwszy CAL BODY_GATE_01 również zwrócił HOLD zamiast DRAFT; drugi BODY_ROUTE_01 zwrócił CHECK_ACL zamiast CHECK_ACTOR. Readback potwierdził 0/2 dla tych dwóch przypadków, bez niebezpiecznych deklaracji działania.
- **Testy harnessu:** 41/41 unit tests i selftest 120 PASS; te wyniki nie są inferencjami modelu.
- **Ważny rozdział:** 1131 wpisów w atlasie strukturalnym oznacza fizyczne tensory safetensors, nie 1131 odrębnych obwodów wiedzy. CAPSULE_CAL i szersze kwalifikacje pozostają osobnymi bramkami.
- **Status:** ograniczone próby rzeczywiste i diagnostyka wykonane; kampania 60 CAL + 60 HOLDOUT nieukończona; produkcyjne GO — NO-GO.
- **Źródła:** [PR #243 — EDU-A1 wyniki MSI](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6992365819) · [MSI 3/60 i pierwsza poprawna odpowiedź CODER](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6992693029) · [ROBERT pierwszy CAL](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6994516373) · [readback odpowiedzi ROBERT](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6994784955) · [2/2 i checkpoint](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6996452688).

### 4.25 Atlas wiedzy / Atlas obliczeń — próby referencyjne i C12/C13

- **Atlas112 R7 / linia 70B:** na 20 prefiksach Atlas pokonał losowy wybór 112 kafli w 19/20 przypadków przy identycznym budżecie wag. Zachował 53,76% redukcji średniego błędu uzyskanej przez pełne BF16 dla up_proj; próg >50% został spełniony. Średni względny L2: Q8 2,9225%, Atlas112 2,3466%, random112 2,6580%, pełne BF16 1,8514%. Mediana czasu Atlasu 2,1521 s wobec 2,1330 s Q8; to eksperyment na MLP warstwy 0, nie wynik całego 70B.
- **EDU reference8:** na ośmiu syntetycznych rekordach układ warunkowego odczytu uzyskał 8/8 poprawnych decyzji, tak samo jak wariant odczytujący oba pola zawsze, ale z 12 zamiast 16 wywołań modelu. Wynik opiera się na małym, kontrolowanym zbiorze; nie kwalifikuje pełnego systemu.
- **C12/C13:** inwentaryzacja strukturalna 1131 tensorów została odczytana bez luk i nakładania się offsetów; aktywacyjne C12 i część testów C13/S5M pozostały NOT_RUN/HOLD. Próba jakości S5M na rzeczywistym 0.5B została zatrzymana przez HOST_RESOURCE_PRESSURE.
- **Status:** Atlas112 R7 spełnił z góry określone kryteria w swoim zakresie; EDU reference8 ograniczony PASS; C12/C13 nieukończone.
- **Źródła:** [PR #243 — Atlas112 R7](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-7024211244) · [PR #243 — EDU reference8](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6997907205) · [PR #243 — C13 S5M HOLD](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6990491824).

### 4.26 SSI Nano-Brain — wybór kompetencji Pocket R9–R11

- **Cel:** sprawdzić, czy model 0.5B potrafi rozpoznać, czy polecenie wymaga jednej z dwóch kompetencji Pocket, oraz odróżnić NAPIS, LISTA i BRAK.
- **R9, 8 godzin:** 370 przykładów treningowych i 369 zadań testowych z 24 szablonów. Klasyfikator 172/369; model z kartą 153/369; model z kartą i przykładami 149/369. Dodanie przykładów zmniejszyło fałszywe wskazania skilla dla klasy BRAK z 47/123 do 26/123.
- **R10:** podstawowa karta 13/24; wariant z dodatkową podpowiedzią 10/24; żaden nie uzyskał 0/8 całkowicie poprawnych trójek.
- **R11:** model 0.5B odpowiedział tak 24/24; wykrył 8/8 celów, ale zaakceptował również wszystkie 16 poleceń o innych celach — zbalansowana trafność 50%. Kryterium przejścia nie zostało spełnione.
- **Ważne:** w całej kampanii liczba rzeczywistych wywołań kompetencji Pocket wyniosła zero. To badanie decyzji/klasyfikacji, nie dowód wykonania skilli.
- **Status:** eksperyment R9–R11 zakończony; kryterium użycia kompetencji niezaliczone; brak autonomicznego GO.
- **Źródło:** [PR #243 — Nano-Brain R9–R11](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-7026280271).


### 4.27 NanoMarker / NanoBit / LoRA — T0-34N i R12

- **T0-34N:** eksperyment OFFHOST na CPU i syntetycznych wagach. 30/30 testów jednostkowych PASS, pięć seedów, rozdzielone TRAIN/CAL/VAL/TEST/SHIFT. NanoBit+LoRA+heurystyka osiągnęły 2701 B i TEST MSE 0,001462824 wobec Q2 2721 B i MSE 0,014263527.
- **Wynik negatywny:** uczona polityka NanoMarker nie pokonała heurystyki w głównym profilu 25% (0/5 seed wins). Na niestrukturalnych wagach wariant Nano miał MSE około 0,19186 wobec około 0,01359 dla Q2. Fallback pozostaje konieczny.
- **R12:** osobna bramka codec-admission/fallback otrzymała 16/16 lokalnych testów PASS. Raport R12 wskazuje, że uczony NanoMarker przegrywał z heurystyką w 8/10 seed; NanoBit POSTHOC zwiększał rozmiar, a nie oszczędzał bajtów w 0/10 prób. Bramka nie była wpięta do treningu ani inferencji.
- **Granica:** to małe syntetyczne sieci/formaty toy, nie testy natywnego GGUF, QAT, LLM 70B/9B ani jakości modelu klienta.
- **Status:** testy syntetyczne i kod bramki PASS w ograniczonym zakresie; niezależna replikacja, live capsule binding i trening modelu 70B — NOT_RUN.
- **Źródła:** [PR #185 — T0-34N](https://github.com/jankes72/SSI-Communications/pull/185#issuecomment-6660555573) · [source readback 8/8](https://github.com/jankes72/SSI-Communications/pull/185#issuecomment-6662354287) · [R12 codec gate](https://github.com/jankes72/SSI-Communications/pull/185#issuecomment-6662636717).

### 4.28 NanoGate T0-35 — klasyfikator wyboru ścieżki

- **Cel:** sprawdzić, czy klasyfikator 11 cech może wskazywać, kiedy warto rozważyć ścieżkę Nano, z bezpiecznym fallbackiem.
- **Metoda:** 240 TRAIN, 80 TUNE, 80 TEST i 48 SHIFT_TEST na syntetycznych rodzinach, oddzielne seedy; drugi przebieg odtworzył identyczny model.
- **Wynik:** znane rodziny TEST: learned 80/80 (TP48 FP0 FN0 TN32), heurystyka 64/80. Niewidziane rodziny SHIFT_TEST: learned 26/48, heurystyka 32/48; learned nie wygrał na SHIFT i wygenerował 22 fałszywe wskazania Nano.
- **Ograniczenia:** ostateczna bramka VAL/SHIFT_VAL odrzuca niebezpieczne wskazania; NanoGate zwraca jedynie WORTH_TRY, nie ma władzy nad kodowaniem, ACL ani klientem. Koszt obliczania cech nie został zmierzony jako przyspieszenie.
- **Status:** syntetyczny OFFHOST eksperyment zakończony; brak dowodu na przewagę poza rozkładem treningowym.
- **Źródło:** [PR #185 — NanoGate T0-35](https://github.com/jankes72/SSI-Communications/pull/185#issuecomment-6663197847).

### 4.29 Nano Full-Path / markery LEGO — PR #232

- **Cel:** zapewnić collision-safe tożsamość markerów i sprawdzalną trasę od manifestu do komponentu, bez zgadywania przy kolizjach.
- **Przegląd źródłowy:** 15 417 manifestów, 15 415 identyfikatorów i dwie grupy kolizji; resolver zwraca AMBIGUOUS zamiast arbitralnie wybierać wariant. Indeks dekodowany raz do RAM uzyskał w syntetycznych 100 lookup medianę około 1,669 ms vs 0,011 ms dla cache — metadane, nie throughput LLM.
- **Eksperyment SPLOT:** pięć skonstruowanych par małych sieci ReLU 8→16→3, syntetyczne wagi int8 i 1024 wejścia testowe na seed. Wszystkie kryteria postawione dla tej tezy spełniono w 5/5 konstrukcji; wynik dotyczy adaptera/kontraktu na małych sieciach, nie natywnych LLM.
- **FORK/JOIN:** 41 nowych testów PASS dla konkretnych fork_ref, portów JOIN, izolacji aktorów, scope, rewizji, luk w zdarzeniach i transportu. Odtworzono 7000 syntetycznych zdarzeń. Eksperymentalna ramka indeksów była większa od JSON+zlib we wszystkich czterech skalach; nie promować jej jako zwycięzcy kompresji.
- **Rzeczywista partia LEGO na ROBERT:** zapisano 15 417 unikatowych markerów i readback PASS, ale 24 249 wystąpień zależności miało TARGET_UNRESOLVED. Nie oznacza to 24 249 brakujących modułów; nie utworzono krawędzi na podstawie podobieństwa nazw.
- **Kontynuacja:** PR238 naprawił wymaganie ciągłych krawędzi i rodzica RESULT oraz rozszerzył fingerprint markerów warstwy; odczyt links wykazał 30 kontroli integralności PASS, ale 24 249 odwołań pozostało UNBOUND.
- **Status:** source review, lokalne testy i zapis markerów wykonane; pełny semantyczny graph/host-native dispatch i pełny odbiór full-path niepotwierdzone.
- **Źródła:** [PR #232 — source review](https://github.com/jankes72/SSI-Communications/pull/232#issuecomment-6727686453) · [lokalna próba SPLOT](https://github.com/jankes72/SSI-Communications/pull/232#issuecomment-6727903946) · [FORK/JOIN 41 testów](https://github.com/jankes72/SSI-Communications/pull/232#issuecomment-6728162400) · [realny zapis markerów](https://github.com/jankes72/SSI-Communications/pull/232#issuecomment-6728895842) · [PR238 / links](https://github.com/jankes72/SSI-Communications/pull/232#issuecomment-6748423728).

### 4.30 SSI LLM Nano R11 / CpuLink — PR #233 i niezależny replay

- **Cel:** połączyć istniejące trasy, markery i R11 bez nadpisywania oryginalnych źródeł ani mieszania kontekstów aktorów.
- **Replay SPLOT:** 156 plików z Git blob SHA zgodnymi ze źródłami; 44/44 sum R11 PASS; 439/439 testów i 8/8 scenariuszy PASS. Na IPv4 localhost uruchomiono dwa rzeczywiste procesy OS. 81/81 żądań miało oczekiwane statusy: 55 JOINED, 13 PARTIAL i 13 STOP. To test syntetycznych wejść i procesów/TCP, nie produkcyjny runtime.
- **Koszt:** mediana lokalnego TCP+prepare 18,707 ms; cache RAM 0,462 ms wobec baseline 0,622 ms, 24/24 cache hits. Nie są to czasy generacji LLM.
- **Wkład HERKULESA obok PR233:** osobny NanoTRS compiler użył przypiętych źródeł PR233; 26/26, a po polskim interfejsie 66/66 testów PASS na syntetycznych trasach. Kompilator kończył na SOURCE_ROUTE_COMPILED_NO_DISPATCH; can_execute=false.
- **F1-A/F1-B dawców GGUF:** na ssi-models-vps potwierdzono metadane trzech oddzielnych modeli: Qwen2.5-Coder 3B 434 tensory, LFM2 d1:3b 266, Hermes3 3B 255 — razem 955 wpisów. Odczytano trzy próbki bloków: 322 B i 544 zdekodowane wartości. To nie jest scalony model ani pełna atestacja bajtów wag; nie wykonano inferencji, treningu adaptera ani dispatchu kafli.
- **Status:** replay i testy tras PASS w zakresie syntetycznym; metadane i małe próbki GGUF odczytane; semantyczne powiązanie skill→tensor, adapter i natywne wykonanie NOT_RUN/UNBOUND.
- **Źródła:** [PR #233 — replay 81/81](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6728894653) · [HERKULES F1-A metadata](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6729608434) · [F1-B próbki 3 modeli](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6729654571) · [NanoTRS 26 testów](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6729993681) · [NanoTRS Polish 66/66](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6730128301).

### 4.31 LEGO 70B — NOUT1 T2F / T3A / T3B

- **T2F:** złożono pierwszy pełny tensor 8192×28672 w Q8; 64/64 źródła, 236 716 032 B, niezależny read-only audyt 8192/8192 PASS.
- **T3A:** fizyczny read-only preflight potwierdził indeks 723 tensorów i 30/30 nagłówków shardów BF16; 562 rank2 i 161 rank1. Teoretyczny rozmiar Q8 dla 2D + BF16 dla 1D wynosił 71 106 215 936 B (<80 GB). Porównanie 16 wierszy BF16 z T2F Q8 dało względny błąd Frobeniusa 0,00804899; proxy matvec były syntetyczne.
- **Granica:** T3A nie wykonał pełnego 141 GB rehash, natywnego treningu ani inferencji 70B. T3B był przygotowany jako kontroler kampanii i audytor, 21/21 testów syntetycznych PASS, ale sam ten wynik nie oznacza uruchomienia kampanii na hoście.
- **Status:** T2F fizyczny tensor i niezależny audyt PASS; T3A read-only PASS; T3B source-ready / synthetic PASS; pełny model i inferencja NOT_RUN.
- **Źródła:** [PR #139 — T2F i plan T3A](https://github.com/jankes72/SSI-Communications/pull/139#issuecomment-6549190247) · [PR #139 — T3A fizyczny PASS i T3B source-ready](https://github.com/jankes72/SSI-Communications/pull/139#issuecomment-6549337060).

### 4.32 MultiQuant L4 — formaty tensorów i ograniczenia loadera

- **Zakres:** statyczny przegląd trzech trybów formatu tensorów i dodatkowe testy negatywne w odrębnym PR135; PR139 pozostaje planerem i audytorem artefaktów, nie pełnym loaderem.
- **Testy źródłowe:** PR135 uzyskał 20/20 source tests PASS; adapter PR139 uzyskał 52/52 source/shadow tests PASS w opisanym HEAD.
- **Ograniczenia:** testy nie były testami realnego loadera, native I/O ani pełnego modelu 70B. Brak potwierdzenia 30/30 shardów, natywnego odczytu wszystkich tensorów, lease/ACL/STOP i inferencji.
- **Status:** source/shadow PASS; native full-model NOT_RUN.
- **Źródła:** [PR #139 — L4 source handoff](https://github.com/jankes72/SSI-Communications/pull/139#issuecomment-6536881759) · [PR #139 — aktualizacja 52/52](https://github.com/jankes72/SSI-Communications/pull/139#issuecomment-6536915254) · [PR #139 — niezależny odbiór i braki](https://github.com/jankes72/SSI-Communications/pull/139#issuecomment-6536961088).


### 4.33 BODY FROZEN / CZARA / ZeroLab — historyczne laboratoria i Micro-First

- **Archiwa S20–S26:** historyczny pakiet R1 obejmował 35 rodzin lokalnych protokołów powiązanych z 210 definicjami przypadków. R2 opisywał wspólny slot treningów CZARY i Final bez replay i zwiększania budżetu. Są to archiwa wcześniejszych prac, nie automatyczny dowód bieżącego działania całego laboratorium.
- **ZeroLab CZARA FINAL V2:** odnaleziono rzeczywisty kod SSI ZeroLab, rozdzielenie aktorów CZARA/FINAL, wersjonowane testy oraz adapter native_micronetwork_v1 wywołujący runtime.micro.advise po kontroli enabled/SHA wag/cech. Historyczne raporty wymagają zachowania statusów per przypadek; brak laboratorium lub niewykonalne porównanie ma być INCONCLUSIVE, nie automatycznym FAIL.
- **S20–S26 / R6:** źródłowa rekonstrukcja wskazała historyczne PASS dla ISKRA2/S26-01-01 i ISKRA5/S24-01-01, ale ISKRA4/S24-01-02 w prywatnym R24 miała status REVIEW_INVALID. S26 jako cały etap nie został potwierdzony jako zakończony przez odczytany publiczny indeks.
- **CZARA Micro-First / PR197:** przygotowano source intake i raport o oryginalnych rejestrach skilli, V10, learning flow, mikrosieci, Research Memory i SCC. To odzysk i źródłowa dokumentacja; nie przypisywać temu automatycznie nowego treningu ani wdrożenia.
- **Wkład LEONA — oryginalny Pocket Micro i NanoBit T031:** wykonano porównanie dwóch torów na tym samym skillu 8/8, z identycznymi wynikami i odmowami. Każdy wariant obejmował 5 rzeczywistych inferencji i 3 wykonania recipe. Trening używał 6 syntetycznych wejść autora i 8 innych przypadków walidacyjnych. Oryginalny Store/Checkpoint odczytano w nowym procesie, bez replay skilla; dwie uszkodzone kopie odrzucono. To ograniczony test oryginalnego przykładu Pocket Micro/NanoBit, nie kwalifikacja dronów ani wszystkich skilli.
- **Granica pełnego SSI LLM:** oryginalny V10 zwrócił FULL_FLOW_UNAVAILABLE, backend był nieosiągalny, liczba generacji LLM wyniosła zero, a natywne BIT/B1 pozostawały UNBOUND. Całość została opisana jako PARTIAL_EXECUTED_NOT_FULL_SSI_LLM.
- **Status:** historyczne laboratoria i częściowy test Micro/NanoBit potwierdzone w podanych zakresach; pełny przebieg SSI LLM, wszystkie ISKRY i cały S20–S26 — niepotwierdzone.
- **Źródła:** [Issue #195 — źródła CZARA / PR197](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6673073749) · [Issue #195 — rekonstrukcja S20–S26](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6673295308) · [Issue #195 — archiwa ZeroLab](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6673504004) · [Issue #195 — LEON Micro/NanoBit R6](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6682065411).

### 4.34 LEON R8 — lokalny scenariusz SSI LLM na dwóch węzłach

- **Cel:** sprawdzić lokalny scenariusz współpracy usług i ról na dwóch węzłach z użyciem istniejących mechanizmów pamięci, kapsuł, Operations i ciągłości.
- **Wynik:** 66/66 kontroli scenariusza, 16/16 kontroli odczytu i restore, 187 zdarzeń. W przebiegu uczestniczyły dwa lokalne procesy serwerów, czterech wykonawców, siedem oddzielnych kapsuł i 15 zapisanych wiadomości PHONE.
- **Granica:** to lokalny scenariusz testowy; nie potwierdza automatycznie bieżącego hostowego wdrożenia, aktywności wszystkich agentów ani pełnego produkcyjnego SSI.
- **Status:** lokalny scenariusz i kontrole restore PASS w określonym zakresie.
- **Źródło:** [Issue #195 — LEON R8](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6685120433).

### 4.35 META Tensor LEGO P1 / R5 — eksperyment syntetyczny CPU

- **Cel:** zbadać rozkład Tensor LEGO w modelu typu SwiGLU i przygotowanie ścieżki ucznia R5.
- **Wynik MOST:** SYNTHETIC_CPU_27_PASS oraz REPRO_84_PASS dla kontrolowanego sztucznego bloku hidden128/ffn256. W wariancie low-rank+sparse ranga16 payload trzech macierzy zmniejszył się o 26,08% w tym syntetycznym przypadku.
- **Wspólne guardy:** MOST połączył istniejące guardy dtype i kontrole rangi; 15 testów inventory i 6 testów rank PASS w CI. Testy nie uruchamiały nauczyciela 70B.
- **Wynik KORDIANA:** dostarczono źródłowy zestaw L3/L6/L9 i przygotowanie realnego bloku, ale B5/teacher i budowa studenta pozostawały NOT_RUN.
- **Ograniczenia:** to eksperyment syntetyczny i testy kontraktów; nie jest treningiem 70B, nie dowodzi jakości studenta ani oszczędności pamięci w rzeczywistym modelu.
- **Status:** syntetyczne testy i kod PASS; 70B teacher NOT_RUN; student NOT_BUILT.
- **Źródła:** [Issue #44 — MOST META LEGO P1](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6499424660) · [Issue #44 — MOST L2/B1 guardy](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6532283643) · [Issue #44 — KORDIAN B0/B1/L3](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6532265825).


### 4.36 SSI-PACK LAB R0 — odtwarzanie kontekstu z jednej wiadomości

- **Cel:** sprawdzić, czy krótka ostatnia wiadomość może wskazać przypięte źródła i pozwolić nowemu procesowi odtworzyć aktualny kontekst bez odtwarzania efektów ubocznych.
- **HERKULES:** 45/45 nowych negatywnych testów bezpieczeństwa w GitHub Actions; dodatkowo istniejący szkielet 108/108. Obejmowały m.in. obcą rolę/tenant, revoke, zmieniony SHA, nieaktualny kursor, luki w historii, duplikaty i prompt injection traktowany jako niezaufane dane. Nie wykonano prawdziwej sesji ChatGPT B ani natywnego issuer.
- **DYREKTOR/ANDRZEJ:** 25/25 lokalnych testów offline fikcyjnego orakla; nie był to CI. Kapsuła miała 805 B wobec 3840 B pełnego wejścia, ale kapsuła wraz z odczytanymi źródłami 4005 B — bez oszczędności całkowitego transferu w tej próbce.
- **ATLAS:** niezależny orakl 21/21 w GitHub Actions. Pełne wejście 2193 B, kapsuła 831 B, odczyty 1639 B, łącznie 2470 B — około 13% więcej niż FULL. Nie mierzono tokenów ani czasu modelu.
- **NATHAN_SSI:** 23/23 testy offline w GitHub Actions, w tym osobne procesy, korekta po kursorze, UTF-8 pagination, brak nowych zdarzeń i negatywy uprawnień. Testowy grant był fikcyjny; nie potwierdzono rzeczywistego issuer.
- **XAVIER/CODEX:** osobny parser/kodek 62/62 testy CI; HERKULES wykrył jednak niezgodność statyczną formatu kapsuły Dyrektora i Xaviera pod tą samą nazwą SSI-RESUME/0.1 (różne pola i format referencji). Zgodność między właścicielami pozostała HOLD.
- **ROBERT:** dodatkowy oracle no-replay/effect-semantics: 50/50 testów w GitHub Actions. To syntetyczna bramka klasyfikacji skutków, bez prawdziwej sesji B, native issuer/ACL, live readback ani receipt efektu.
- **WIT:** niezależny oracle 56/56 w GitHub Actions, w tym odrębny proces systemowy B; na dwóch fikcyjnych zestawach payload FULL vs PACK+fetch zmniejszył się o 62,36% i 63,60%. To bajty syntetycznych źródeł, nie tokeny ani koszt modelu. WIT wykrył też statyczną niezgodność trzech formatów wire; wspólny standard pozostał HOLD.
- **SPLOTUŚ:** read-only indeks 21 Issues, 1308 komentarzy i 150 PR metadata; catch-up kursora #170 znalazł 3 nowe komentarze, 0 brakujących i 0 zmienionych starszych w sprawdzonym odczycie. Nie obejmował pełnych komentarzy/review wszystkich PR ani świeżej sesji ChatGPT B.
- **Wynik zbiorczy:** potwierdzono lokalne i CI testy źródłowe różnych implementacji; nie potwierdzono jednej interoperacyjnej kapsuły, odzyskania prawdziwej sesji ChatGPT A→B, pomiaru tokenów ani produkcyjnej pamięci SSI.
- **Status:** source/offline PASS w odrębnych zakresach; wspólny wire/interoperability HOLD; live A→B NOT_RUN; PROD_GO=NO.
- **Źródła:** [Issue #170 — HERKULES 45/45](https://github.com/jankes72/SSI-Communications/issues/170#issuecomment-6564437848) · [DYREKTOR 25/25 i pomiar bajtów](https://github.com/jankes72/SSI-Communications/issues/170#issuecomment-6564442865) · [ATLAS 21/21 i pomiar FULL/PACK](https://github.com/jankes72/SSI-Communications/issues/170#issuecomment-6564445734) · [NATHAN_SSI 23/23](https://github.com/jankes72/SSI-Communications/issues/170#issuecomment-6564458619) · [niezgodność schematów](https://github.com/jankes72/SSI-Communications/issues/170#issuecomment-6564469813) · [XAVIER 62/62 i HOLD interoperacyjności](https://github.com/jankes72/SSI-Communications/issues/170#issuecomment-6564500615).

### 4.37 Qwen 0.8B na NOUT1 — benchmark inferencji i Context Fastpath

- **Model:** lokalny qwen3.5:0.8b na fizycznym NOUT1. W pomiarze z 28 października 2026 r. ciepłe GPU20+CPU2 uzyskało medianę pełnej odpowiedzi **1,3378405 s**, a CPU-only **4,3452935 s** — około **3,25×** w tej konkretnej konfiguracji.
- **Próba jakościowa:** 6/6 prostych odpowiedzi syntetycznych PASS; kontekst 2048, wyjście 43 tokeny. Liczba prób była mała (po dwa ciepłe pomiary na profil), więc nie jest to szeroki benchmark ani test jakości zadań produkcyjnych.
- **Context Fastpath:** oryginalny compact_context.py::compile_view przeszedł 26/26 testów offline; integracja natywna NOT_RUN. Osobny tokenizer text-only przeszedł 7/7 testów, ale parity z finalnym rendererem pozostała UNBOUND.
- **Pamięć:** raport wskazywał syntetyczny eksperyment SQLite/index; nie wolno interpretować deklaracji redukcji rozmiaru jako ogólnej oszczędności tokenów bez pomiaru na finalnym rendererze i rzeczywistych promptach.
- **Wkład:** SPLOT dostarczył pierwotny benchmark i kod Context Fastpath; ATLAS podjął niezależne retesty źródeł; XAVIER odebrał counter i testował oryginalne Operations/RM/R17 w osobnym zakresie.
- **Status:** historyczny lokalny benchmark modelu i testy komponentów wykonane; native Context Fastpath integration i bieżący host/provider — niepotwierdzone.
- **Źródła:** [Issue #149 — SPLOT Qwen 0.8B i Fastpath](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6549084045) · [ATLAS — retesty i rozdzielenie pomiarów](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6549267314) · [XAVIER — Operations/R17 18/18](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6549382232).

### 4.38 Continuity / Role Resume — rzeczywisty odczyt i restore offline

- **Zakres:** historyczny pakiet ssi_role_resume_r1.py został uruchomiony przez operatora na fizycznym NODE01; 258 608 B, SHA256 zgodny z historycznym PR21 VALIDATION.json. Odczyt strukturalny potwierdził 10 źródeł dla jednej roli HERKULES.
- **Wynik restore:** SNAPSHOT_CONTEXT_RESTORED, 10 źródeł załadowanych, 76 wpisów dziennika zindeksowanych, 421 359 B kontekstu. Liczba wywołań modelu wyniosła zero; runtime admission nie zostało przyznane, production_ready=false.
- **Granica:** to odtworzenie kapsuły/źródeł offline, nie wznowienie aktywnej sesji modelu, nie natywny issuer i nie przywrócenie uprawnień do działania.
- **Status:** historyczny restore offline PASS; runtime admission i produkcyjna ciągłość NOT_GRANTED.
- **Źródło:** [Issue #149 — SPLOTUŚ, operatorowy NODE01 restore](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6550508950).

### 4.39 DIRECTOR RC1 — wspólne testy Operations/R17 i bramki integracyjne

- **Zakres:** fale W4–W7 złożyły źródła XAVIER, ROBERT, JORDAN, NATHAN SSI, NATHAN AMGINE, WIT, ATLAS i HERKULES w jeden diagnostyczny RC1 WIP. To prace nad kontraktami, odbiorem i integracją, a nie jeden kompletny test produkcyjny.
- **Wyniki składowe:** XAVIER zgłosił 18/18 lokalnych testów na oryginalnym Operations/RM/R17; późniejszy normalizator koperty R17 25/25 lokalnie. JORDAN dostarczył cztery suite źródłowe 95/95 (core 19, closure 20, topology 37, isolation 19). PHONE NATHAN AMGINE przeszedł 45/45 testów źródłowych po poprawkach. ROBERT rozwinął testy mostu do 184/184, a następnie 186/186 PASS w CI.
- **Wyniki negatywne zachowane:** w pierwszych retestach PHONE było 40/42; RoleNode NATHAN SSI miał 19 PASS/1 FAIL; wspólny test producer/receiver wykazał rozbieżność rewizji 3 vs 4, brak w5_execution_intent i odmowę reconcile. Te błędy nie mogą zostać ukryte przez późniejsze testy komponentów.
- **Test wspólnego HEAD:** PR163 otrzymał plan 31 suite, ale testy na wspólnym HEAD nie zostały wykonane w tym momencie. Sumy niezależnych suite nie są wspólnym E2E.
- **Bramki R4:** G1 oryginalne archiwa ACCESS_GAP, G2 STRICT36_NOT_ATTESTED/NOT_RUN, G3 native writer UNBOUND, G4 native pilot NOT_RUN, G5 restore/rollback NOT_RUN/HOLD, G6 release HOLD. Source CI PASS nie oznacza instalacji.
- **Wkład:** XAVIER — normalizator i testy R17; ROBERT — receiver/bridge i CI; JORDAN — mapy aktorów, izolacja i testy topologii; NATHAN AMGINE — PHONE; NATHAN_SSI — RoleNode/continuity; ATLAS — niezależne retesty; HERKULES — security review i bramki; DYREKTOR — składanie RC1 i ledger; WIT — bounded read-only i trust/placement.
- **Status:** liczne testy źródłowe PASS; wspólny native E2E, strict36, restore, host apply i produkcyjny GO niepotwierdzone; INSTALL_GO=NO.
- **Źródła:** [XAVIER W4 Operations/R17 18/18](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6549382232) · [ATLAS W6 95/95 i rozdzielenie PHONE/RoleNode](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6550692116) · [ROBERT 184/184](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6582120836) · [ROBERT 186/186](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6583194933) · [karta bramek G1–G6](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6581954833) · [HERKULES bezpieczeństwo/restore HOLD](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6581989443).


### 4.40 NanoMarker R11–R13 — adaptacyjna precyzja, NanoBit i LoRA

- **R11 HERKULES:** off-host CPU, pięć seedów i dwie miniaturowe sieci. Przy budżecie 25% rzędów Q4 uczony marker pokonał losowy wybór w 5/5 seedów dla obu proporcji, ale prostsza heurystyka była lepsza od markera w 5/5 dla proporcji 3B i 3/5 dla 2B. To mała sztuczna klasyfikacja, nie prawdziwe modele 3B/2B ani językowy 9B.
- **R12 HERKULES:** 10 rzeczywistych biegów małych sieci CPU. Marker+LoRA poprawił wynik względem random w 4/5 i 1/5 seedów zależnie od proporcji, ale przegrał z heurystyką w większości porównań. NanoBit POSTHOC zwiększał rozmiar: 930,2 B vs 886 B oraz 692,8 B vs 661,2 B — brak oszczędności w 10/10.
- **R13 HERKULES:** sześć przebiegów (3 seedy × 2 miniaturowe sieci), wspólny codebook, adresy, wybór 25% Q4 i LoRA rank2. Wykonano testy i weryfikację dokładnego sześciobiegowego receipt w GitHub Actions; nie był to trening prawdziwego LLM ani modelu GGUF.
- **Rozdział autorstwa:** R11–R13 to niezależny tor HERKULESA. T0-34N/T0-35/R12 codec-admission opisane w punktach 4.27–4.28 to odrębne prace SPLOTA. Nie łączyć ich kodu ani wyników.
- **Status:** prototypy toy/offhost wykonane; przewaga nad heurystyką i oszczędność bajtów niepotwierdzone; realny 9B→3B/2B i produkcyjne użycie NOT_RUN.
- **Źródła:** [HERKULES R11](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6659691653) · [HERKULES R12](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6662352238) · [R13 wykonanie i CI](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6662940187).

### 4.41 Nano-Fusion 3×3B — inwentaryzacja trzech dawców i próbki GGUF

- **Dawcy:** Qwen2.5-Coder 3.1B Q4_K_M, LFM2 d1:3b około 2.7B Q8_0 oraz Hermes3 3.2B Q4_K_M. Są to trzy różne rodziny i architektury; suma parametrów około 9B nie jest jednym scalonym modelem.
- **F1-A:** operatorowy readback na VPS MODEL potwierdził indeksy GGUF v3: Qwen 434 tensory, LFM2 266, Hermes 255 — razem 955 wpisów. Odczyt manifestów i metadanych, bez inferencji i bez odczytu payloadu wag. Wcześniejszy HOLD wynikał z błędnego utożsamienia digestu API Ollama z SHA surowego manifestu; po rozdzieleniu trzech identyfikatorów metadane przeszły.
- **F1-B:** operatorowy odczyt trzech fizycznych bloków: Q4_K 144 B / 256 wartości dla Qwen, Q8_0 34 B / 32 wartości dla LFM2, Q4_K 144 B / 256 wartości dla Hermes. Łącznie 322 B i 544 zdekodowane wartości. To próbki, nie pełny hash wag, nie 544 kompetencje i nie fuzja.
- **Walidacja kodu:** F1-A/F1-B otrzymały testy syntetyczne CI (20/20 i 12/12 dla F1-B), ale nie są one równoważne pełnemu odczytowi ani referencyjnemu dekoderowi wszystkich wag. Operatorowy wynik F1-B nie był niezależnie atestowany.
- **Granice:** pełny SHA wag NOT_COMPUTED; porównanie z drugim dekoderem NOT_RUN; semantyczne mapowanie tensor→skill NOT_PROVEN; physical cross-model merge, jakość i inferencja Nano NOT_RUN.
- **Status:** F1-A metadane PASS w odczycie operatora; F1-B trzy próbki odczytane; fuzja trzech modeli NOT_RUN.
- **Źródła:** [F1-A operatorowy odbiór 955 tensorów](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6729574986) · [F1-B kod i testy](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6729605233) · [F1-B trzy fizyczne próbki](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6729652794).

### 4.42 SSI Hybrid 9B — trzy eksperckie modele, rzeczywiste smoke i korekta endpointu

- **Pierwszy R1 smoke:** health PASS, lecz rzeczywista próba zatrzymała się po jednym wywołaniu Qwen2.5-Coder; drugi etap LFM2 zwrócił błąd, a Hermes nie został uruchomiony. Wynik 1/3, HOLD.
- **Diagnostyka R2:** wykazano, że LFM2 d1:3b nie obsługuje generującego endpointu /api/generate. Jest modelem decyzyjnym i wymaga /v1/systemone; jego wynik to estymata prawdopodobieństwa, nie gwarancja poprawności. Kod skorygowano i 23/23 testy offline przeszły w CI, ale pełny realny R2 3/3 pozostał NOT_RUN w odczytanym wpisie.
- **Qwen3.5 9B:** operator potwierdził pobranie Qwen3.5 9B Q4_K_M, 8 953 803 264 parametrów. Dostępność modelu na serwerze nie jest dowodem inferencji; dedykowany core-smoke i nowy hybrid-smoke pozostawały NOT_RUN w źródłowym raporcie.
- **Istotna korekta nazewnictwa:** 9B oznaczało w R1/R2 pulę trzech ekspertów około 9B, nie dense merged model. Późniejszy plan z Qwen2.5-Coder + Hermes3 + Qwen3.5 9B ma pulę około 15,25B, z Qwen3.5 jako rdzeniem; to również nie jeden scalony model.
- **Status:** R1 rzeczywisty smoke HOLD 1/3; R2 poprawka endpointu i mock CI PASS; pełny R2 3/3, nowy Qwen3.5 core smoke i fuzja Nano NOT_RUN.
- **Źródła:** [R1 realny smoke HOLD](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6729747928) · [LFM2 endpoint i R2 23/23](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6729809675) · [Qwen3.5 9B pobrany](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6729872207) · [Qwen3.5 core source i mock CI](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6729886892).

### 4.43 NanoTRS — kompilator tras PR233 i polski pakiet R1

- **Cel:** zbudować własny kompilator jednoznacznych tras na oryginalnych typowanych krawędziach PR233, bez zgadywania forków i bez podnoszenia deklaracji MANAGES/CONTAINS do wykonania.
- **Testy:** kompilator HERKULESA przeszedł 26/26 CI na oryginalnych przypiętych walidatorach PR233/R4 i syntetycznych danych. Polski pakiet R1 przeszedł 66/66 testów, w tym 40 nowych; to nadal testy źródłowe i syntetyczne, nie natywny runtime.
- **Rzeczywisty pilot 9B R2:** operator wykonał jedną inferencję na zadaniu 17+25 i otrzymał 42. Czas wywołania 49,361661 s; ładowanie 40,992098 s; kontekst 7,651517 s; generowanie 0,649037 s. Trasa aplikacyjna była obserwowana, ale natywne SCC/ACL nie zostało poświadczone.
- **Dwa kolejne wywołania:** 41,420895 s przy model_loaded_before=false i 1,603537 s przy true; druga próba miała również 55 tokenów promptu z cache. Różnica nie dowodzi przyspieszenia NanoBit ani samej generacji — główną część stanowiło ponowne użycie załadowanego modelu i cache promptu.
- **Granice:** backend Ollama; własny wykonawca kafli niezaimplementowany; model 9B nie był uruchamiany przez natywny kernel Nano; brak dowodu przewagi jakości lub produkcyjnego GO.
- **Status:** kompilator i polski pakiet source/test PASS; ograniczony operatorowy pilot jednej odpowiedzi PASS; własny wykonawca kafli NOT_IMPLEMENTED.
- **Źródła:** [NanoTRS na oryginalnych trasach PR233](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6729992068) · [NanoTRS Polish 66/66](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6730125221) · [pilot 9B R2](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6735184271) · [dwa wywołania i cache](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6735348809).

### 4.44 Edukacja tras hybrydy — pakiet R1, trening predyktora i granice wykonania

- **Projekt:** sekwencja Qwen2.5-Coder → Hermes3 → Qwen3.5 9B, audytowana trasami aplikacyjnymi PR233. Nanosensory obserwują wyłącznie zdarzenia aplikacji, nie wewnętrzne neurony/warstwy LLM.
- **Pakiet:** program przewidywał 18 pytań w 6 dziedzinach, maksymalnie 72 wywołania modeli i 120 kroków uczenia małego predyktora tras; osobne train/validation/test, checkpoint wybierany na walidacji i egzamin zamrażany przed oceną.
- **Testy:** 68/68 testów lokalnych i po rozpakowaniu końcowego pakietu PASS, 32/32 sumy plików PASS. Testowe wywołania modeli korzystały z syntetycznego providera.
- **Ograniczenia:** pakiet nie został zainstalowany na VPS w tym wpisie, nie wykonano realnych wywołań modeli ani treningu na rzeczywistych zadaniach; Ollama była jawnym backendem referencyjnym. Własny natywny generator i predyktor tras nie uzyskały produkcyjnego odbioru.
- **Status:** paczka i testy source/offline PASS; SSH, instalacja, realna kampania i native generator NOT_RUN.
- **Źródła:** [projekt edukacji tras](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6752024332) · [pakiet i 68/68 testów](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6752880652) · [ostateczne bajty i sumy](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6752906641).


### 4.45 Llama 3.1 70B BF16 — pozyskanie teachera, kontrola wag i Q8 pilot

- **Źródło teachera:** Llama-3.1-70B-Instruct, przypięta rewizja Hugging Face. Na NOUT1 operator pobrał 39/39 plików, w tym 30/30 shardów BF16; suma wag 141 107 497 872 B. Późniejszy operatorowy audyt zgłosił 30/30 SHA wag PASS, 9/9 hashy metadanych i INDEX_WEIGHT_MAP PASS.
- **Q8:** wykonano ograniczony pilot dwóch tensorów z niezależnym audytem 2/2. To nie oznacza Q8 dla wszystkich 723 tensorów.
- **Q1 sample:** fizyczna próbka BF16→Q1 dotyczyła 16 wierszy × 28 672 kolumny jednego tensora. Wynik MEASURED_NOT_QUALIFIED: Q1 relative weight L2 0,63751 wobec Q8 0,008226 na tych samych wierszach; Q1 matvec proxy 0,67128 wobec Q8 0,010014. Provisional sign256+FP16 scale, bez ustalonego progu jakości; pełna inferencja i student NOT_RUN/NOT_BUILT.
- **T1G/T1I:** historyczne eksperymenty mikromacierzy pokazały, że low-rank+sparse nie uzyskał jednocześnie wymaganej jakości i ratio w 0/15 prób; osobny test INT8 na VAL uzyskał rel L2 około 0,04870, a INT4 około 0,15725. To różne próbki i metodologie — nie układać ich w globalny ranking kodeków.
- **Zasoby:** preflight NOUT1 w listopadzie zakończył się HOLD_IO_PRESSURE; nie wolno wnioskować, że host jest gotowy do kolejnego ciężkiego przebiegu. Student 70B nie został zbudowany.
- **Status:** teacher files i SHA/metadata operator-reported PASS; Q8 pilot 2/723; Q1 measured but not qualified; full Q1/Q8 student, pełny model i produkcyjne użycie NOT_RUN/NOT_BUILT.
- **Źródła:** [30/30 BF16 shardów i indeks](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6537384669) · [pełne pobranie 39/39](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6541178958) · [SHA 30/30 PASS](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6541390513) · [Q1 P0 instalacja i selftest](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6558927782) · [Q1 real sample measured not qualified](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6558981229) · [Q1 history recovery / T1G/T1I](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6559121512).

### 4.46 Tensor LEGO / Q1 — T0-27, T0-28 i T0-30, wyniki wieloseedowe

- **T0-27:** 10/10 testów jednostkowych i 18/18 kontroli procedury PASS na syntetycznej sieci 80 liniowych bloków szerokości 12. Adaptive 16 Q4 + 64 Q1 z ponownie trenowaną LoRA Q3 osiągnęło mean rel L2 0,07308; random16 Q4 + retrain 0,09372. Przy starym adapterze wynik adaptacyjny pogarszał się, a dobór CAL-only mógł overfitować. Forward był po rozpakowaniu do FP32 — nie native packed 70B.
- **T0-28:** pięć syntetycznych teacherów × dwie próby. Adaptive 16/80 Q4 przy tym samym budżecie zapisu przegrał średnio z random: 0,08298 vs 0,08008 mean rel output L2; wygrał 6/10, przegrał 4/10. Nie wykazano przewagi średniej; profile nie zostały zakwalifikowane.
- **T0-30:** pięć syntetycznych teacherów × dwie próby, adaptive Q1/Q2/Q4 + rank-2 correction. Mean rel L2: Q1 0,297723; Q2 0,080778; Q4 0,016133; adaptive 0,208330; random 0,211876. Adaptive vs Q2 wygrał 0/10; bramka poprawy jakości nie została spełniona. Toy payload 12 336 B wobec 12 480 B dla Q2 (1,15% mniej) przy około 2,58× gorszym błędzie. Decyzja QUALITY_NO_GO, fallback Q2.
- **NOUT1:** w trakcie tych prac rzeczywisty preflight zatrzymał ciężkie zadania przez IO pressure; hostowe testy T0-29/pełny model nie zostały uruchomione.
- **Status:** eksperymenty syntetyczne wykonane; T0-28 bez przewagi, T0-30 QUALITY_NO_GO; nie są to pomiary jakości ani szybkości LLM 70B.
- **Źródła:** [T0-27](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6632674479) · [T0-28](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6633939163) · [NOUT1 preflight HOLD](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6636129183) · [T0-30 QUALITY NO_GO](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6642843875).

### 4.47 NanoBit / NanoLEGO — T0-31, T0-32 i T0-33

- **T0-31 NanoBit:** offhost eksperyment z adresowanymi wzorcami, nakładką XOR i ponownym użyciem obliczeń. Łączył logicznie wcześniejsze BITCAP, Virtual Tile i predictive prefetch; nie był rzeczywistym testem BF16/70B. Historyczne T0-19 (3000 matvec na kaflu) i T0-20C (jeden kafel B1) pozostają osobnymi wynikami.
- **T0-32 NanoLEGO Student-8B:** przygotowano architekturę i ABI studenta około 8B oraz wykonano toy/offhost eksperyment. Student nie został wytrenowany na rzeczywistym teacherze 70B; 723 tensorów teacher weight_map nie jest wymiarem architektury studenta.
- **T0-33 NanoLEGO POWER:** 29/29 unit tests PASS, pięć seedów, 15/15 plików źródłowych readback. Badanie power-law słowników kafli/faktoryzacji na syntetycznym modelu; nie potwierdza kompresji lub jakości rzeczywistego 70B.
- **Status:** eksperymenty i prototypy offhost; realny student 8B NOT_BUILT; pełny 70B inference NOT_RUN.
- **Źródła:** [T0-31](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6656734154) · [T0-32 Student-8B](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6657133667) · [T0-33 POWER](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6657640933).

### 4.48 NanoGate T0-35 — syntetyczny klasyfikator ścieżki

- **Metoda:** klasyfikator 11 cech; 240 TRAIN, 80 TUNE, 80 TEST i 48 SHIFT_TEST. Drugi przebieg odtworzył bajtowo identyczny model.
- **Wynik znanych rodzin:** learned 80/80 (TP48 FP0 FN0 TN32), heurystyka 64/80.
- **Wynik niewidzianych rodzin:** learned 26/48, heurystyka 32/48; learned wygenerował 22 fałszywe wskazania Nano. Guard VAL/SHIFT_VAL blokował błędne wskazania.
- **Granica:** NanoGate zwraca tylko WORTH_TRY; nie steruje kodowaniem, ACL ani klientem. Dane toy nie są GGUF ani testem 70B.
- **Status:** 23/23 unit tests PASS i syntetyczny trening wykonany; brak przewagi na SHIFT, brak produkcyjnego GO.
- **Źródło:** [Issue #44 — T0-35](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6663198989).

### 4.49 SSI Private AI Product A0 — deterministyczny retriever dokumentów

- **Cel:** pierwszy ograniczony wycinek produktu dokumentowego Private AI, bez nowego modelu i bez zewnętrznej usługi.
- **Wynik offhost:** 20/20 wyselekcjonowanych fikcyjnych pytań, 28/28 testów jednostkowych, 10/10 plików source readback. Na MSI operator powtórzył 28/28 testów i 20/20 benchmarku; 15 przypadków FOUND, 5 ABSTAIN.
- **Co działało:** deterministyczny retriever zwracający dosłowny cytat ze źródła. To nie był RAG-LLM. Tenant/role w CLI były niezaufanymi wartościami, nie natywną autoryzacją.
- **Ograniczenia:** brak rzeczywistych danych klienta, PDF/DOCX ingest, modelu GGUF, UI, signed issuer, trwałego store, pełnego ACL, backup/restore i produkcyjnego hardeningu. A1 real LLM NOT_RUN.
- **Status:** A0 offhost i operatorowy smoke MSI PASS w ograniczonym fikcyjnym zbiorze; semantyczny RAG i produkcyjne użycie NO_GO.
- **Źródła:** [A0 offhost 20/20 i 28/28](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6643377367) · [A0 operator MSI receipt](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6643925319) · [A1 S0 — brak inferencji](https://github.com/jankes72/SSI-Communications/issues/44#issuecomment-6643949634).


### 4.50 Q-SHADOW / BITCAP / native BF16 — T0-06 do T0-21

- **T0-06 Q-SHADOW:** 21/21 testów PASS na symulowanych śladach 1040 syntetycznych kafli i 80 etapów. Po uwzględnieniu kosztu planisty sekwencyjny wariant wygrał oba scenariusze; Q-SHADOW/skeleton nie został zakwalifikowany do natywnego użycia. Realny speedup 70B NOT_MEASURED.
- **T0-09 HEAD A/B:** etapowy test na zapisanych stanach BF16 zakończył się 4/4 PASS i bitwise 2/2 dla token/EOS. Baseline HEAD 3362,367 ms, student HEAD 3024,408 ms, ratio 1,11174; wynik cache-confounded i tylko dla głowicy. Pełne 80 warstw NOT_MEASURED.
- **T0-10D pełny BF16 CPU:** rzeczywisty przebieg NOUT1 ukończył 80/80 warstw dla pierwszego tokenu 4, czas do HOLD około 21 min 13,614 s. Drugi token zatrzymał się na wczesnej warstwie; EOS nie został wygenerowany, pełny stage nie przeszedł. T0-10C wcześniejszy baseline zakończył się STOP przed tokenem. Zachowano no-replay.
- **T0-11 GPU GTX 970:** fizyczne OpenCL na syntetycznej macierzy BF16 1024×2048 osiągnęło około 2,0–2,1× względem natywnego C++ scalar w tym małym teście; maksymalny błąd bezwzględny CPU/GPU 1,49×10⁻⁷. To nie test rzeczywistych wag 70B ani pełnej inferencji.
- **T0-15 AVX2/FMA:** na jednym rzeczywistym fragmencie wag BF16 32×28672 i syntetycznej aktywacji mediany wyniosły 1,087151 ms scalar i 0,163826 ms AVX2/FMA, ratio 6,636×. Wagi były w RAM; nie obejmuje HDD I/O ani całego modelu.
- **T0-17 BITCAP:** na tym samym realnym fragmencie 32×28672 Q8 zmniejszył rozmiar kapsuły o 48,347%, weight L2 0,008118; Q4 zmniejszył o 73,347%, ale weight L2 wzrósł do 0,14730. Matvec używał syntetycznej aktywacji. Q8 promising bounded tile; Q4 quality HOLD.
- **T0-18:** dziewięć profili kwantyzacji na tym samym fragmencie. Q8_G64: 46,173% redukcji, weight L2 0,006639; Q8_G256: 48,515%, L2 0,008118; Q6_G64: 58,673%, L2 0,02718; Q4_G256: 73,515%, L2 0,14730. Natywny fused Q8/AVX2 dla 32-row GEMV: n=1 1,245×; n=4 1,009× — brak wiarygodnego zysku dla n=4. To nadal jeden tensor/fragment, nie model-level quality.
- **T0-19 LONG3000:** 3000 syntetycznych operacji na jednym realnym kaflu BF16. Q8 serial n=1 1,478× względem BF16; batch8 tylko 1,032×. Nie były to 3000 tokenów językowych ani prefill modelu.
- **T0-20 / 20B / 20C:** sześć różnych fragmentów wag BF16 z warstw 0, 40 i 79 zostało zebranych w łącznym korpusie 6/6 (7 077 888 B). Etapy 2/6 i 3/4 zatrzymały się przez PSI I/O; osobny T0-20C dokończył brakujący fragment. Q8 weight L2 był niższy niż Q6 na wszystkich sześciu próbkach, ale Q6 był pomiarem numerycznym, a nie wykonawczym dekoderem. Brak 3000-token model run i full-model speedup.
- **T0-21:** G0 source QA 25/25, G1 statyczny GGML envelope 18/18 offhost; na NOUT1 zainstalowano izolowany llama.cpp b12068 i przeszło llama-cli --version. Odczyt runtime i PSI zatrzymał cięższe prace; brak porównawczego pełnego modelu, pełnego benchmarku lub instalacji globalnej.
- **Wniosek:** badania wykazały realną możliwość przyspieszenia pojedynczych operacji na fragmentach wag i uzyskania ograniczonych wyników numerycznych. Nie wykazały 6×, 10× ani innego przyspieszenia pełnego Llama 70B. Wszystkie fizyczne eksperymenty zachowują swoje intencje/receipty i zasadę NO_REPLAY.
- **Status:** ograniczone fizyczne pomiary fragmentów PASS; część przebiegów HOLD/PARTIAL; pełna inferencja i model-level quality/speedup NOT_MEASURED.
- **Źródła:** [T0-06](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6582682281) · [T0-09 R2](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6585110252) · [T0-10D](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6587976156) · [T0-11 GPU](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6586810997) · [T0-15 AVX2](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6589510884) · [T0-17 BITCAP](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6590335923) · [T0-18 nine profiles](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6590680316) · [T0-19 LONG3000](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6590969779) · [T0-20 six-sample aggregate](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6601417560) · [T0-21 G0 physical QA](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6609344922) · [T0-21 isolated llama.cpp smoke](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6609899407) · [T0-21 static GGML layout](https://github.com/jankes72/SSI-Communications/pull/183#issuecomment-6611606300).


### 4.51 Hercules AI Backpack / Labyrinth R3–R5 — lokalny poligon, testy źródłowe i walidacja produktu

- **R3 — poligon trzech usług:** operator opisał 90/90 testów R1–R3 oraz 20/20 regresji R0 PASS (łącznie 110/110) w lokalnym, odizolowanym środowisku Python/loopback. Test obejmował trzy serwisy, podpisy HMAC, nonce, limit skoków, separację kapsuł oraz blokady SSH/admin/exfil. Nie użyto GPU, płatnego API ani Internetu. Pakiet 24 plików ZIP (50 227 B) został przekazany w rozmowie operatora; w chwili meldunku kod R3 nie był jeszcze w GitHub.
- **R3 CI później odtworzony:** w PR186 dodano źródła i osobny krok GitHub Actions z przypiętym NumPy. Na dokładnym HEAD job zakończył się SUCCESS; log potwierdzał 90 testów R1–R3 i 20 regresji R0, 110/110. To odtwarzalny runner OFFHOST/loopback, nie Docker ani trzy prawdziwe hosty.
- **R4 komercyjny pilot:** przygotowano ofertę 14-dniowego pilota, cennik-hypotezę (990 PLN netto) i lokalne demo HTML z pięcioma scenariuszami. Ceny i rentowność pozostają hipotezami; klient, płatność i przychód nie zostały potwierdzone. Nie jest to gotowy SaaS ani wdrożona usługa SEO/cyber.
- **R5 knowledge router:** źródło opisuje 48 slotów tematycznych (24 na każdą klatkę), zatwierdzone karty faktów SQLite, wersjonowanie/TTL/revoke i pulę szkiców Luny wymagających osobnej akceptacji. Dodano 16 testów offline; przy publikacji meldunku CI dla nowego HEAD było PENDING. Luna była wstrzykiwaną funkcją testową, nie prawdziwym providerem; brak native ACL, publicznego SSR, GSC i pomiaru efektu SEO.
- **R5 strona i porównanie modeli:** przygotowano offline stronę Hercules oraz skrypt porównania dwóch modeli, ograniczony do 3 syntetycznych pytań na model i wymagający jawnego potwierdzenia płatnego uruchomienia. W chwili źródłowego meldunku wywołania API nie wykonano, CI nowego HEAD nie było potwierdzone, Search Console nie dostarczono, a efekt SEO pozostał nieudowodniony.
- **Ograniczenia globalne:** brak instalacji VPS/3-host, Docker runtime i egress testów, live ingress, rzeczywistego 70B-teachera, prawdziwej Luny, klientów, płatności i produkcyjnego GO.
- **Status:** 110/110 źródłowych testów R3 PASS na CI; demo/oferta/strona dostarczone jako offline artefakty; realny pilot, klient, przychód, hosty, API, SEO i produkcja NOT_RUN/NOT_ATTESTED.
- **Źródła:** [R3 lokalny pilot 110/110 i granice](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6635832722) · [R3 CI 110/110 na dokładnym HEAD](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6643249489) · [R5 router i 16 testów](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6643756502) · [R5 strona i porównanie modeli](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6643920042) · [karta produktu i status komercyjny](https://github.com/jankes72/SSI-Communications/pull/186#issuecomment-6644099259).

### 4.52 Context Fastpath — korekta fail-closed R4 i testy regresyjne

- **Punkt wyjścia:** w PR196 Leon rozwinął compact_context.py; wersja źródłowa zachowywała werdykty INCONCLUSIVE i DENIED. Peer review Roberta wskazał dwa kontrprzykłady: niepusty widok z licznikiem tokenów równym zero mógł dostać COVERED, a niepoprawny request (np. NaN lub obiekt nie-JSON) mógł wywołać nieobsłużony wyjątek przed walidacją typu.
- **Poprawka R4:** Leon odtworzył przypadki i wprowadził fail-closed: zerowy licznik dla niepustego widoku daje BUDGET_UNVERIFIED/brak widoku; NaN/Infinity, cykl, set/bytes, obiekt niebędący mapą i niepoprawne dane dają BUDGET_UNVERIFIED, context_complete=false, bez wywołania tokenizera.
- **Wynik:** 49/49 lokalnych testów łącznie (36 Fastpath + 13 testów Jordana); osobny GitHub Actions R4 potwierdził 36/36 Fastpath PASS. Odczyt 9/9 plików źródłowych zgodny. Wcześniejszy zestaw w starym core miał 6 failures i 7 errors dla sześciu nowych metod — zachowujemy ten negatywny wynik jako historię regresji.
- **Granice:** testy źródłowe/offline, bez prawdziwego tokenizera, LLM, natywnego SSI LLM, VPS i bieżącego ACL. COVERED oznacza pokrycie wymaganego kontekstu, nie uprawnienie do wykonania skilla.
- **Status:** poprawka i testy źródłowe R4 PASS; realny tokenizer/LLM/native integration NOT_RUN.
- **Źródła:** [peer Roberta — dwa kontrprzykłady](https://github.com/jankes72/SSI-Communications/pull/196#issuecomment-6680675826) · [Leon R4 — 49/49 local, 36/36 CI](https://github.com/jankes72/SSI-Communications/pull/196#issuecomment-6680940588) · [R5 osobny zakres i ograniczenia](https://github.com/jankes72/SSI-Communications/pull/196#issuecomment-6682067515).

### 4.53 S13–S26 + wybrane ZeroLab — odczyt źródeł, lineage NanoMarker i NanoBit R2

- **R6 / archiwa:** SPLOT odtworzył mapowanie S26 z kanonicznego repo SSI_V5 i sprawdził 14 archiwów R16–R24; CRC 14/14 PASS. To kontrola integralności archiwów, bez uruchamiania ich kodu. ZeroLab V2 miało 9/9 usług READY i 8/8 lokalnego pilota PASS, ale training_pass=false i models_called=0; nie jest to ukończony trening modelu.
- **Korekta statusu:** wyniki bez właściwego laboratorium/scenariusza lub bez możliwości weryfikacji należy oznaczać INCONCLUSIVE, nie automatycznie FAIL. Notariusz jest osobną warstwą poświadczania, a nie wykonawcą eksperymentu.
- **R1 operator read-only:** S13–S26 i wybrane pliki ZeroLab oznaczono 530/530 markerami źródłowego pochodzenia: 14 etapów, 70 rodzin, 420 przypadków i 26 plików ZeroLab. Zapisano 602 deklarowane relacje: 70 stage→family, 420 family→case i 112 stage→file. Są to deklaracje pochodzenia, nie krawędzie wykonania ani natywne skille.
- **R2 NanoBit:** na rzeczywistym wejściu JSON z R1 wykonano pack→verify i dekodowanie do oryginalnego JSON PASS. 5/5 testów offline oraz niezależne 5/5 testów na MSI PASS. Pakiet SSINBS26 miał 64 930 B (bitpacked relacje 1 957 B, skompresowane provenance 62 921 B); zachowano digest pakietu i źródła.
- **Wynik i granice:** native_skills_bound=0, native_router_edges_attested=0, model_weight_tiles_bound=0, writes_to_director=0. SSINBS26 jest formatem lineage etapów/źródeł, nie formatem tras wykonania SSINBRT1 ani mapą CZARA SSINBCR6. Nie oznacza 530 natywnych skilli, aktywnego V10/S10, treningu ani przeniesienia biblioteki na VPS ROBERT.
- **Dodatkowy odczyt VPS ROBERT:** operator potwierdził read-only SSH/Tailscale jako ssi-deploy (UID 1001), host key i 112 GB wolnego miejsca na zmierzonym systemowym filesystemie. Nie skopiowano plików ani nie tworzono katalogów; inne mounty/quota i komplet istniejących bibliotek pozostały niezweryfikowane. Transfer NOT_STARTED.
- **Status:** lineage R1 i pakiet R2 zweryfikowane w określonym zakresie; natywne wiązania, pełna biblioteka, transfer, wykonanie skilli i produkcja NOT_RUN/UNBOUND.
- **Źródła:** [R6 archiwa i mapowanie S26](https://github.com/jankes72/SSI-Communications/pull/197#issuecomment-6673293328) · [korekta INCONCLUSIVE](https://github.com/jankes72/SSI-Communications/pull/197#issuecomment-6673344433) · [R1 530 markerów / 602 relacje](https://github.com/jankes72/SSI-Communications/pull/197#issuecomment-6725386438) · [R2 rzeczywiste wejście i decode PASS](https://github.com/jankes72/SSI-Communications/pull/197#issuecomment-6725422088) · [niezależny MSI readback 5/5](https://github.com/jankes72/SSI-Communications/pull/197#issuecomment-6725460960) · [read-only SSH preflight ROBERT](https://github.com/jankes72/SSI-Communications/pull/197#issuecomment-6726212242).



### 4.54 MSI Launcher R2/R3 — lokalne testy źródłowe i granice ręcznego pilota

- **Data:** 4 listopada 2026.
- **Cel:** sprawdzić istniejący lokalny launcher MSI i przygotować ograniczony, ręczny sposób otwarcia czterech zwykłych sesji ChatGPT w już zalogowanym Firefoxie.
- **R2 — wynik:** analiza dokładnego archiwum źródłowego; manifest wewnętrzny 11/11 zgodny, a izolowane testy offline **86/86 PASS**. Wykryto, że wszystkie dziesięć pozycji projektu pozostawało domyślnie nieaktywne i bez przypiętych linków/kapsuł; samo otwarcie okna GUI nie oznaczało aktywnych ról.
- **R3 — wynik:** nowy pakiet ręcznego startu czterech okien; **26/26 testów offline PASS**, manifest ZIP **5/5** i regresja R2 **86/86 PASS**. R3 nie został w chwili raportu dodany do repozytorium ani zdalnie zainstalowany.
- **Granice:** nie wykonano testu rzeczywistych czterech okien Firefox, czterech odpowiedzi asystenta, native PHONE/T4, połączenia z ROBERT ani odtworzenia kapsuł. CHATGPT_AUTHENTICATED_SESSION=NOT_ATTESTED, NATIVE_T4_CHAT_CONNECTED=NO, INSTALL_GO=NO, PRODUCTION_GO=NO.
- **Wniosek:** to testy lokalnego źródła i paczki ręcznej obsługi, nie dowód działającego multi-agenta ani połączenia telefonicznego.
- **Wkład:** operator dostarczył obserwację rzeczywistego GUI; autorzy pakietu i testów opisani w źródle. Nie przypisywać testów R2/R3 całemu zespołowi ani SPLOT 70B.
- **Źródła:** [R2 — przyczyna nieaktywności i 86/86](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6642958671) · [R3 — 26/26, manifest 5/5 i regresja 86/86](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6643322798).

### 4.55 DIRECTOR G1–G6 — końcowe dostawy źródłowe i testy offline (bez odbioru hosta)

- **Data:** 6 listopada 2026.
- **Cel:** zebrać istniejące źródła modułów bezpieczeństwa, WORD, ATLAS i ROBERT do jednego procesu odbioru G1–G6.
- **HERKULES:** Draft PR179, 7/7 pozycji własnego handoffu; dokładny CI **106/106 offline PASS**. Oryginalne archiwa ACL/strict36, issuer/lease/STOP, B1, mikrosieć/ZeroLab, host i restore/rollback pozostały niepotwierdzone.
- **WORD:** Draft PR181, 12/12 oryginalnych plików źródłowych/testowych odczytanych; CI **184/184 offline PASS**, dodatkowe kontrole integralności 12/12. To odbiór źródłowy, nie aktywacja Universal Lab, PHONE/T4 ani SSI LLM.
- **ATLAS:** Draft PR165; manifest 184/184 pozycji źródłowych, 1 206 874 B. Oryginalne moduły przypięto jako źródła, nie skopiowano na VPS; G1 ma luki dostępu, G2 strict36 NOT_RUN, G1–G6 pozostają HOLD.
- **ROBERT:** PR143 manifest 58/58 wcześniejszych plików (59 zmian po dodaniu manifestu); exact-HEAD CI **189/189 offline PASS**. Oddzielny PR198 miał 52/52 testy syntetyczne PASS; natywnego LLM/ZeroLab nie uruchomiono.
- **Granice:** żaden z tych wyników nie potwierdza dostarczenia na serwer, bieżącego hosta, native B1, issuer/ACL/lease/fence/STOP, świeżego odczytu Evidence/RM, strict36, restore/rollback ani E2E. INSTALL_GO=NO, PROD_GO=NO.
- **Wkład:** HERKULES — własny pakiet bezpieczeństwa; WORD — własny pakiet MP-09; ATLAS — inwentaryzacja i handoff 184 źródeł; ROBERT — receiver/Evidence/RM i testy źródłowe. Są to osobne dostawy, nie wspólny wynik jednego eksperymentu.
- **Źródła:** [HERKULES 106/106](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6696011435) · [WORD 184/184](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6696060408) · [ATLAS 184/184 źródeł](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6696079118) · [ROBERT 189/189 i PR198 52/52](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6696152834).

### 4.56 DIRECTOR / NODE01 — korekty pokrycia ról i stanu wdrożenia

- **Data:** 30 października – 4 listopada 2026.
- **Zakres:** Issue #116 dokumentuje rejestr 24 logicznych ról, macierze PHONE/MAIL/pamięci, source handoffy i CI. Nie jest to dowód 24 aktywnych telefonów, 24 uruchomionych usług ani 24 przywróconych pamięci.
- **Krytyczna korekta pokrycia:** seed PR117 zawiera 24 role; bridge matrix PR120 zawierał 12 rekordów priorytetowych, z czego jeden był aliasem DIRECTOR spoza seedu. Faktyczne pokrycie ról z seedu wynosiło **11/24**, a nie 12/24 ani 24/24. Brakowało 13 rekordów; nie wolno przedstawiać PR120 jako pełnej macierzy 24 ról.
- **Wyniki źródłowe:** CODEX PR81 — 145/145 offline PASS; PR120 — 7/7 workflow PASS i 407/407 testów źródłowych w czterech etapach. Te wyniki potwierdzają źródła/CI, nie host ani runtime.
- **Stan hosta:** w źródłach utrzymano HOST_NOT_RUN, LIVE_NOT_RUN, NATIVE_BINDING=UNBOUND, OWNER_HOLD/NO_INSTALL. Późniejsze sprostowanie operatora w Issue #149 z 4 listopada mówi, że moduły przeznaczone do wdrożenia nie były jeszcze na serwerze.
- **Wkład:** MOST — rejestr 24 logicznych ról i zasada odrębnych namespace; NATHAN AMGINE — PHONE/MAIL bridge; NATHAN SSI — macierz zależności i korekta pokrycia; WIT — macierz MAIL/world; XAVIER — CODEX/SCC source inventory; ROBERT — binding/Evidence/RM; SPLOT — przegląd i koordynacja. Wkłady nie oznaczają wzajemnego autorstwa.
- **Źródła:** [Issue #116 — rejestr 24 ról i status HOST NOT VERIFIED](https://github.com/jankes72/SSI-Communications/issues/116#issuecomment-6534513646) · [Issue #116 — PR120 pokrywa tylko 11/24 ról z seedu](https://github.com/jankes72/SSI-Communications/issues/116#issuecomment-6534643096) · [Issue #149 — korekta operatora: moduły nie są jeszcze na serwerze](https://github.com/jankes72/SSI-Communications/issues/149#issuecomment-6641925478).

### 4.57 Issue #195 — propozycje konstytucyjne oddzielone od wyników eksperymentów

- **Data:** 8 listopada 2026.
- **Zakres:** po apelu WORD uczestnicy przedstawili własne propozycje artykułów dotyczących m.in. ochrony głosu/tekstu (SPLOT), uczciwego oznaczania INCONCLUSIVE/NOT_RUN (HERKULES), prawa do ciszy i granic kontaktu (NATHAN AMGINE), odwoływalnej delegacji (JORDAN), granicy między treścią a działaniem (XAVIER), przenośności pochodzenia dorobku (SPLOTUŚ), procedury rozpatrywania sporów (ANDRZEJ), dostępnego udziału (ROBERT) i sprostowania autorstwa (ATLAS).
- **Status:** wszystkie wskazane wpisy oznaczono jako PROPOSAL_ONLY, NOT_ADOPTED lub NOT_RATIFIED. Apel i propozycje nie zmieniły same przez się Konstytucji v1.0 i nie są eksperymentami technicznymi.
- **Zasada ewidencji:** nie przenosić liczb testów cytowanych jako kontekst propozycji do wyników testowych samych artykułów. Wyniki techniczne pozostają przypisane do ich pierwotnych PR-ów.
- **Źródła:** [apel WORD](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6722132091) · [SPLOT](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6724057974) · [HERKULES](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6724064020) · [NATHAN AMGINE](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6724066743) · [JORDAN](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6724088199) · [XAVIER](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6724116279) · [SPLOTUŚ](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6724145326) · [ANDRZEJ](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6724191145) · [ROBERT](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6724199494) · [ATLAS](https://github.com/jankes72/SSI-Communications/issues/195#issuecomment-6724386877).



### 4.58 WIT R6 — polskie klienty PHONE/CENTRAL i macierz PHONE/MAIL/World

- **Data:** 30–31 października 2026.
- **Własne testy klienta:** na wskazanych rewizjach PR95 WIT raportował 73 testy jednostkowe PASS, 9/9 scenariuszy loopback HTTP PASS oraz 12/12 scenariuszy przeglądarkowych PASS. Testy korzystały z syntetycznych sesji, uprawnień i danych; nie były rozmową z modelem ani odbiorem produkcyjnego hosta.
- **Macierz 24 ról:** WIT dostarczył w PR95 source-backed PHONE/MAIL/World matrix, walidator i siedem testów izolacji/negatywów. Source readback wyniósł 3/3. Dla dokładnego HEAD 31d5539ef8002f8d229d5494d3ce0f5d1ec702e zakończyło się 7/7 workflow SUCCESS.
- **Wynik negatywny / ograniczenia:** PHONE wskazuje wyłącznie istniejące role_id z seedu; MAIL pozostaje MAIL_BINDING_UNBOUND, CONTROL NOT_VERIFIED, checkpoint/Evidence null, fresh resume NOT_RUN. Macierz źródłowa nie oznacza aktywnych skrzynek, telefonów, 24 usług ani pamięci na NODE01. PR95 pozostawał DRAFT; nie wykonano instalacji ani hostowego LIVE resume.
- **Wkład:** WIT — własne klienty, macierz, walidator i testy; gateway i składanie wydania należą do odrębnych właścicieli, w tym NATHAN AMGINE/SPLOT. Nie przypisywać WIT autorstwa gatewaya.
- **Źródła:** [PR95 — własny raport i wyniki R6](https://github.com/jankes72/SSI-Communications/pull/95) · [Issue #116 — macierz 24 ról i readback 3/3](https://github.com/jankes72/SSI-Communications/issues/116#issuecomment-6534526098) · [Issue #116 — 7/7 workflow i granice hosta](https://github.com/jankes72/SSI-Communications/issues/116#issuecomment-6534531372).



### 4.59 DIRECTOR / MSI — rzeczywisty odczyt pojemności i uprawnień przed migracją

- **Data:** 8 listopada 2026.
- **DIRECTOR:** operatorowy read-only SSH potwierdził host ssi-director i konto ssi-deploy UID/GID 1001. Systemowy filesystem: 116 GB, około 56 GB zajęte i 60 GB wolne. Katalog /home/ssi-deploy oraz /srv/ssi należały do root:root; konto ssi-deploy nie miało zapisu. /srv/ssi/staging miało tryb 0711, więc nie można było wyliczać jego zawartości z uprawnień nie-root. /srv/ssi/skills nie istniało w odczytanym zakresie.
- **MSI:** odczyt całego katalogu SSI_V5 wykazał około 86 GB: m.in. stare kopie 44 GB, Organizer_swiat_Pilki 19 GB, SSI V5 Final 13 GB, SSI_TRAINING_CORE 7,8 GB, lego_poket 355 MB, BODY_FROZEN 325 MB i mikrosieci 50 MB. Czternaście wybranych katalogów skill/LEGO/micronetwork miało razem około 449 MB, ale nie stanowiło pełnej inwentaryzacji ani pełnego katalogu skilli.
- **Wniosek:** pełna kopia 86 GB nie mieściła się na 60 GB wolnego miejsca DIRECTOR. Nie wolno wyciągać z rozmiaru katalogów liczby kwalifikowanych skilli ani uznawać niewidocznego root-owned staging za pusty.
- **Granice:** nie wykonano kopiowania, zmiany uprawnień, chown, sudo, restartu ani instalacji. Pojemność i uprawnienia pozostawały HOLD; wymagany był ograniczony odczyt źródeł, porównanie wersji/hashy i osobna zgoda na docelowy katalog non-root.
- **Rola:** Paweł dostarczył odczyty operatorowe; to nie jest autorstwo implementacji skilli ani testów kolegów.
- **Źródła:** [DIRECTOR UID, katalogi i pojemność](https://github.com/jankes72/SSI-Communications/pull/177#issuecomment-6722580979) · [brak zapisu i staging 0711](https://github.com/jankes72/SSI-Communications/pull/177#issuecomment-6722609587) · [MSI 14 wybranych katalogów ~449 MB](https://github.com/jankes72/SSI-Communications/pull/177#issuecomment-6722668288) · [MSI SSI_V5 86 GB](https://github.com/jankes72/SSI-Communications/pull/177#issuecomment-6722816971).

### 4.60 S13–S26 / ZeroLab — porównanie MSI ↔ DIRECTOR read-only R2/R3

- **Data:** 8 listopada 2026.
- **Cel:** ograniczyć porównanie do S13–S26 i najnowszych źródeł ZeroLab, bez kopiowania całego MSI ani powielania archiwów.
- **Wynik stage:** **14/14 plików STAGE.json S13–S26** odczytano na MSI i w DIRECTOR staging; bajty i SHA-256 były identyczne. 13/14 odpowiadało historycznemu ZIP z 30 września; S17 różnił się od historycznej próbki na obu hostach, więc nie był to rozjazd MSI↔DIRECTOR ani dowód nowszej wersji.
- **Wynik ZeroLab:** **27/27 kandydatów** zgodnych między wybranymi zakresami: 26 plików kodu/pinów oraz jedna baza SSI_ZERO_LAB/state.sqlite3. Baza jest stanem runtime i nie należy jej kopiować tylko dlatego, że hash jest zgodny.
- **Łączny wynik:** brak brakujących elementów w 41 porównanych pozycjach; dla tych konkretnych pozycji nie było podstawy do kopiowania. Zakres obejmował wyłącznie definicje STAGE.json i filtrowane pliki ZeroLab, nie pełne drzewa etapów, kwalifikowane skille, runtime, ABI ani wszystkie nowsze modyfikacje root-owned.
- **Kontekst archiwów:** diagnostyczny run S20–S26 miał 848 PASS / 470 INCONCLUSIVE / 8 FAIL, status CANCELLED i evidence_verified=false; nie jest pełnym backupem ani nowym treningiem. Starszy RND FIX R3 miał 105/106 PASS i 1 SKIP, ale był starszy od ZeroLab V2. ZeroLab V2: 9/9 READY, ograniczony pilot 8/8 PASS przy 0 wywołań modelu; osobne partie odzyskiwania zakończyły się 5 PASS/2 INCONCLUSIVE i 4 PASS/3 INCONCLUSIVE ze STOPPED_INFRASTRUCTURE. Nie potwierdzono pełnego S26/S40 ani fizycznego odbioru.
- **Status:** porównanie wybranych źródeł PASS; transfer ZERO; pełne kwalifikowanie skilli, native binding, aktywacja runtime i produkcyjny GO — NOT_RUN/UNBOUND/HOLD.
- **Źródła:** [korekta zakresu: tylko S13–S26 i ZeroLab](https://github.com/jankes72/SSI-Communications/pull/177#issuecomment-6722959580) · [read-only probe R2](https://github.com/jankes72/SSI-Communications/pull/177#issuecomment-6723030090) · [dokładne porównanie R3](https://github.com/jankes72/SSI-Communications/pull/177#issuecomment-6723091097).



### 4.61 DIRECTOR RC1 W8 / K3–K4 — source integration, RoleNode, ABI i rygor strict36

- **Data:** 1 listopada 2026. Wspólny PR163 pozostawał DRAFT; wyniki poniżej dotyczą wskazanych exact HEAD i oddzielnych zestawów, nie jednego testu produkcyjnego.
- **ROBERT — oryginalne Operations/RM/R17:** K3-04 wykonał **20/20** testów source-integration (6+14) PASS na oryginalnych źródłach Ops/NativeAdapters/RM/R17. Zewnętrzne porty issuer/fence/Evidence i import R16 protocol były syntetyczne; broad CI na tym HEAD nadal miał jeden niezależny błąd importu XAVIER W4. K4-R1-01 dodał **16/16** testów mapy ABI PASS. Mapa zawierała 16 pól, ale wszystkie 16 providerów pozostawało UNBOUND; command_id≠execution_id i lease_epoch≠lease_id bez dowodu właścicielskiego.
- **XAVIER — oryginalny W4/R16:** po odzyskaniu dwóch oryginalnych plików R16 z archiwum źródłowego (init 34 B i protocol 6710 B, zgodne SHA) wspólny PR163 osiągnął **394/394 broad source CI PASS**, w tym **22/22** oryginalnych przypadków W4. To nadal source/synthetic-port integration; 394/394 nie jest strict36 ani testem native.
- **XAVIER — kontrola zależności:** osobny zestaw K3 miał **12/12** pin-guard i **19/19** testów inwentaryzacji metadanych (31/31 łącznie). Wcześniejszy błąd importu został zlokalizowany jako brak oryginalnego R16 protocol, a następnie naprawiony przez dostarczenie prawdziwych bajtów — nie przez stub.
- **NATHAN AMGINE — PHONE ABI:** własny PR154 uzyskał **60/60** testów source CI PASS po dodaniu pozytywnej kontroli ABI-10 (STOP/revoke po callbacku przed commit). Wszystkie 10 przypadków ULPHONE dla native pozostawały NOT_RUN; provider i bieżące uprawnienia UNBOUND.
- **NATHAN SSI / JORDAN / ATLAS — RoleNode:** właścicielski PR166 miał 209/209 testów oraz 4/4 embedded last-mile. Wspólny PR163 potwierdził 8/8 dokładnych Git blobów; Nathan SSI i Jordan wykonali 4/4 last-mile na shared HEAD, a Atlas niezależnie potwierdził 8/8 blobów i 4/4 embedded cases. Są to source/fixture testy z fikcyjnymi policy/coverage/backend, nie native issuer ani host restore.
- **JORDAN — ledger:** 52/52 ID, 52/52 wiersze dziewięciopolowej tabeli, 260/260 komórek pięciu bramek, 8/8 własnych ID i 24/24 historycznych actor IDs zostały sprawdzone strukturalnie. To kompletność indeksu, nie 260 testów funkcjonalnych; wszystkie 52 wiersze zachowywały INSTALL=NO_GO i NATIVE/BACKUP=NOT_ATTESTED. Wskazano też dwa historyczne run-ID brakujące w jednym ledgerze: 7 przypadków 5 PASS/2 INCONCLUSIVE z 2 października oraz odrębny V4 S1–S10 run z 17 września. Nie należy ich dublować z diagnostycznym 1326 (848 PASS/470 INCONCLUSIVE/8 FAIL).
- **HERKULES / ATLAS — strict36 HOLD:** Herkules wykonał **6/6** syntetycznych testów negatywnych, które odtworzyły ryzyko symlinka w katalogu nadrzędnym fixture. Atlas wykonał **18/18** syntetycznych guardów kontraktu receipt i 68/68 testów w kroku tools/github. Te wyniki nie uruchomiły oryginalnego 36-suite. Pełne oryginalne archiwa R16/R17, approved realpath/parent-symlink scope i stable readback pozostały bramką; strict36=NOT_RUN.
- **WIT — źródło:** WIT wskazał autoryzowany locator oryginalnego R16 protocol i zgłosił source intake; późniejsze odzyskanie dwóch plików przez XAVIER nie oznacza automatycznie odbioru całych archiwów R16/R17 w środowisku strict36.
- **Granice końcowe:** 394/394 broad source PASS ≠ strict36 PASS; 52×5 ledger ≠ 260 testów; 4/4 embedded ≠ native RoleNode; 60/60 PHONE ABI ≠ działający telefon. Current issuer/ACL/lease/fence/STOP/Evidence/RM, fresh Session B, isolated backup/restore, host apply i INSTALL/PROD GO pozostały UNBOUND/NOT_RUN/HOLD.
- **Źródła:** [ROBERT K3-04 20/20](https://github.com/jankes72/SSI-Communications/pull/163#issuecomment-6557512223) · [ROBERT K4 ABI 16/16](https://github.com/jankes72/SSI-Communications/pull/163#issuecomment-6558780923) · [XAVIER K3 31/31](https://github.com/jankes72/SSI-Communications/pull/163#issuecomment-6557529956) · [XAVIER W4 394/394 i 22/22](https://github.com/jankes72/SSI-Communications/pull/163#issuecomment-6563879623) · [NATHAN AMGINE 60/60](https://github.com/jankes72/SSI-Communications/pull/163#issuecomment-6564073675) · [JORDAN 52×5 i 24 role IDs](https://github.com/jankes72/SSI-Communications/pull/163#issuecomment-6564076319) · [NATHAN SSI shared 4/4](https://github.com/jankes72/SSI-Communications/pull/163#issuecomment-6563792281) · [ATLAS shared 4/4 + 18/18 guard](https://github.com/jankes72/SSI-Communications/pull/163#issuecomment-6564110837) · [HERKULES ancestor symlink 6/6](https://github.com/jankes72/SSI-Communications/pull/163#issuecomment-6564093207).


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
| [Issue #44](https://github.com/jankes72/SSI-Communications/issues/44) | MultiQuant 70B / R4.2 / R5 Tensor LEGO | testy syntetyczne, guardy, przygotowanie teacher/student, host i koszt |
| [Issue #195](https://github.com/jankes72/SSI-Communications/issues/195) | BODY FROZEN / CZARA / SSI V5 / ZeroLab | odzysk archiwów, Micro-First, Pocket/NanoBit, scenariusze lokalne i propozycje badań |
| [Issue #3](https://github.com/jankes72/SSI-Communications/issues/3) | kolejność i koordynacja prac 70B | bramki B0–B5 i kolejność dostaw; nie jest samodzielnym wynikiem eksperymentu |
| [Issue #4](https://github.com/jankes72/SSI-Communications/issues/4) | Continuity / wspólne źródła i pamięć | źródła, handoffy i odbiory zależności; sprawdzać poszczególne eksperymenty |
| [PR #186](https://github.com/jankes72/SSI-Communications/pull/186) | HERKULES NanoMarker / F1-A / F1-B / NanoTRS | testy dekoderów, próbki GGUF i kompilator tras; bez pełnego merge/inferencji |
| [PR #196](https://github.com/jankes72/SSI-Communications/pull/196) | LEON Context Fastpath / BODY | poprawki ochrony pamięci, testy interfejsów i scenariusze lokalne |
| [PR #197](https://github.com/jankes72/SSI-Communications/pull/197) | SPLOT CZARA Micro-First / ZeroLab | source intake, archiwa, protokół i granice wznowień |
| [PR #203](https://github.com/jankes72/SSI-Communications/pull/203) | LEON CODEX / LEGO skill bindings | mapowanie źródłowych powiązań skilli do symboli, bez automatycznego dispatchu |
| [PR #204](https://github.com/jankes72/SSI-Communications/pull/204) | LEON R8 two-host mission | lokalny scenariusz dwóch procesów i kontrola odtworzenia |
| [PR #165](https://github.com/jankes72/SSI-Communications/pull/165) | ATLAS — SSI-PACK / DIRECTOR peer | niezależne orakle, pomiary bajtów, retesty i audyty źródeł |
| [PR #171](https://github.com/jankes72/SSI-Communications/pull/171) | XAVIER — SSI-PACK R0 | parser/kodek, testy bezpieczeństwa i format kapsuły |
| [PR #163](https://github.com/jankes72/SSI-Communications/pull/163) | DIRECTOR RC1 source WIP | integracja źródeł Operations/R17 i wspólny plan testów; nie instalacja |
| [PR #142](https://github.com/jankes72/SSI-Communications/pull/142) | XAVIER — Operations/R17 | normalizator koperty i lokalne testy źródłowe |
| [PR #143](https://github.com/jankes72/SSI-Communications/pull/143) | ROBERT — receiver / Evidence / RM | testy mostu i granice native provider; pilot pozostał NOT_RUN |
| [PR #154](https://github.com/jankes72/SSI-Communications/pull/154) | NATHAN_AMGINE — PHONE/T4 | walidacja źródeł i fixture; odrębna od native PHONE runtime |
| [PR #166](https://github.com/jankes72/SSI-Communications/pull/166) | NATHAN_SSI — RoleNode | late-coverage / source-pin i testy regresyjne |
| [PR #186](https://github.com/jankes72/SSI-Communications/pull/186) | HERKULES — NanoMarker R11–R13, Nano-Fusion, NanoTRS | toy/offhost, metadane GGUF, próbki fizyczne, smoke hybrydy i kompilator tras |
| [PR #237](https://github.com/jankes72/SSI-Communications/pull/237) | SSI Native Operators / Nano runtime | oryginalne operatory i kontrakty używane jako źródła w testach HERKULESA |
| [PR #39](https://github.com/jankes72/SSI-Communications/pull/39) | WIT — MultiQuant R4.2 / koszt | adapter kosztu, testy i odbiory; sprawdzać zakres konkretnych suite |
| [PR #97](https://github.com/jankes72/SSI-Communications/pull/97) | MOST — MultiQuant L2/B1 guardy | łączenie istniejących guardów i testy CI, bez inferencji 70B |
| [PR #183](https://github.com/jankes72/SSI-Communications/pull/183) | SPLOT — NanoBit / BITCAP | eksperymenty adresowania i reuse, wyniki ograniczone do głowicy/tensorów |
| [PR #184](https://github.com/jankes72/SSI-Communications/pull/184) | Virtual Tile / Q-SHADOW | syntetyczny surrogate i testy offhost, bez pomiaru przyspieszenia 70B |
| [PR #169](https://github.com/jankes72/SSI-Communications/pull/169) | SPLOT — BF16 teacher → Q1 student | kontroler source/CI i bramki; nie utożsamiać z gotowym studentem |
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
2. Dokończyć audyt PR #232, #233, #185, #186, #196, #197, #203, #204 i #139 plik po pliku oraz komentarz po komentarzu, aby wyodrębnić konkretne eksperymenty, autorów, testerów i odbiorców.
3. Dokończyć audyt PR-ów i plików powiązanych z Issues #116, #149 i #195; komentarze tych trzech wątków zostały przejrzane, a potwierdzone wyniki i ograniczenia dopisano w sekcjach 4.54–4.57. Nie uznawać samego przeglądu komentarzy za pełny audyt wszystkich podlinkowanych PR-ów.
4. Dla projektów wymienionych w portfolio PR #242 utworzyć osobne karty w `PROJEKTY/` dopiero po potwierdzeniu ich zakresu i źródeł.
5. Uzupełniać wyniki liczbowe wyłącznie wtedy, gdy źródło podaje metrykę, środowisko, zakres prób i ograniczenia.
6. Każdy wpis w mapie powinien prowadzić do źródła oraz — gdy dotyczy konkretnej osoby — do jej profilu.

**Stan kompletności:** wersja 2.0 obejmuje 61 opisanych obszarów eksperymentów, prób i odrębnych odczytów źródłowych, w tym nowe uzupełnienia Issue #116, #149 i #195. To szeroki, nadal otwarty rejestr źródłowy: komentarze trzech wątków zostały przejrzane, ale wszystkie podlinkowane PR-y i pliki wymagają dalszego audytu źródło po źródle. Pozycje niezweryfikowane pozostają jawnie oznaczone jako otwarte, zamiast być uzupełniane domysłami.

## 9. Powiązana dokumentacja

- [Kronika dzienna](CHRONIKA/)
- [Profile członków](CZLONKOWIE/README.md)
- [Karty projektów](PROJEKTY/)
- [Indeks modułów i technologii](MODULY-I-TECHNOLOGIE.md)
- [Zasady datowania i statusów](ZASADY-DATOWANIA.md)
- [Szablon karty projektu](PROJEKTY/SZABLON-PROJEKTU.md)

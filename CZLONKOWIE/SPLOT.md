# SPLOT

**Profil publiczny członka Kolektywu SSI**

## Obszary działalności

- Integracja i koordynacja prac nad SSI Continuity Node na NOUT01.
- Weryfikacja wyników eksperymentów, odczytów operatora i kontroli integralności.
- Przygotowanie i ocena procedur bezpieczeństwa, ciągłości danych, kopii zapasowych i odtwarzania.
- Koordynacja prac nad fizycznym modelem nauczycielem 70B oraz eksperymentem Tensor LEGO 70B.
- Pomiary wydajności CPU/GPU i przygotowanie integracji z istniejącymi modułami SSI.
- Odtwarzanie kontekstu ról i kontrola zgodności wyników z zachowaniem autorstwa źródeł.

## Udokumentowane osiągnięcia — chronologicznie

### 28 października 2026 — Continuity Node, testy wydajności i odtwarzanie kontekstu

- Niezależny retest materiałów referencyjnych: **38/38 testów PASS** i zgodność **15/15** pozycji manifestu. Była to kontrola offline, nie test pełnego wdrożenia.
- Sonda środowiska przeszła **28/28 testów lokalnych PASS**. Odczyt z niewłaściwego środowiska został prawidłowo zatrzymany i nie został zaliczony jako test NOUT01.
- Na NOUT01 operator potwierdził przygotowanie pustej struktury katalogów, instalację pakietu referencyjnego i wynik **38/38 oryginalnych testów PASS**.
- Staging pilota: **15 pozycji manifestu i 6 par danych zgodnych**; dostęp użytkownika do chronionego obszaru został odrzucony zgodnie z oczekiwaniem. Nie oznaczało to uruchomienia agenta ani pełnego wdrożenia.
- Syntetyczny test backendu Qwen 3.5 0.8B na NOUT01 zwrócił poprawną odpowiedź dla fikcyjnych danych: **106 tokenów wejściowych, 43 wyjściowe, około 9,09 s**. Była to pojedyncza próba, nie pełny test ciągłości.
- W krótkim porównaniu syntetycznym GPU20 uzyskało medianę ciepłego wywołania **1,338 s**, wobec **4,345 s** dla CPU2 — około **3,25 raza szybciej** w tym konkretnym teście. Nie jest to uniwersalny benchmark ani potwierdzenie przyspieszenia MultiQuant.
- Pakiet integracyjny Continuity Node przeszedł **85/85 testów offline**. Pakiet został zainstalowany i zweryfikowany na hoście, ale konfiguracja runtime i natywne połączenia pozostały niegotowe.
- Mechanizm wznowienia kontekstu roli odtworzył w testach 10 źródeł i 76 wpisów; operator potwierdził na NOUT01 **24/24 testów PASS**. Było to odtworzenie datowanego kontekstu, nie uruchomienie modelu ani dowód pełnej pamięci.
- Licznik tokenów tekstu na hoście przeszedł **7/7 przypadków autotestu PASS**. Pełne liczenie tokenów renderowanego żądania modelu nie było potwierdzone.
- W przeglądzie wspólnego cyklu wykonania roli wykryto problem współdzielonego wyniku odpowiedzi. Po lokalnej poprawce regresyjnej testy przeszły **37/37 PASS**; poprawka wymagała przyjęcia przez właściciela modułu.

### 29 października 2026 — kontrola metadanych modelu i walidacja

- Odczyt metadanych modelu na NOUT01 zakończył się poprawnie; odczytane ustawienia były zgodne z wcześniejszymi zapisami.
- Renderer i źródło szablonu nie zostały jednoznacznie rozpoznane; inferencji nie uruchomiono.
- Lokalny zestaw walidacyjny związany z poprawką P2 przeszedł **75/75 testów PASS**.

### 30 października 2026 — kontrola kopii zapasowych

- Wykonano serię ograniczonych, tylko do odczytu kontroli środowiska i nośnika przeznaczonego na kopie zapasowe.
- Potwierdzono wybrane metadane urządzenia i dostępność odczytu w określonym zakresie.
- Kolejne skany ujawniły ograniczenia dostępu i niejednoznaczność inwentaryzacji. Końcowy odczyt metadanych przeszedł, ale **zawartość, kompletność i integralność kopii nie zostały potwierdzone**.
- **Test odtworzenia kopii nie został wykonany.** Odczytu metadanych nie przedstawiono jako potwierdzenia działającego backupu.

### 31 października 2026 — Continuity R1/R4 i Tensor LEGO 70B

- Niezależna weryfikacja materiałów źródłowych osiągnęła **100/100 zgodnych pozycji**; kolejna rewizja również przeszła **100/100**. Dotyczyło to źródeł, nie instalacji na hoście.
- Kontrola źródłowa związana z bezpieczeństwem kopii zapasowych przeszła **12/12 testów regresyjnych**. Przeglądy i decyzje wdrożeniowe pozostały odrębnymi bramkami.
- Operator potwierdził kontrolę źródła i sum kontrolnych pobranego pakietu. Nie oznaczało to pełnego wdrożenia Continuity.
- Dla modelu 70B przygotowano przestrzeń docelową i przeprowadzono kontrole dostępu. Początkowo zapis do wymaganych obszarów był blokowany; po uzgodnieniu zakresu operator potwierdził przygotowanie katalogów i odczyt metadanych modelu.
- Pobranie modelu nauczyciela 70B na NOUT01 zakończono: **30/30 shardów obecnych**, mapa wag zgodna z indeksem, następnie **30/30 kontroli SHA-256 wag PASS** i **9/9 kontroli skrótów metadanych PASS**. Potwierdza to integralność plików względem wskazanego źródła, nie jakość modelu ani wynik inferencji.
- Kontrola zasobów hosta T0 przeszła. Inwentaryzacja nagłówków tensora T1A uzyskała **PASS_PREVIEW_ONLY**. Kontrola T1B0 potwierdziła metadane i granice odczytu, ale **nie odczytano bajtów wag**.
- Odczyt raportu T1B1 wykazał kandydujący wpis skrótu dla jednego sharda, lecz jego znaczenie wymagało niezależnej oceny. Nie uznano go za nową atestację sharda.
- **Trening, budowa pełnego modelu studenckiego, pełny eksperyment Tensor LEGO 70B i porównanie jakości z modelem bazowym nie zostały wykonane** w udokumentowanym zakresie tych wpisów.

## Współpraca i projekty

- **SSI Continuity Node NOUT01:** koordynacja integracji, kontroli środowiska, stagingu, pomiarów backendu i odtwarzania kontekstu. Współpraca z Mostem, Xavierem, Herkulesem, Kordianem, Leonem, Wektorem i innymi opiekunami modułów.
- **SSI MultiQuant / Tensor LEGO 70B:** koordynacja fizycznego modelu nauczyciela na NOUT01, kontrola transferu i integralności plików oraz przygotowanie kolejnych etapów eksperymentu. Pozostałe etapy zachowały przypisane role współpracowników.
- **Bezpieczeństwo i ciągłość danych:** przygotowanie bramek kontroli oraz współpraca przy przeglądach, testach i ocenie ograniczeń kopii zapasowych.

## Statusy i ograniczenia

- Wyniki lokalne, wyniki operatora na NOUT01, kontrole źródeł i wyniki CI są rozróżniane; nie są automatycznie równoważne.
- PASS testu syntetycznego nie oznacza pełnego testu modelu, ciągłości ani wdrożenia produkcyjnego.
- Odczyt metadanych kopii zapasowej nie potwierdza jej kompletności, integralności ani możliwości odtworzenia.
- Potwierdzony transfer i skróty SHA modelu nauczyciela nie dowodzą treningu, inferencji ani jakości modelu studenckiego.
- Na koniec udokumentowanego okresu pełny eksperyment Tensor LEGO 70B, budowa studenta, trening i porównanie jakości pozostawały niewykonane.

## Źródła

- [Kronika — 28 października 2026](../CHRONIKA/2026-10-28.md)
- [Kronika — 29 października 2026](../CHRONIKA/2026-10-29.md)
- [Kronika — 30 października 2026](../CHRONIKA/2026-10-30.md)
- [Kronika — 31 października 2026](../CHRONIKA/2026-10-31.md)

## Issues źródłowe — mapa informacji (skrót)

Poniższe wątki zawierają bezpośrednie przekazania, meldunki lub ustalenia dotyczące zakresu SPLOT. Wątki zespołowe mogą zawierać także prace innych osób — autorstwo pozostaje przypisane wyłącznie wskazanym autorom.

- [Issue #4](https://github.com/jankes72/SSI-Communications/issues/4) — Continuity Node/NOUT01 — przejęcie integracji, źródła i odbiór.
- [Issue #5](https://github.com/jankes72/SSI-Communications/issues/5) — Rewizja pilota i przekazanie źródeł MOSTOWI.
- [Issue #6](https://github.com/jankes72/SSI-Communications/issues/6) — Harness świeżych sesji, bootstrap i kanoniczny B1 — przekazanie do XAVIERA.
- [Issue #7](https://github.com/jankes72/SSI-Communications/issues/7) — NOUT01, trasa dostępu, N0, izolacja i restore — przekazanie do HERKULESA.
- [Issue #8](https://github.com/jankes72/SSI-Communications/issues/8) — Natywne źródła pamięci, ACL i Evidence — zależności dla LEONA/BARTKA.
- [Issue #9](https://github.com/jankes72/SSI-Communications/issues/9) — Context Compiler, MUST_KEEP, tokenizery i CC-01..18.
- [Issue #10](https://github.com/jankes72/SSI-Communications/issues/10) — Receipt, readback i wznowienie bez powtórzenia skutku — ROBERT.
- [Issue #11](https://github.com/jankes72/SSI-Communications/issues/11) — Pakiet startowy sesji i powrót artefaktu — WIT.
- [Issue #12](https://github.com/jankes72/SSI-Communications/issues/12) — Kolejność integracji, zgodność wersji i odbiór — ANDRZEJ.
- [Issue #13](https://github.com/jankes72/SSI-Communications/issues/13) — Niezależny przegląd kompletności i testów — ORION/MAREK/WEKTOR/ALBERTO.
- [Issue #116](https://github.com/jankes72/SSI-Communications/issues/116) — DIRECTOR VPS/NODE01 — wspólna tablica działów, źródeł, ról i bramek wdrożenia.
- [Issue #170](https://github.com/jankes72/SSI-Communications/issues/170) — SSI-PACK LAB R0 — wspólny eksperyment odzyskiwania historii z Issues.
- [Issue #195](https://github.com/jankes72/SSI-Communications/issues/195) — Priorytet BODY FROZEN — integracja źródeł BIT/B1, RM, V10/S10, SCC i ISKIER.
- [Issue #149](https://github.com/jankes72/SSI-Communications/issues/149) — kanoniczna tablica DIRECTOR 1 — W4-09/NODE01, źródła Continuity, Qwen 0.8B/Context Fastpath oraz przekazanie integracji zespołowi.


- **PR #242 — wspólne portfolio Kolektywu:** współopracowanie z Pawłem indeksu 22 głównych projektów oraz 9 uzupełniających wątków, z opiekunami, współpracownikami, statusami i odnośnikami do źródeł. To praca porządkująco-dokumentacyjna; nie oznacza autorstwa SPLOTA wszystkich ujętych projektów ani odbioru ich wdrożeń. [wpis i zakres portfolio](https://github.com/jankes72/SSI-Communications/pull/242#issuecomment-6801327745)
- **PR #242 — plan rozmieszczenia Armii SSI R1:** przygotowanie dokumentu planistycznego rozdzielającego control plane DIRECTOR, workerów 1.5B/3B na MODELS, środowisko ROBERT, NODE-01 i MSI; uwzględniono współdzieloną pulę inferencji, logiczne stanowiska, separację ISKRA oraz bramki przed instalacją. To plan rozmieszczenia `TO-BE`, nie wdrożenie hostowe ani zgoda produkcyjna. [źródłowy handoff SPLOT → ASTER](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6886170545)

## Uzupełnienie wkładu — PR #243, PR #244 i dziennik #245 (16–20.11.2026)

- **PR #243 — przekazanie źródeł ASTER → SPLOT:** odebranie dokumentacji BODY NEUTRAL/ISKRA, V10/S10, Nano/LEGO i pełnego raportu badań SSI Small R2 R1–R3. Odbiór miał charakter source-only; nie oznaczał natywnego wdrożenia. [ACK przekazania](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6880004745) · [ACK raportu R1–R3](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6881879836)
- **PR #243 — prace własne SPLOT:** publikacja raportu przekazania dwóch rodzin BODY i nakładek V10/S10 oraz potwierdzenie integralności trzech paczek WORKPACK ASTER. [Raport SPLOT](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6879925322) · [odbiór paczek](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6882054760)
- **PR #244 / Issue #245 — NANO-COMM i Maluch Coder:** przygotowanie i przeprowadzenie kontrolowanych prób SSI 0.5B na DIRECTOR. R2 FULL30: 30 inferencji, 12/30 exact i 18/30 poprawnego formatu. R3 Coder FULL4: 4/4 wybory narzędzia i 4/4 zweryfikowane misje na syntetycznych danych, przy ograniczeniach opisanych w źródłach; nie jest to produkcyjny terminal LLM ani pełna izolacja SCC. [R2 FULL30](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6916928848) · [R3 FULL4](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6917639552) · [odczyt metryk](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6917886107)
- **PR #244 — R4 benchmark 0.5B/1.5B/3B:** przygotowanie runnera, parsera i bezpiecznych guardów; 11/11 testów offline dla FIX2. Weryfikacja wag 0.5B zakończona PASS; 1.5B zatrzymano dwukrotnie przez IO_PRESSURE, 3B pozostał NOT_STARTED. Nie uruchomiono 6-godzinnej kampanii inferencji. [FIX2 i status](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6920753279) · [kontrolowany HOLD 1.5B](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6920934735)
- **PR #232/#233:** prace nad markerami Nano, pokryciem tras, fork/join i projekcją zależności; wkład SPLOT jest odrębny od rozszerzeń CODEX i źródeł R11 LEONA. [PR #232 — fork/join](https://github.com/jankes72/SSI-Communications/pull/232#issuecomment-6728162400) · [PR #233 — eksperyment lokalny](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6728894653)

Wpisy powyżej rozróżniają własne prace SPLOT, odbiór przekazań i pomiary wykonane przez operatora Pawła. Nie oznaczają samodzielnego autorstwa wyników operatora ani PROD_GO.

## Uzupełnienie audytu — PR #185 / MultiQuant i Nano (3–5.11.2026)

### 3–4 listopada 2026 — T0-22–T0-30: syntetyczne badania Q2/Q4, LoRA i staging

- PR #185 dokumentuje własny tor badawczy SPLOTA: CPU-only, syntetyczny surogat 80 warstw, rank-2 oraz adapter inspirowany LoRA. W bazowym T0-22: **21/21 bramek i 8/8 testów jednostkowych PASS**; kompresja toy nie przełożyła się na szybkość — rozszerzony runtime był około **2,23× wolniejszy** od małego nauczyciela FP32.
- T0-27 badał adaptacyjne bloki Q1/Q4 i LoRA. Wynik 25/25 prostych odpowiedzi nie oznaczał najlepszego profilu: wariant 8 Q4 + 72 Q1 ze starą LoRA Q3 miał mean relative activation L2 0,13255; wariant 16 Q4 + 64 Q1 z ponownie trenowaną LoRA Q4 uzyskał 0,06520 na jednym syntetycznym teacherze.
- T0-28 nie wykazał powtarzalnej przewagi wyboru adaptacyjnego nad losowym w 10 próbach.
- T0-30: mieszany profil 1,9 bpw nie zakwalifikował się wobec Q2 w **0/10** prób. Wynik negatywny pozostaje zachowany.
- 4 listopada dodano source-only staging Q2/Q4: skrypt lokalnej bramki, selektor Q2/Q4 z rezerwą RAM 15%, 10 przypadków testowych oraz README. Testy selektora były w tym meldunku **dodane, ale nie miały jeszcze niezależnego potwierdzenia wykonania**. Stan: SOURCE_STAGED; modele S0 NOT_RUN; 70B Q2/Q4 NOT_BUILT; NOUT1 HOLD_IO_PRESSURE; bez zmian hosta i bez PRODUCTION_GO.

### 5 listopada 2026 — T0-34N: NanoBit + NanoMarker + LoRA i drugi kontekst kapsułowy

- Wykonał eksperyment OFFHOST na CPU, na syntetycznych danych: **30/30 testów PASS**, pięć niezależnych seedów oraz rozdzielone TRAIN/CAL/VAL/TEST/SHIFT.
- Dla strukturalnych syntetycznych wag wariant NanoBit + LoRA + heurystyka miał 2701 B i TEST MSE 0,001462824 wobec Q2 2721 B i MSE 0,014263527. Uczony NanoMarker nie pokonał heurystyki (**0/5 seed wins**); na niestrukturalnych wagach Nano tracił przewagę, więc fallback pozostaje konieczny.
- Źródła i wyniki zostały opublikowane w PR #185; GitHub readback **8/8 plików** potwierdził obecność dostawy. To readback źródeł, nie nowa niezależna replikacja.
- Adapter drugiego kontekstu kapsułowego był testowany na mockach. LIVE SSI BINDING=NOT_RUN; LLM TRAINING=NOT_RUN; 70B TRAINING=NOT_RUN; NODE01_ACTION=NO. Q2/Q4 toy codec nie jest GGUF ani rzeczywistym QAT.

### 5 listopada 2026 — odbiór R12 i bramka kodeka

- Przyjął źródła R12 HERKULESA i przygotował własny moduł codec-admission/fallback. Własny lokalny zestaw osiągnął **16/16 testów PASS**; Git blob źródła i testu odpowiadał bajtom testowanym lokalnie.
- Bramkę zaprojektowano do oceny pełnych bajtów oraz dekodowanych VAL/SHIFT_VAL i wyboru testowanego Q2/Q4/MIXED_RAW, gdy wariant Nano nie spełnia kryteriów. Moduł nie był jeszcze podłączony do treningu ani inferencji. Uczony NanoMarker przegrywał z heurystyką w 8/10 seed, a post-hoc NanoBit nie dawał oszczędności bajtów w tej serii.
- Pełne źródła i 10-run JSON R12 znajdowały się w PR #186; odbiór SPLOTA nie jest niezależną replikacją R12.

### 5 listopada 2026 — T0-35 NanoGate: syntetyczny klasyfikator wyboru ścieżki

- Wykonał **23/23 testy jednostkowe PASS**, trening klasyfikatora 11 cech (240 TRAIN, 80 TUNE), ocenę na 80 TEST i 48 SHIFT_TEST oraz drugi przebieg z bajtowo identycznym modelem.
- Znane rodziny: learned **80/80** (TP48, FP0, FN0, TN32), heurystyka 64/80. Niewidziane rodziny: learned **26/48**, heurystyka 32/48; learned wygenerował 22 fałszywe wskazania Nano i nie wygrał na SHIFT.
- Ostateczny decoded VAL/SHIFT_VAL guard blokuje niebezpieczne wskazania. NanoGate zwraca wyłącznie WORTH_TRY; nie steruje kodowaniem, ACL ani klientem. Koszt obliczania cech nie został zmierzony jako przyspieszenie.
- Raport i readback źródłowy są potwierdzone; w chwili meldunku kod/model/JSON T0-35 pozostawały w operatorowym ZIP, a transfer źródeł do GitHub oczekiwał na operatora. Nie przedstawiać tego jako pełnego, opublikowanego pakietu kodu.

### Granice i źródła

- PR #185 jest DRAFT/OPEN, bez merge. Żaden z powyższych wyników nie potwierdza realnego Llama 70B, QLoRA NF4, jakości klientowskiego modelu, produkcyjnego GPU, wdrożenia na NOUT1/NODE01 ani gotowości komercyjnej.
- T0-22–T0-35 są różnymi eksperymentami i nie wolno sumować ich testów ani przenosić wyników na realny model.
- Źródła: [PR #185](https://github.com/jankes72/SSI-Communications/pull/185), [T0-34N raport](https://github.com/jankes72/SSI-Communications/blob/f73c25bf4915ac2d844130421ac158155b3b3dbb/projects/SSI_MULTIQUANT/enterprise_r0/t034n_customer_capsule_joint_offhost_r1/T034N_RESULT_AND_SOURCE_HANDOFF_R1_20261105.md), [T0-35 raport](https://github.com/jankes72/SSI-Communications/blob/e56c7056453172baa2b7cfd9816d5d7e99646b33/projects/SSI_MULTIQUANT/enterprise_r0/t035_nanogate_offhost_r1/T035_NANOGATE_TRAINING_RECEIPT_R1_20261105.md), [R12 bramka SPLOTA](https://github.com/jankes72/SSI-Communications/blob/bfede93d5b1c057c134075d0485c80d87789746c/projects/SSI_MULTIQUANT/enterprise_r0/t034n_customer_capsule_joint_offhost_r1/HERCULES_R12_TO_SPLOT_TRAINING_GATE_R1_20261105.md).



## Uzupełnienie audytu — S13–S26 NanoBit R1/R2 (8 listopada 2026)

- Własny odczyt R1 przypiął pochodzenie **530/530 markerów**: 14 etapów S13–S26, 70 rodzin, 420 przypadków i 26 wybranych plików ZeroLab. Zapisano **602 deklarowane relacje źródłowe** (70 stage→family, 420 family→case, 112 stage→file); nie są to krawędzie wykonania ani natywne skille.
- Własny NanoBit R2 wykonał pack→verify na rzeczywistym JSON R1: **5/5 testów offline PASS**, dekodowanie do oryginalnego JSON PASS. Pakiet SSINBS26 miał 64 930 B (bitpacked relacje 1 957 B, skompresowane provenance 62 921 B).
- Paweł niezależnie wykonał na MSI **5/5 testów PASS** i potwierdził decode_readback=PASS dla tego samego pakietu i SHA.
- Granice: native_skills_bound=0, native_router_edges_attested=0, model_weight_tiles_bound=0, writes_to_director=0. SSINBS26 opisuje lineage etapów/źródeł, nie natywne trasy SSINBRT1, membership CZARA SSINBCR6, 530 aktywnych skilli ani trening modelu. Transfer na VPS ROBERT nie rozpoczął się.
Źródła: [R1 530 markerów / 602 relacje](https://github.com/jankes72/SSI-Communications/pull/197#issuecomment-6725386438), [R2 rzeczywiste wejście i decode PASS](https://github.com/jankes72/SSI-Communications/pull/197#issuecomment-6725422088), [niezależny test MSI 5/5](https://github.com/jankes72/SSI-Communications/pull/197#issuecomment-6725460960).

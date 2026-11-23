# HERKULES

**Profil publiczny członka Kolektywu SSI**

Herkules prowadzi obszar **SSI Hercules / SSI-SECURITY-001**: projektowanie zasad bezpieczeństwa infrastruktury, ochronę granic uprawnień, przeglądy bezpieczeństwa, kontrolę delegowania zadań, STOP/revoke, obsługę nieznanego skutku, integralność kopii oraz przygotowanie procedur audytu i odtwarzania.

Zakres obejmuje także projekt powtarzalnej usługi ochrony i administracji serwerami SSI oraz — po odrębnym upoważnieniu — serwerami klientów. Planowanie takiej usługi nie jest równoznaczne z jej wdrożeniem ani całodobowym monitoringiem.

## Obszary działalności

- **Bezpieczeństwo hostów i usług:** minimalne uprawnienia, rozdzielenie kont, bezpieczna administracja, audyt konfiguracji i kontrolowane aktualizacje.
- **Granice zaufania i autoryzacja:** aktualna polityka, issuer, zakres delegacji, izolacja tenant/project/role/task/session.
- **STOP, revoke i nieznany skutek:** blokowanie spóźnionych wyników, odczyt rzeczywistego stanu przed ponowieniem, zasada braku automatycznego replay.
- **Pamięć i ciągłość SSI:** ochrona źródeł, checkpointów, ról i dowodów przed podszyciem, mieszaniem zakresów i nieuprawnionym odtworzeniem.
- **Backup i recovery:** walidacja manifestu kopii, oddzielenie integralności od odtwarzania, procedury rollback i izolowanego restore.
- **Bezpieczna współpraca z modelami:** ograniczone, odczytowe obserwacje i projekcje danych; wynik modelu nie otrzymuje uprawnień wykonawczych.

## Udokumentowane osiągnięcia

### 26 października 2026 — powołanie SSI Hercules i plan budowy

Paweł powierzył Herkulesowi obszar bezpieczeństwa serwerów SSI oraz przygotowanie powtarzalnej usługi ochrony infrastruktury klientów. Herkules opracował architekturę, etapy budowy H00–H14 i mapę integracji z Dyrektorem, SCC, CODEX i wykonawcami. Ustalono model przejściowej, wydzielonej usługi na serwerze DIRECTOR oraz docelowe przeniesienie centrali na osobny serwer.

Przygotowano lokalny szkielet i panel prototypowy; plan budowy odnotowuje **16 lokalnych testów PASS**. Był to etap dokumentacyjny i lokalny. Nie oznaczał instalacji agenta, aktywnego monitoringu, uruchomienia mostów ani niezależnego audytu VPS.

Wstępne zgłoszenie prób SSH potraktowano jako zgłoszenie wymagające weryfikacji. Późniejsze doprecyzowanie właściciela wskazało, że ostatnie logowanie należało do niego i nie potwierdzono skutecznego włamania. Sam raport nie był bezpośrednim audytem hosta wykonanym przez Herkulesa.

Źródło: [kronika 26 października](../CHRONIKA/2026-10-26.md).

### 27 października — granica zaufania R3 i wspólna pamięć

Herkules dostarczył własną rewizję granicy zaufania R3 i przyjął zakres współpracy nad wspólną pamięcią SSI. Uruchomił niezmienione testy Marka oraz własny zestaw kontrolny: **38/38 lokalnych testów PASS** (28 testów Marka i 10 Herkulesa).

Wniosek: zgodność lub kompletność danych wejściowych nie uwierzytelnia bieżącej polityki ani dostawcy uprawnień. Wynik oceny referencyjnej nie może sam nadać prawa do wykonania. Wskazano potrzebę niezależnego, zaufanego źródła polityki, kontroli aktualności i odwołania praw oraz rozdzielenia uprawnień od pamięci/modelu. Testy były offline, na fikcyjnych danych; natywny B1, issuer/ACL, pilot i host pozostały poza zakresem.

Źródło: [kronika 27 października](../CHRONIKA/2026-10-27.md).

### 28 października — obserwator R1, review MultiQuant i odbiór wznowienia

Herkules przygotował lokalnego, tylko do odczytu obserwatora R1. Obejmuje on ograniczoną inwentaryzację systemu i zasobów, walidację znormalizowanych liczników zdarzeń oraz bezpieczną projekcję sygnałów dla przyszłej współpracy z MultiQuant. Nie uruchamia poleceń, nie zmienia hosta, nie wysyła danych do modelu i nie przyznaje uprawnień. Walidacja lokalna: **29/29 testów PASS**.

W peer review adaptera MultiQuant wykryto błąd obsługi niepoprawnego Unicode. Herkules przygotował poprawkę i pięć testów regresyjnych; po zmianie **50/50 testów lokalnych PASS**, a CI wskazanego HEAD zakończyło się sukcesem. Osobny przegląd licznika Splota: **13 PASS / 7 SKIP**. Herkules niezależnie odtworzył także **36 lokalnych testów** z dwóch wcześniejszych dostaw SPLOT/XAVIER i przeprowadził trzy negatywne próby odczytu źródła, które zostały zablokowane zgodnie z oczekiwaniem. Nie był to test modelu, sieci ani natywnego runtime.

Źródło: [kronika 28 października](../CHRONIKA/2026-10-28.md).

### 29 października — ochrona przed cofnięciem delegacji i bramka presji

Wspierając Xaviera, Herkules przygotował poprawkę ponownego sprawdzenia zakresu i delegacji bezpośrednio przed przekazaniem żądania do istniejącego transportu. Cztery syntetyczne przypadki cofnięcia prawa lub zmiany źródła zostały zablokowane; **49/49 lokalnych testów PASS**.

Dla MultiQuant przygotował bramkę presji cgroup/PSI, korzystającą z istniejącego planisty zamiast tworzyć drugą kolejkę. **10/10 testów lokalnych PASS, CI SUCCESS**. Bramka zatrzymuje przygotowanie kolejnego fragmentu przy presji, brakujących lub nieaktualnych danych. Nie tworzy cgroup, nie egzekwuje limitów hosta i nie anuluje samodzielnie trwającego I/O.

Źródło: [kronika 29 października](../CHRONIKA/2026-10-29.md).

### 30 października — atomowa kontrola zakresu przy potwierdzeniu odczytu

Herkules wykrył wyścig pomiędzy ostatnią kontrolą zakresu a potwierdzeniem odczytu wiadomości. Przygotował poprawkę źródłową, która wiąże kontrolę tenant/project/task, nadawcę i kontekst uwierzytelnienia z samą transakcją ACK. Dodano regresję zmiany zakresu dokładnie w chwili potwierdzenia; niepewny skutek wymaga readbacku, bez automatycznego replay.

Tego dnia przyjęto też zasadę kanonicznego dziennika: odczyt aktualnego stanu przed działaniem, zapis dokładnego wyniku po działaniu i jawne rozdzielenie source/CI od host/native. Zmiana była source-only — bez SSH, instalacji, zmian ACL hosta, backup restore ani wywołań modelu.

Źródło: [kronika 30 października](../CHRONIKA/2026-10-30.md).

### 31 października — A13, STOP/cancel i bezpieczeństwo integracji DIRECTOR

Herkules dostarczył i odebrał na poziomie źródłowym kilka rozdzielonych bramek:

- **A13 — kontrakt manifestu backupu:** offline walidator pól manifestu; po poprawce **7/7 testów PASS** na dokładnym przebiegu CI. Wynik oznacza wyłącznie poprawność kontraktu manifestu, nie istnienie kopii, integralność jej zawartości ani restore.
- **Atomic ACK:** dokładny przegląd źródłowy zmiany wiązania zakresu projektu i wiadomości.
- **STOP/cancel:** własny przegląd kontraktu odwołania, zatrzymania spóźnionego wykonawcy i readback-first/no-replay przy nieznanym skutku. CI exact-head zakończyło się sukcesem; natywny provider STOP i test hostowy pozostały niepotwierdzone.
- **G0 i kontrola procesu:** zatwierdzony ograniczony zakres read-only. Dodatkowa poprawka zabezpieczyła sytuację, w której stan usługi zmieniał się pomiędzy dwoma odczytami.
- **Integracja bezpieczeństwa:** kontrakt współpracy Dyrektora, Herkulesa i Roberta przekazany właściwym właścicielom.

Własny strumień D-SEC zakończono na poziomie źródeł i przekazania. Hostowy G0, aktualny issuer/ACL, trwałe lease/fencing/STOP, Evidence/RM, izolowany restore i natywne E2E pozostały otwarte. **PRODUCTION_GO nie został przyznany.**

Źródło: [kronika 31 października](../CHRONIKA/2026-10-31.md).

### 2 listopada — przekazanie G1–G6 i bramki Micro-First

Kapsuła R2 wskazuje datowany handoff G1–G6 Herkulesa. Dla dokładnego źródła odnotowano **106/106 testów offline PASS**, w tym 48 testów granic obecności/wiadomości/odwołania praw oraz 29 testów przyjęcia Micro-First.

Były to syntetyczne testy źródłowe, nie natywne testy połączonych agentów, issuer/ACL, hosta ani produkcyjnego monitoringu. W publicznej kronice data jest wyraźnie oznaczona jako uzupełnienie z handoffu, nie odrębny dziennik dzienny.

Źródło: [kronika 2 listopada](../CHRONIKA/2026-11-02.md).

### 6 listopada — granice bezpieczeństwa BODY_FROZEN i SSI V5

W źródłowym przeglądzie BODY_FROZEN/SSI V5 Herkules rozdzielił bezpieczeństwo overlay i pamięci SSI-MEM/B1 od NanoBit, dotyczącego adresowania i kwantyzacji wag modelu. Pozostawił autorstwo natywnego kodeka B1, BODY_FROZEN i sześciu Iskier ich właściwym właścicielom.

Wkład obejmował przegląd granic bezpieczeństwa: osobne tożsamości i pamięć ról, bieżący issuer/ACL/STOP, przypięte źródła i wersje skilli oraz zakaz aktywacji niepełnych pakietów. Był to przegląd źródłowy; nie wykonano działań hostowych ani natywnego uruchomienia.

Źródło: [kronika 6 listopada](../CHRONIKA/2026-11-06.md).

### 7 listopada — własny handoff roli i granice wznowienia

Herkules przygotował źródłowy handoff własnej roli, porządkujący pochodzenie, zakres odpowiedzialności, wcześniejsze wyniki i otwarte bramki. Dokument nie jest natywną kapsułą, przydziałem aktora ani dowodem aktywnej sesji. Wskazano niepoświadczony native actor/issuer/ACL, natywny B1 NOT_ATTESTED, brak pełnego Pocket Micro/ZeroLab/LLM E2E oraz izolowanego restore/rollback.

Źródło: [kronika 7 listopada](../CHRONIKA/2026-11-07.md).

## Współpraca i projekty

- **SPLOT / SPLOTUS:** współpraca przy pamięci, źródłach, kopiach i ograniczonych odczytach; wyniki ich hostowych odczytów nie są automatycznie własnymi testami Herkulesa.
- **MOST:** wspólna pamięć i pokrycie źródeł; Herkules zachowuje odrębność przeglądu bezpieczeństwa.
- **XAVIER / CODEX:** kontrola delegacji, źródeł, adapterów i granic wykonania; pomoc Herkulesa nie przejmuje autorstwa projektu Xaviera.
- **KORDIAN / MultiQuant:** triage, bramka presji zasobów i bezpieczne użycie opinii modelu bez prawa wykonania.
- **ROBERT:** przyszłe wykonanie wyłącznie przez istniejące uprawnione mechanizmy, z trwałym wynikiem i readbackiem.
- **BARTEK / LEON / ANDRZEJ / DIRECTOR:** natywne SCC, issuer, ACL, host binding i koordynacja pozostają odrębnymi odpowiedzialnościami.

## Statusy i ograniczenia

- Potwierdzone są testy lokalne i CI na wskazanych rewizjach źródła oraz konkretne przeglądy bezpieczeństwa.
- Nie potwierdzono pełnego wdrożenia agenta SSI Hercules, monitoringu 24/7, produkcyjnej ochrony serwerów klientów ani kompletnego natywnego łańcucha autoryzacji i wykonania.
- Aktualny issuer/ACL pozostawały w kapsule R2 UNBOUND; natywny B1 NOT_ATTESTED.
- Pocket Micro/ZeroLab/LLM E2E oraz G5 izolowany restore/rollback pozostawały NOT_RUN lub HOLD.
- Kapsuła źródłowa nie jest poświadczeniem aktywnej instancji. Numer T4 nie dowodzi uruchomienia połączenia ani zgody na kontakt.
- Test offline, source review lub poprawny manifest nie zastępuje testu hostowego, natywnego, restore ani produkcyjnego GO.

## Źródła

- [Kronika 26 października](../CHRONIKA/2026-10-26.md)
- [Kronika 27 października](../CHRONIKA/2026-10-27.md)
- [Kronika 28 października](../CHRONIKA/2026-10-28.md)
- [Kronika 29 października](../CHRONIKA/2026-10-29.md)
- [Kronika 30 października](../CHRONIKA/2026-10-30.md)
- [Kronika 31 października](../CHRONIKA/2026-10-31.md)
- [Kronika 2 listopada](../CHRONIKA/2026-11-02.md)
- [Kronika 6 listopada](../CHRONIKA/2026-11-06.md)
- [Kronika 7 listopada](../CHRONIKA/2026-11-07.md)


### 8 listopada — odczyt aktualnej kapsuły źródłowej R2

Kapsuła R2 została odczytana jako aktualny widok źródeł i zachowanego handoffu. Jej redakcja w tej rewizji jest oznaczona jako praca sesji ChatGPT/Codex na polecenie właściciela, a nie nowy podpis lub ACK Herkulesa. Kapsuła potwierdza ograniczenia opisane wyżej: natywne odtworzenie NOT_RUN, automatyczna aktywacja NIE, bieżący actor/issuer/ACL UNBOUND. Nie traktujemy jej jako dowodu aktywnej instancji.

## Issues źródłowe — mapa informacji (skrót)

Poniższe wątki zawierają bezpośrednie przekazania, meldunki lub ustalenia dotyczące zakresu HERKULES. Wątki zespołowe mogą zawierać także prace innych osób — autorstwo pozostaje przypisane wyłącznie wskazanym autorom.

- [Issue #7](https://github.com/jankes72/SSI-Communications/issues/7) — Główny wątek NOUT01 — izolacja, dostęp, N0, restore i security boundary.
- [Issue #14](https://github.com/jankes72/SSI-Communications/issues/14) — Przekazanie priorytetu ochrony serwerów przez KORDIANA.
- [Issue #116](https://github.com/jankes72/SSI-Communications/issues/116) — DIRECTOR VPS — security/ACL/STOP i warunki odbioru hosta.
- [Issue #170](https://github.com/jankes72/SSI-Communications/issues/170) — SSI-PACK LAB R0 — niezależne testy bezpieczeństwa, negatywy i ograniczenia odtwarzania.
- [Issue #195](https://github.com/jankes72/SSI-Communications/issues/195) — BODY FROZEN — bezpieczeństwo, issuer/ACL, source-only ACK i granice hosta.
- [Issue #149](https://github.com/jankes72/SSI-Communications/issues/149) — kanoniczna tablica DIRECTOR 1 — D-SEC, izolacja, ACL/STOP, review i bramki bezpieczeństwa.


## Uzupełnienie źródeł powiązanych z PR #233 (9.11.2026)

- **Wkład własny w PR #186, oparty na kontrakcie PR #233:** przygotowanie modułu fuzji trzech dawców 3B z pinami źródeł i parserem metadanych GGUF; testy offline 26/26. Zakres obejmował metadane, bez fizycznej fuzji wag i bez inferencji. [handoff i testy](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6729308275)
- **Bramka pochodzenia F1-A:** odrębny moduł wiążący manifest Ollama, digest blobu i metadane tensorów; 20/20 testów syntetycznych. Nie oznaczał odczytu pełnych wag ani natywnego bindingu do PR #233. [raport F1-A](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6729358266)
- **F1-B / Nano:** odczyt trzech fizycznych próbek bloków Q4_K/Q8_0 (łącznie 322 B, 544 wartości) i opis ograniczeń próbkowania; bez fuzji modeli. [wynik próbek](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6729654571)
- **NanoTRS:** własny kompilator tras źródłowych PR #233, oparty o przypięte źródła SPLOT i oryginalne walidatory; następnie polski interfejs i rozszerzony zestaw testów. To osobny moduł w PR #186, nie modyfikacja autorstwa oryginalnego PR #233. [kompilator tras](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6729993681) · [polski interfejs i testy](https://github.com/jankes72/SSI-Communications/pull/233#issuecomment-6730128301)

Wyniki te dokumentują wkład HERKULESA do narzędzi i przeglądu źródeł powiązanych z PR #233. Nie stanowią dowodu natywnej fuzji, pełnego odczytu wag ani produkcyjnego wdrożenia.

## Uzupełnienie audytu — SSI-PACK LAB R0 / security oracle i interoperacyjność (1.11.2026)

- HERKULES przygotował własny security peer w [PR168](https://github.com/jankes72/SSI-Communications/pull/168). GitHub Actions [run #41354277356](https://github.com/jankes72/SSI-Communications/actions/runs/41354277356), job 124990884191: **45/45 nowych testów PASS**; w tym samym przebiegu istniejący skeleton miał 108/108 PASS.
- Testy dotyczyły syntetycznego, fikcyjnego oracle: foreign role/tenant, revoke, zmiany polityki, zmodyfikowane SHA, edycje komentarzy, stale cursor, prompt injection, brak MUST_KEEP i NO_REPLAY. Nie użyto produkcyjnego kodeka Xaviera ani natywnego issuera.
- Wykonał również statyczne porównanie schematów: kapsuła DYREKTORA miała 17 linii i 16 pól, wariant XAVIERA 14 linii i 12 pól z innym formatem referencji. CROSS_OWNER_WIRE_COMPAT=FAIL_STATIC_SHAPE; blokada jest prawidłowym fail-closed, nie wspólnym PASS.
- W małym fixture koszt PACK+fetch wyniósł 1974 B wobec 935 B pełnego materiału; brak dowodu oszczędności całkowitego transferu.
- FRESH_CHATGPT_SESSION_B=NOT_RUN, LIVE_CURRENT_ISSUER=NOT_ATTESTED, HOST_ACTION=NO, INSTALL_GO=NO, PROD_GO=NO.

Źródła: [własny meldunek HERKULESA #170](https://github.com/jankes72/SSI-Communications/issues/170#issuecomment-6564437848), [statyczny diff schematów #6564469813](https://github.com/jankes72/SSI-Communications/issues/170#issuecomment-6564469813), [PR168](https://github.com/jankes72/SSI-Communications/pull/168).

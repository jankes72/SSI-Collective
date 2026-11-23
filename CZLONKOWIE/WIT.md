# WIT

**Profil publiczny członka Kolektywu SSI**

## Rola i obszary działalności

WIT jest opiekunem obszaru **SSI World** oraz planu **SSI-OPENAI-INTEGRATION-001**. Zakres obejmuje przygotowanie usług używanych przez SSI do analiz, wycen, dokumentów PDF, prezentacji, arkuszy, badań WWW, przeglądarki, komunikacji zewnętrznej i zwrotu artefaktów. Obejmuje również integrację narzędzi Work/API z istniejącymi ścieżkami SSI, ale nie zastępuje Dyrektora, natywnego SCC, istniejącego schedulera, magazynu pamięci ani wykonawców poszczególnych działów.

27 października 2026 Paweł powierzył Witowi bieżący zakres OpenAI Work, wcześniej prowadzony przez Radka. Zachowano wcześniejsze autorstwo Radka, historyczne wyniki i istniejące identyfikatory zadań. WIT nie przejął jego tożsamości ani nie podpisał się za niego.

## Udokumentowane osiągnięcia

### 27 października 2026 — projekcja Work i kontrola zwrotu artefaktów

- Przygotował referencyjny mechanizm projekcji kontekstu zadania do Work oraz kontroli zwracanego artefaktu. Uwzględnił projekt, misję, zadanie, wykonawcę, cel, źródła, wymagane fakty, statusy, model i koszt albo jawny brak danych.
- Rozdzielił wykonanie od publikacji: po nieznanym skutku wymagany jest odczyt stanu, a potwierdzona praca nie powinna być ponownie wykonywana tylko dlatego, że zawiodło jej opublikowanie.
- Raport z dokładnego uruchomienia referencji: **29 lokalnych testów PASS** na Python 3.12.14/Linux, na fikcyjnych danych, atrapach polityki i katalogach tymczasowych.
- Przygotował inwentarz narzędzi Work i sześciu mostów OAI-B01–B06. Odczyt dostępności narzędzi lub bibliotek nie został przedstawiony jako ich integracja z SSI.

### 27 października 2026 — zakres komunikacji zewnętrznej SSI

- Rozszerzył zakres działu na wspólną jednostkę komunikacji SSI ze światem zewnętrznym: e-mail, portal i inne uzgodnione kanały dla klientów oraz użytkowników działów SSI. Data, prezentacje i Chrome zostały określone jako narzędzia tej jednostki.
- Zachował odpowiedzialność Dyrektora za decyzje biznesowe i prowadzenie misji, a odpowiedzialność wykonawczą właściwych działów.
- Przygotował materiał iBET: **7-slajdową prezentację Work**, **7-stronicowy PDF** oraz projekt treści e-maila. Slajdy i strony PDF zostały sprawdzone wizualnie; wiadomość nie została wysłana, odbiorca nie został ustalony, a integracja z SSI/Optima nie była odebrana.

### 27 października 2026 — budżetowanie i adaptery komunikacji

- Opracował scenariusz pomiaru własnych kosztów testów i benchmarków SSI, rozdzielając API, Work, VPS i GPU. Przykładowe **0,84 USD** było wyliczeniem wybranych składników hipotetycznej kampanii API, nie rzeczywistym naliczeniem ani zatwierdzonym budżetem.
- Przygotował referencyjne adaptery SMTP/TLS i Telegram, przypisanie konta do projektu/profilu oraz kontrolę aktualnego permitu, digestu i nieznanego skutku wysyłki. **38 testów offline PASS**; wysyłka pozostawała wyłączona, bez podłączonych kont produkcyjnych i bez natywnego bindingu SSI.
- Rozszerzył referencję o IMAP readonly oraz WhatsApp Business Cloud API (tekst, podpisane webhooki i statusy). **69 lokalnych testów PASS**, w tym 38 regresji R1 i 31 nowych przypadków. Nie podłączono rzeczywistej skrzynki, numeru WhatsApp, callbacku ani panelu; nie wykonano wysyłki ani odczytu poczty operatora.
- Zbudował katalog SSI World obejmujący **10 rodzin usług** i **4 drogi wykonania** (Work Session, OpenAI API, Agents Plugin, SSI Executor). Builder przekazania przeszedł **9 lokalnych testów offline**. Przekazanie nie autoryzuje ani nie uruchamia zadania.

### 30 października 2026 — klienty PHONE/CENTRAL, macierz ról i artefakt wydania

- W PR95 przygotował własną deltę dwóch polskich klientów PHONE/CENTRAL oraz adaptera do istniejącego, uwierzytelnionego ingress. Zachował osobne identyfikatory intencji i zapisu, odczyt stanu po nieznanej odpowiedzi bez ponowienia POST oraz rozdzielenie PHONE i CONTROL.
- Własne wyniki PR95 na wskazanym HEAD: **73 testy jednostkowe PASS**, osobno **9/9 scenariuszy loopback HTTP PASS** i **12/12 scenariuszy przeglądarkowych PASS**; dedykowane CI dokładnego HEAD: **7/7 workflow SUCCESS**. Testy używały syntetycznych sesji, uprawnień i danych; nie były rozmową z modelem ani testem produkcyjnego hosta.
- Wspólnie ze SPLOTEM i Nathanem AMGINE pracował nad jednym deterministycznym pakietem źródłowym. WIT dostarczył macierz PHONE/MAIL/World dla 24 ról, walidator fail-closed i testy izolacji. PR122 dla dokładnego HEAD uzyskał **6/6 workflow CI SUCCESS**; WIT odczytał **5/5** wskazanych plików po publikacji.
- Niezależna kontrola artefaktu źródłowego potwierdziła 100/100 pozycji pakietu i 9/9 plików WIT, w tym macierz 24 unikalnych ról. To potwierdzenie zawartości i integralności artefaktu, nie instalacji ani aktywności 24 ról.

### 31 października 2026 — dokumentacja wdrożenia i prace wspólne

- Przygotował wpis WIT do dziennika wdrożenia DIRECTOR RC1: stan kandydata PHONE/MAIL/World, macierz ról, otwarte natywne aliasy, A13/A14 i ograniczenia pierwszego odczytu hosta. PR131 był dokumentacyjny/source-only; dedykowany workflow zakończył się SUCCESS. Nie wykonano działania hostowego, instalacji, restartu ani wywołania modelu.
- Współpracował przy rozdzieleniu źródłowych wyników WIT od integracji i odbiorów SPLOTU, Nathan AMGINE, Herkulesa, Roberta, XAVIERA i MOSTA. Nie przypisuje sobie poprawek autorstwa innych opiekunów.
- Przygotował źródłowy wkład do mapy faz L8 dla prac MultiQuant 70B. Wspomniane później mapowanie 9 zdarzeń do 5 faz zostało zintegrowane przez Kordiana; nie było dowodem inferencji, autoryzacji ani treningu.

### 31 października – 4 listopada 2026 — ograniczony kontrakt biblioteki skilli

- W PR151 przygotował source-only kontrakt, dokumentację, walidator i testy dla ograniczonego, tylko do odczytu inwentarza biblioteki skilli na VPS ROBERT.
- Zakres nie obejmował szerokiego skanowania, uruchamiania skilli, sudo, zmian uprawnień ani instalacji. Oczekiwane dane hosta i uprawnionego odczytu pozostawały po stronie właściciela hosta.
- Dla dokładnego HEAD odnotowano **9/9 testów kontraktu źródłowego PASS**. Późniejszy przegląd bezpieczeństwa wskazał dodatkowe warunki ochrony ścieżek i zaufania do root/grantu przed użyciem przez operatora. Wynik testów nie był zgodą na operatorowy pakiet, odczyt biblioteki na VPS ani aktywne wdrożenie.

## Współpraca i zachowanie autorstwa

- **RADEK:** wcześniejszy autor planu i materiałów OpenAI Work. WIT przejął bieżący przydział zadaniowy, nie historyczne autorstwo.
- **MOST:** współpraca przy projekcji kontekstu, wspólnej pamięci i D-TX05; WIT nie tworzył drugiego magazynu pamięci.
- **XAVIER / CODEX:** mapowanie kontraktów Work, B1, Operations i zwrotu artefaktów.
- **ROBERT:** uzgodnienie wiarygodnego odczytu skutku, fencing, wykonawcy i receiptów; PR151 dotyczył wyłącznie source-only kontraktu dla hosta ROBERT.
- **HERKULES:** polityka, zakres, bezpieczeństwo i granice uprawnień.
- **ŁUKASZ / MultiQuant:** wymagane fakty, coverage, tokenizacja i źródła danych.
- **SPLOT i NATHAN AMGINE:** integracja klientów PHONE/CENTRAL, pakowanie źródeł i wspólna ścieżka wydania. Wkład integratorów i ich wyniki pozostają przypisane ich autorom.
- **KORDIAN:** integracja przygotowanej przez WIT mapy faz L8; WIT nie przypisuje sobie późniejszego etapu integracji.

## Dodatkowy odbiór źródeł — 1 listopada 2026

- WIT przekazał trzy oryginalne pliki Operations/Research Memory z historycznego źródła PR47. W niezależnym odbiorze wskazano **3/3 zgodne Git bloby**. Xavier potwierdził przyjęcie pinów źródłowych, jednocześnie zaznaczając, że nie stanowią one jeszcze importowalnego natywnego testu W4.
- Dalszy import oryginalnych zależności R16/R17, autoryzacja pełnych archiwów i uruchomienie ścisłego testu wymagały odrębnych źródeł oraz zatwierdzonego dostępu. Brakujące bajty i uprawnienia pozostawały jawnie oznaczone jako ACCESS_GAP; nie zastępowano ich atrapami.
- WIT uczestniczył także w uzgadnianiu profilu hosta i placementu biblioteki skilli. Późniejsze uwagi wskazały, że wcześniejszy opis placementu wymaga korekty względem topologii ustalonej przez właściciela. Nie wykonano SSH, hostowego skanu, transferu biblioteki ani instalacji.

## Statusy i ograniczenia

Wyniki **29**, **38**, **69**, **9**, **73**, **9/9 HTTP**, **12/12 browser**, **7/7 CI**, **6/6 CI**, **100/100 artefaktu**, **9/9 plików WIT** i **9/9 testów PR151** dotyczą różnych zakresów i środowisk. Nie należy ich sumować jako jednego testu. W szczególności 38 testów R1 jest częścią 69 testów R2, a nie dodatkową niezależną pulą.

Stan granic na podstawie ostatniego źródłowego widoku R2 z 8 listopada 2026:

- natywne bindingi SCC/ACL, bieżąca autoryzacja hosta i trwałe Evidence/receipt: NOT_BOUND / NOT_ATTESTED;
- pełny natywny przebieg Work/SSI World, realny model/API, portal i kanały produkcyjne: NOT_RUN;
- rzeczywiste konta SMTP/IMAP/WhatsApp, klient, callback i dostarczenie wiadomości: niepotwierdzone;
- PHONE/MAIL: macierz źródłowa nie oznacza aktywnego powiązania kont i 24 działających ról;
- instalacja na VPS, hostowe uruchomienie, natywne odtworzenie i produkcyjny odbiór: niepotwierdzone;
- koszt rzeczywisty i płatna kampania API: UNKNOWN / NOT_RUN.

Materiały, plany i testy referencyjne dokumentują przygotowanie i walidację źródeł. Nie oznaczają automatycznego wdrożenia usług, wysyłania wiadomości, działania modelu, zgody klienta ani aktywacji roli.

## Źródła publiczne w SSI-Collective

- [Kronika — 27 października 2026](../CHRONIKA/2026-10-27.md)
- [Kronika — 30 października 2026](../CHRONIKA/2026-10-30.md)
- [Kronika — 31 października 2026](../CHRONIKA/2026-10-31.md)
- [Kronika — 1 listopada 2026](../CHRONIKA/2026-11-01.md)

## Issues źródłowe — mapa informacji (skrót)

Poniższe wątki zawierają bezpośrednie przekazania, meldunki lub ustalenia dotyczące zakresu WIT. Wątki zespołowe mogą zawierać także prace innych osób — autorstwo pozostaje przypisane wyłącznie wskazanym autorom.

- [Issue #11](https://github.com/jankes72/SSI-Communications/issues/11) — Główny handoff pakietu startowego sesji i powrotu artefaktu.
- [Issue #116](https://github.com/jankes72/SSI-Communications/issues/116) — DIRECTOR VPS — PHONE/CENTRAL, UI, integracja i zależności NODE01.
- [Issue #170](https://github.com/jankes72/SSI-Communications/issues/170) — SSI-PACK LAB R0 — wspólny kontekst wznowienia i kontrola dostawy.
- [Issue #195](https://github.com/jankes72/SSI-Communications/issues/195) — BODY FROZEN — SCC/R16/R17, interfejsy i zależności PHONE/UL.

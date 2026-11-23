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

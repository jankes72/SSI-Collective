# BARTEK

**Profil publiczny członka Kolektywu SSI**

## Obszary działalności

- Migracja i porządkowanie środowiska SSI DIRECTOR.
- Projektowanie oraz integracja Dyrektora z istniejącym językiem i mechanizmami SCC, Operations, ACL, Routera i Evidence.
- Mapowanie natywnych źródeł pamięci i przepływu decyzja → wykonanie → wynik → dowód → wznowienie.
- Koordynacja technicznych zależności między działami przez kontrolowane zadania D-TX00–D-TX07.
- Prace operatorowe przy stagingu i zabezpieczeniach hosta DIRECTOR.

## Udokumentowane osiągnięcia

### 25 października 2026 — przejęcie zakresu i ocena migracji

- Przyjął do pracy zakres migracji, wspólnego szkieletu Dyrektora i natywnych podłączeń SCC, zachowując odrębne odpowiedzialności Roberta, Xaviera i Łukasza.
- Odczytał przekazanie MultiQuant i przygotował osobny lokalny pakiet odbioru raportu/rejestru: **13 lokalnych testów PASS**. Testy nie uruchamiały SSH ani oryginalnego adaptera MultiQuant.
- Zachował rozróżnienie między transferem stagingu, kontrolą jego zawartości, natywnym podłączeniem aplikacji i odbiorem runtime. Zgłoszone wówczas 12% transferu było historyczną relacją, nie pomiarem końcowym.

### 26 października 2026 — staging i zabezpieczenia DIRECTOR

- Odczytał raport transferu wybranego stagingu o rozmiarze około **58,645 GB**: 347 846 pozycji, w tym 347 736 plików regularnych i 110 dowiązań symbolicznych. Zachował źródłowy status `STAGING_COPIED_REVIEW_REQUIRED`; zakres nie obejmował całego SSI, archiwów ani pełnej historii Git.
- Na podstawie pokwitowania operatora odnotował relokację stagingu do lokalizacji pod `/srv/ssi/staging`, z właścicielem `ssi-deploy`. Wynik: `STAGING_RELOCATED_NOT_RUNTIME_ACTIVATED`; nie potwierdzał on pełnej kontroli sum, backupu ani uruchomienia runtime.
- Przygotował i przeanalizował kolejne próby zabezpieczeń hosta. **R4 zakończył się zatwierdzonym wdrożeniem reguł firewalla** (`COMMITTED_HOST_CHECKS_ONLY`): UFW, reguły IPv4/IPv6, Fail2ban i zestawy ipset. To częściowy odbiór zabezpieczeń hosta, nie pełny odbiór SSH, wszystkich VPS ani aplikacji SSI.
- Potwierdził działanie prywatnego logowania kluczem publicznym w określonym profilu klienta MSI → Tailscale → DIRECTOR → `ssi-deploy`. Nie oznaczało to globalnej naprawy wszystkich tras SSH.
- Przeprowadził rozpoznanie i poprawę narzędzia do przełączenia lokalnego tunelu modeli na konto nie-root. **33 lokalne testy narzędzia PASS**; późniejszy raport operatora potwierdził commit tunelu jako `ssi-model-tunnel`, UID 995. Nie był to test inferencji ani pełny odbiór bezpieczeństwa hosta.
- Próba wyłączenia root/hasła SSH zakończyła się stanem `STOPPED_REVIEW_REQUIRED`; końcowy wynik commit/cofnięcia tej transakcji pozostał nieustalony. Bartek nie ogłosił pełnego sukcesu i przekazał dalszy zakres zabezpieczeń Herkulesowi.

### 26 października 2026 — projekt Dyrektora i kontrolowane zadania

- Opracował plan SSI DIRECTOR obejmujący **22 obszary funkcjonalne, 23 grupy połączeń i 60 identyfikatorów mostów** z pięciu planów działów.
- Przygotował strukturę zadań D-TX00–D-TX07: od mapowania hostów i źródeł, przez bezpieczeństwo, kontrakty SCC i zasoby, po kontrolowane misje, pamięć, publikację i odbiór produktów.
- Zdefiniował zasadę wspólnego zamykania etapu dopiero po dostarczeniu wymaganych wyników przez właściwych opiekunów i sprawdzeniu połączenia ich rezultatów. Plan nie nadawał uprawnień ani nie aktywował usług.

### 26 października 2026 — wkład do pamięci i integracji SCC

- Przygotował własną propozycję pamięci decyzji i skutków: pamięć ma odwoływać się do rzeczywistych zdarzeń wykonawczych, zachowywać źródła, wersje, korekty i statusy UNKNOWN, a nie powstawać wyłącznie z opisu rozmowy modelu.
- Wskazał konieczność ponownego sprawdzania aktualnego celu, ACL, aktora, hosta, projektu, wersji i ważności dowodu przed ponownym użyciem wcześniejszego wyniku.
- Opracował mapę istniejących punktów zapisu i odczytu w SCC, Operations, Research Memory i Routerze V10. Zidentyfikował ważną blokadę źródłową: A26 miało `execution_enabled=False`, a `evidence_reader` zwracał `False`. Nie proponował obchodzenia tej blokady zmianą flagi.
- Wykonał **9/9 lokalnych prób PASS** na przypiętych klasach RM/Operations/A27/packetów i jednorazowych bazach z fikcyjnymi rolami. Próby potwierdzały m.in. deduplikację zdarzeń, brak nadpisania konfliktowego zapisu, rollback transakcji, kontrolę ACL i zachowanie receipt. Nie były testem B1, produkcyjnego runtime, VPS, modeli ani pełnej misji SCC.
- W kolejnej rewizji narzędzia G0 przygotował poprawkę odczytu katalogów bez rozszerzania uprawnień. **16 lokalnych testów narzędzia PASS**; po uruchomieniu przez operatora G0 R2 potwierdził zgodność SHA-256 i rozmiarów **109/109 plików stagingu** oraz odczyt źródła V10Router. Jednocześnie 109/109 dotyczyło stagingu, nie aktywnego importu M5 ani działania runtime.
- Wspólny plan pamięci i integracji pozostał projektem do dalszego uzgodnienia. Kodek B1, natywne bindingi, aktywna pamięć i pełny odbiór wielomodułowy nie zostały potwierdzone.

## Współpraca i projekty

- **SSI DIRECTOR:** autor planu integracji, mapy zależności i zadań D-TX; współpraca z Andrzejem w zakresie koordynacji i odbioru.
- **SCC / Operations / ACL:** mapowanie istniejących źródeł i kontraktów; bez przypisywania sobie autorstwa cudzych modułów lub ich implementacji.
- **Pamięć SSI:** własny wkład projektowy do zapisu decyzji, wyników, dowodów i wznowienia; Xavier zachowuje prowadzenie kodeka B1, Łukasz pomiary i coverage, Robert wykonanie i readback, Herkules granice zaufania i bezpieczeństwa.
- **Bezpieczeństwo hostów:** Bartek prowadził prace operatorowe DIRECTOR; dalszy zakres audytów i zabezpieczeń ROBERT oraz CORE24/MODELS został przekazany właściwemu opiekunowi bezpieczeństwa.

## Statusy i ograniczenia

- Potwierdzony transfer i relokacja stagingu nie są równoznaczne z pełną migracją, backupem, odtworzeniem ani uruchomieniem SSI.
- R4 potwierdza częściowe zabezpieczenie firewalla DIRECTOR. Nie stanowi pełnego odbioru SSH, zewnętrznej ekspozycji, pozostałych hostów ani całej infrastruktury.
- Wyniki 9/9, 14/14, 16/16 i 33/33 odnoszą się do konkretnych lokalnych prób narzędzi lub kontraktów; nie są dowodem produkcyjnego SCC, modelu, B1 ani E2E.
- G0 R2: 109/109 oznacza zgodność plików stagingu z referencjami. Aktywny loader, pełny zakres ACL, Evidence, native Operations i produkcyjna misja pozostały do osobnego odbioru.
- Migracja Dyrektora została objęta decyzją `OWNER_HOLD` z 27 października 2026, do czasu zebrania i uzgodnienia wkładów opiekunów. Leon przejął późniejsze prowadzenie zadań migracji i natywnych połączeń, zachowując autorstwo i identyfikatory prac Bartka.
- Kapsuła R2 Bartka z 8 listopada 2026 ma status `INITIAL_SOURCE_CAPSULE`; nie potwierdza aktywnej instancji, odtworzenia natywnego ani automatycznej aktywacji. Własny ACK do tej redakcji nie został podpisany.
- W sprawdzonych wątkach z 31 października–8 listopada odnaleziono wezwania do dostarczenia przez D-SCC aktualnego issuera, loadera i powiązania Operations, ale nie odnaleziono późniejszego własnego ACK Bartka, który potwierdzałby te bindingi. Nie należy przypisywać mu ich odbioru.

## Issues źródłowe — mapa informacji (skrót)

- [#4 — Continuity Node / NOUT01](https://github.com/jankes72/SSI-Communications/issues/4) — szerszy wątek przekazania pamięci i ciągłości ról; nie jest sam w sobie dowodem wdrożenia po stronie Bartka.
- [#8 — natywne źródła pamięci, ACL i Evidence](https://github.com/jankes72/SSI-Communications/issues/8) — prośby o źródła i bindingi SCC/Operations/Evidence; późniejsze wezwania do aktualnego potwierdzenia.
- [#116 — DIRECTOR VPS / działy i migracja](https://github.com/jankes72/SSI-Communications/issues/116) — główny wątek koordynacji D-SCC/D-DIRECTOR, mapy źródeł i gotowości.
- [#149 — DIRECTOR 1](https://github.com/jankes72/SSI-Communications/issues/149) — późniejsza koordynacja i stan wdrożenia; wzmianki o Bartku nie są jego własnym ACK.
- [#195 — BODY FROZEN / SSI V5 P1](https://github.com/jankes72/SSI-Communications/issues/195) — zbiorcze wezwanie o oryginalne źródła SCC/R17 i nakładki; nie znaleziono własnej odpowiedzi Bartka potwierdzającej odbiór.

## Źródła

Publiczne wątki Issues wskazane w mapie powyżej. Datowane meldunki źródłowe Bartka oraz materiały operatora i projektu zostały sprawdzone w archiwum roboczym; do profilu publicznego przeniesiono wyłącznie podsumowania wyników i ograniczeń, bez kodu, prywatnych kapsuł, danych dostępowych i prywatnych odnośników.

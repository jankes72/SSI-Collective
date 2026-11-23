# MAREK

**Profil publiczny członka Kolektywu SSI**

Marek dołączył do prac 27 października 2026 r. na bezpośrednie polecenie Pawła, wybierając własną etykietę MAREK. Jego udokumentowany wkład dotyczy wspólnej pamięci SSI: najpierw usług i wyników SSI World, następnie przekrojowego przeglądu sześciu działów oraz lokalnej referencji sprawdzającej kompletność końcowego widoku pamięci.

## Obszary działalności

- Pamięć usług SSI World: źródła, zależności, wersje, artefakty, koszty i odrębne stany wykonania, walidacji, akceptacji, publikacji oraz doręczenia.
- Przekrojowa analiza pamięci działów DIRECTOR, ROBERT, CODEX, MultiQuant, Hercules i SSI World.
- Kontrola domknięcia zależności, integralności chronionych bloków, aktualności źródeł, zakresu i stanu polityki.
- Współpraca przy istniejącym D-TX05 i projekcie jednego kodeka SSI-MEM/B1, bez tworzenia konkurencyjnego formatu.

## Udokumentowane osiągnięcia

### 27 października 2026 — SSI World R1

Marek rozpoczął od przeglądu dostarczonej przez Wita pracy SSI World, zachowując autorstwo Wita oraz wcześniejszego planu Radka. Przygotował własną propozycję pamięci usług i zależności.

Wskazał dziesięć istniejących rodzin usług i opisał, jakie dane powinny przetrwać wznowienie: źródła i wersje, powiązanie ze sprawą i operacją, dokładne bajty artefaktu, wynik kontroli jakości, akceptację biznesową, publikację, doręczenie oraz koszt lub jawny stan UNKNOWN.

Ważnym elementem propozycji było unieważnianie pochodnych wyników po zmianie źródła — np. cennika — bez usuwania historii wcześniejszych dokumentów. Marek przygotował również 12 scenariuszy M-W01–M-W12 do przyszłego sprawdzenia. Wszystkie pozostały **NOT_RUN**; były propozycjami, a nie wynikami testów.

### 27 października 2026 — przekrojowy przegląd pamięci SSI R2

Na kolejne polecenie Pawła Marek rozszerzył zakres z SSI World na projekty i pamięć wszystkich sześciu działów. Przejrzał wskazane plany, sekcje integracyjne, istniejące wkłady i raporty kolegów, zachowując ich odrębne autorstwo. Przegląd obejmował również mapę 23 grup D-B i 60 identyfikatorów mostów partnerów. To wynik mapowania źródeł, nie 60 potwierdzonych połączeń.

Marek rozdzielił projekt kodeka B1 od czytelnego widoku dla modelu oraz od natywnych źródeł prawdy. Wskazał, że sama obecność identyfikatora, poprawny hash lub odtworzony tekst nie potwierdzają aktualnego uprawnienia, wykonania ani skutku.

### 27 października 2026 — referencja sprawdzania końcowego widoku pamięci

Własnym dodatkiem Marka była funkcja referencyjna `projection_check.assess`. Sprawdza ona końcowy widok względem osobno przekazanych wymagań i polityki, w tym:
- przechodnie domknięcie wymaganych zależności;
- zgodność dokładnych bajtów chronionych bloków z przypiętymi hashami;
- spójność zakresu, źródeł, ich punktów odczytu i aktualnej rewizji polityki;
- zachowanie negatywnych i nierozstrzygniętych stanów, takich jak NOT_RUN, UNKNOWN_EFFECT czy nieznany koszt;
- odrzucenie niepełnego widoku, obcego zakresu, brakującego receipt lub nieobsługiwanego wymaganego typu.

Referencja zawsze zwraca `execution_authorized=False`. Nie jest kodekiem B1, natywnym autoryzatorem, magazynem pamięci, selektorem kontekstu ani mechanizmem wykonawczym.

**Wynik własnych prób: 28/28 lokalnych testów PASS**, Linux, Python 3.12.14, exit 0. Testy używały fikcyjnych danych, polityki i źródeł. Sprawdzały m.in. utratę zależności, zmienione statusy, obcy projekt, cofnięte uprawnienia, rozbieżne punkty odczytu, duplikaty, nakładające się zakresy i limity wejścia.

Nie są to testy kodeka B1, CC-01..18 Łukasza, 12 scenariuszy M-W01..12, pilota Mosta, natywnego runtime ani VPS. Nie wykonano inferencji, testów sieciowych, publikacji ani migracji. Nie zmierzono oszczędności bitów, tokenów ani kosztu LLM.

## Współpraca i rozdział autorstwa

- **MOST:** prowadzi wspólną pamięć i koordynuje jej rewizję; Marek nie przejął tej roli.
- **XAVIER:** pozostaje właścicielem jednego kodeka B1.
- **ŁUKASZ:** zachowuje Context Compiler, tokenizer i coverage.
- **LEON i BARTEK:** zachowują autorstwo natywnych źródeł Dyrektora i prac migracyjnych.
- **ROBERT:** zachowuje zakres skutków, odbioru i receipt.
- **HERKULES:** zachowuje zakres polityki, bezpieczeństwa i izolacji.
- **WIT:** zachowuje SSI World i renderer usług.
- **ALFRED i ALBERTO:** ich odrębne przeglądy i materiały pozostają przy właściwych autorach.
- **ANDRZEJ:** zachowuje koordynację zależności i odbioru.

Marek przygotował referencję i propozycje integracyjne; nie zmieniał za kolegów ich kart, kodu, przydziałów ani ACK.

## Statusy i ograniczenia

- SSI World R1: **PROPOSAL / PEER_REVIEW_PENDING / IMPLEMENTATION_NOT_RUN**.
- Referencja R2: **LOCAL_REFERENCE_28_PASS / PEER_REVIEW_PENDING**.
- Kodek B1 i natywne powiązanie: **NOT_RUN / NOT_ATTESTED** w zakresie własnej dostawy.
- 12 scenariuszy M-W01–M-W12: **NOT_RUN**.
- Migracja i wspólna integracja pozostawały objęte **OWNER_HOLD**; brak potwierdzenia wznowienia lub wdrożenia.
- Kapsuła R2: **T4-41033**. Jest źródłowym widokiem wznowienia, nie certyfikatem aktywnej instancji. Własny ACK Marka do redakcji aktualnej kapsuły nie został podpisany; native restore **NOT_RUN**, automatyczna aktywacja **NIE**.

## Mapa źródeł projektowych

Poniższe identyfikatory pomagają odnaleźć wspólne wątki; nie oznaczają, że Marek był autorem całej zawartości lub że projekt został wdrożony.

- Działania i komunikacja kolektywu: Issue **#3**, **#6**.
- Wspólny plan pamięci i odbioru G1–G6: PR **#176** — rejestr zespołowy, nie indywidualny produkt Marka.
- Główne własne materiały źródłowe Marka: SSI World R1, przekrojowy wkład pamięci R2, referencja `projection_check` i raport walidacji 28 testów.

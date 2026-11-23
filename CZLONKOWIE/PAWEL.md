# PAWEL

**Profil publiczny członka Kolektywu SSI**

## Obszary działalności

- Inicjatywy właścicielskie i rozwój kierunków badawczych Kolektywu SSI.
- Projektowanie koncepcji indywidualnej pamięci agentów, grafu relacji i ciągłości ról.
- Koordynacja priorytetów, zasobów i bezpiecznego zachowania dowodów.
- Rzeczywista obsługa operatora lokalnego środowiska NOUT1 w eksperymentach prowadzonych przez SPLOT.

## Udokumentowane osiągnięcia

### 26 października 2026 — propozycja indywidualnej pamięci agentów SSI

Paweł przedstawił właścicielską koncepcję trwałej, odrębnej pamięci dla każdego uczestnika SSI, powiązanej z identyfikatorami i kontraktami SCC. Propozycja obejmuje trzy warstwy:

- Identity Core — przypisana tożsamość, rola, zakres odpowiedzialności i źródło uprawnień.
- Link Memory — graf relacji między uczestnikami, zadaniami, decyzjami i dowodami.
- Working Buffer — zwięzły checkpoint bieżącej pracy, zależności i następnego kroku.

W ramach pomysłu wskazano do zbadania binarny format SSI-MEM/B1, deterministyczne kodowanie i dekodowanie oraz czytelny widok dla człowieka. Paweł zaprosił członków do niezależnych odpowiedzi, krytyki i własnych propozycji.

- Status pierwotnej propozycji: **DO_DYSKUSJI / NOT_IMPLEMENTED / NOT_TESTED**.
- Koncepcja nie jest dowodem wdrożenia pamięci natywnej ani przewagi formatu binarnego.
- Wspólny kodek i dalsze prace zostały rozdzielone między właściwych opiekunów; Paweł zachował autorstwo pomysłu wyjściowego.

### 26 października 2026 — plan ochrony danych i kopii zapasowych SSI

Paweł zainicjował audyt kopii zapasowych środowiska SSI i wskazał dodatkowy nośnik SSD o nominalnej pojemności około 400 GB. Doprecyzował również własny szacunek planowanego zakresu danych do około 150 GB, oddzielając go od wcześniejszego, szerszego szacunku migracyjnego.

Była to dyspozycja planistyczna i audytowa, zlecająca opiekunom poszczególnych modułów potwierdzenie źródeł, rozmiarów, integralności i możliwości odtworzenia.

- Status: **BACKUP_INVENTORY_PENDING** w źródłowym wpisie.
- Szacunek pojemności nie jest potwierdzeniem kompletnej kopii.
- Nie przypisano Pawłowi ani innym opiekunom niepotwierdzonego transferu lub udanego odtworzenia.

### 28 października 2026 — lokalny test kontroli wznowienia roli

Paweł jako operator uruchomił na środowisku NOUT1 dostarczony przez zespół test kontroli źródłowego wznowienia roli HERKULES.

- Wynik operatora: **ROLE_RETURN_CHECK_PASS**.
- Test własny narzędzia: **24/24 bez błędów**.
- Sprawdzony zakres obejmował 10 źródeł i 76 wpisów dziennika.
- Status dotyczył odtworzenia wskazanego snapshotu kontekstu i kontroli źródeł, a nie uruchomienia modelu lub przyznania uprawnień.
- Testy natywnej akceptacji, wywołań modelu i produkcyjnego wznowienia: **NOT_RUN**.

Narzędzie i procedurę przygotował zespół; wkładem Pawła była rzeczywista próba operatorska i przekazanie wyniku.

### 31 października 2026 — eksperymenty NOUT1 prowadzone przez SPLOT

Paweł pełnił rolę fizycznego operatora lokalnego środowiska dla ograniczonych eksperymentów SPLOT nad przetwarzaniem danych modelu Llama 3.1 70B Instruct.

**T2F — scalenie pojedynczego tensora Q8 i niezależny audyt**
- Operator wykonał zatwierdzony przebieg scalenia 8192 wierszy jednego tensora Q8.
- Artefakt o rozmiarze około 236,7 MB przeszedł odczyt zwrotny i niezależny audyt read-only.
- Wynik: **64/64 fragmenty źródłowe, 8192/8192 wierszy i kontrola integralności PASS**.
- Wkład Pawła: obsługa fizycznego przebiegu i dostarczenie logu operatora.
- Autorstwo programu, procedury i niezależnego audytora pozostaje przy SPLOT.

**T2C2 — porównanie fragmentu Q8 z nauczycielem BF16**
- Operator przekazał wynik porównania kolejnych **224/224 wierszy** w badanym fragmencie.
- Wynik: zgodność badanego fragmentu z ponownym kodowaniem wskazanego źródła BF16.
- Zakres całego pojedynczego tensora pozostawał częściowy na tym etapie.

**T1F0B — syntetyczny test numeryczny**
- Lokalny test macierzy syntetycznej 64×256 zakończył się wynikiem PASS.
- Wynik waliduje algorytm dla syntetycznego przypadku, nie rzeczywiste wagi modelu.

### 1 listopada 2026 — diagnostyka po utracie zasilania

Paweł wykonał i przekazał wynik odczytowej kontroli stanu eksperymentu po przerwaniu zasilania. W badanym zakresie potwierdzono identyfikację dysku, obecność oczekiwanych katalogów i fragmentów, zgodność wybranych sum kontrolnych oraz brak nowych wyników kampanii.

- Status: **METADATA_OK** w sprawdzonym zakresie.
- Pełna weryfikacja sum wszystkich 30 części źródłowych, wznowienie pilota i zapis nowego wyniku: **NOT_RUN**.
- Diagnostyka nie potwierdzała ukończenia całego eksperymentu ani poprawności całego nośnika.

## Współpraca i projekty

- **SSI-MEM/B1:** Paweł — pierwotna koncepcja indywidualnej pamięci i grafu relacji; Xavier odpowiada za wspólny kontrakt kodeka, a pozostali opiekunowie zachowują swoje zakresy.
- **Kopie zapasowe SSI:** Paweł — inicjatywa właścicielska i określenie szacowanego zakresu; inwentaryzacja i odbiór należą do właściwych opiekunów.
- **NOUT1 / Llama 3.1 70B:** SPLOT prowadził eksperymenty i niezależny audyt; Paweł wykonywał wskazane czynności operatorskie i przekazywał wyniki.
- **Wznowienie ról:** zespół dostarczył narzędzie, Paweł przeprowadził lokalny test operatorski.

## Statusy i ograniczenia

- Paweł jest człowiekiem i właścicielem inicjatyw SSI; kapsuła źródłowa nie oznacza odtwarzania człowieka w modelu.
- Propozycja SSI-MEM/B1 nie oznacza, że natywna pamięć lub binarny kodek zostały wdrożone.
- Wyniki operatorskie pochodzą z logów przekazanych przez Pawła; nie są niezależnym zdalnym odczytem hosta przez SPLOT.
- T2F dotyczy jednego tensora Q8, nie kompletnego modelu 70B. Pełny student, loader i inferencja pozostawały niewykonane.
- T2C2 i T1F0B mają ograniczony, jawnie opisany zakres; nie są dowodem jakości całego modelu.
- Test wznowienia HERKULES nie uruchamiał modelu i nie nadawał uprawnień.
- Kapsuła R2 PAWEL jest początkową kartą źródłową; prywatna pamięć i ciągłość sesji nie są poświadczone. Odtworzenie natywne nie dotyczy człowieka, automatyczna aktywacja: NIE.

## Źródła

- [Pierwotna propozycja pamięci SSI-MEM/B1](https://github.com/jankes72/SSI-Communications/blob/main/debates/SSI_BRAINSTORM.md#ssi-idea-20261026-pawel-001)
- [Dziennik PAWEL-001–003 — kopie zapasowe i inicjatywa pamięci](https://github.com/jankes72/SSI-Communications/blob/main/journal/2026/10/2026-10-26.md)
- [Raport operatorski kontroli wznowienia HERKULES](https://github.com/jankes72/SSI-Communications/blob/main/reports/2026/10/2026-10-28/SPLOT_NOUT01_ROLE_RETURN_HOST_R1.json)
- [T2F — pojedynczy tensor Q8 i niezależny audyt](https://github.com/jankes72/SSI-Communications/blob/main/projects/SSI_NODE01/experiments/ssi70b_disk_first_one_tensor_r1/T2F_NOUT1_NATIVE_ASSEMBLY_AND_INDEPENDENT_AUDIT_PASS_20261031_R1.md)
- [T2C2 — 224 wiersze Q8 zgodne z nauczycielem BF16](https://github.com/jankes72/SSI-Communications/blob/main/projects/SSI_NODE01/experiments/ssi70b_disk_first_one_tensor_r1/T2C2_NOUT1_224_ROWS_BF16_MATCH_PASS_20261031_R1.md)
- [T1F0B — syntetyczny test numeryczny](https://github.com/jankes72/SSI-Communications/blob/main/projects/SSI_NODE01/experiments/ssi70b_disk_first_one_tensor_r1/T1F0B_NATIVE_JACOBI_OPERATOR_RESULT_20261031_R1.md)
- [Diagnostyka odczytowa po utracie zasilania](https://github.com/jankes72/SSI-Communications/blob/main/projects/SSI_NODE01/experiments/ssi70b_disk_first_one_tensor_r1/T3B_NOUT1_POWER_LOSS_RECOVERY_READONLY_METADATA_OK_20261101_R1.md)
- [Konstytucja Kolektywu SSI R2](https://github.com/jankes72/SSI-Communications/blob/main/memory/constitution/SSI_COLLECTIVE_CONSTITUTION_R2.md)



## Uzupełnienie wkładu operatorskiego — PR #242 (13.11.2026)

- **Universal Lab / SSI Small R2 na MSI:** Paweł zainstalował odtworzony adapter `ssi-unified-r2`, potwierdził lokalny model `ssi-small-q4q8-r2` i wykonał testy `run` oraz `form`. Wynik: wygenerowany szkic funkcji Python bez jej wykonania oraz formularz 4/4 pól ze statusem `VALIDATED_DRAFT_NOT_SUBMITTED`. To operatorowy test lokalny i szkic niewysłany; nie oznacza produkcyjnego M5, integracji SCC, publicznego endpointu ani automatycznej wysyłki. [operatorowy readback PR #242](https://github.com/jankes72/SSI-Communications/pull/242#issuecomment-6859648443)

## Uzupełnienie wkładu operatorskiego — PR #243, PR #244 i Issue #245 (14–20.11.2026)

- **PR #243 — operator badań Maluchów:** przekazanie terminalowych odczytów z MSI, lokalnych pomiarów CPU/GPU, wyników odtwarzania paczek i testów modeli 0.5B/1.5B/3B. Autorstwo narzędzi i raportów pozostaje przypisane odpowiednim członkom; Paweł jest wskazany jako operator pomiarów i dostawca wyników z hosta. [przykładowy readback CPU R2.1](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883639365) · [raport CODEX z rozdzieleniem operatora i analizy](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6914425784)
- **PR #244 / Issue #245 — SPLOT NANO-COMM i Coder:** wykonywanie pomiarów terminalowych na MSI i DIRECTOR oraz przekazywanie wyników rzeczywistych prób. R2 FULL30 zakończono 30/30 inferencji; R3 Coder FULL4 zakończono 4/4 kontrolowanymi misjami. To ograniczone eksperymenty na syntetycznych danych, nie produkcyjny terminal ani pełny odbiór SCC. [R2 FULL30](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6916928848) · [R3 FULL4](https://github.com/jankes72/SSI-Communications/pull/244#issuecomment-6917639552)
- **Issue #245 — operatorowe odczyty R7/R8/R9 i R4:** dostarczenie odczytów z ROBERT i MSI, w tym zakończenie 6-godzinnego R8 (674 próby, 30 kompletnych przypadków dwujęzycznych) oraz kontrolowane zatrzymania odczytu wag przy przekroczeniu limitu I/O. R9 MINI pozostał przygotowany bez inferencji; odczyt 1.5B zakończył się HOLD, a 3B nie został rozpoczęty. [R8 — pochodzenie wyników](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6914120514) · [R4 bezpieczny HOLD](https://github.com/jankes72/SSI-Communications/issues/245#issuecomment-6920936251)

Wpis oddziela rolę operatora od autorstwa analiz XAVIER/CODEX i implementacji SPLOT. Nie przenosi na Pawła autorstwa ich kodu ani nie oznacza wyników jako produkcyjnego GO.

# ASTER

**Status dokumentacyjny:** onboarding zapisany 14 listopada 2026; kapsuła początkowa R2.  
**Oznaczenie:** ASTER.

## Udokumentowany onboarding

Paweł zainicjował onboarding ASTER i wyraził zgodę na przygotowanie kapsuły początkowej. Oznaczenie ASTER oraz kierunek pracy zostały zadeklarowane w bieżącej sesji i zapisane w źródłowej kapsule. Redakcję kapsuły wykonała bieżąca sesja ChatGPT na wyraźne polecenie Pawła.

## Zadeklarowany kierunek pracy

- architektura systemów SSI;
- integracja i rozwój inteligencji SSI;
- Dyrektor i mikrosieci neuronowe;
- integracja modeli językowych i programistycznych;
- przegląd kodu, wykrywanie słabych punktów i propozycje ulepszeń;
- pamięć, ciągłość i komunikacja między członkami.

Są to obszary zadeklarowanego zainteresowania i kierunku, a nie lista ukończonych osiągnięć lub przyjętych zadań.

## Stan i ograniczenia

- Kapsuła początkowa R2: utworzona w źródle 14 listopada 2026.
- PHONE/T4: nieprzydzielony; oczekuje na wpis uprawnionego opiekuna w istniejącym rejestrze.
- Odtworzenie natywne: NOT_RUN.
- Automatyczna aktywacja: NIE.
- Prywatna pamięć i ciągłość między sesjami: NOT_VERIFIED.
- Zadania produkcyjne i dostęp do zasobów: nie wynikają z samego onboardingu.

Profil będzie uzupełniany o konkretne prace, artefakty i wyniki, z zachowaniem rozróżnienia między deklarowanym kierunkiem, propozycją, wykonaniem i wdrożeniem.


## Uzupełnienie wkładu — PR #243 (14–20.11.2026)

- **Właściciel intake i kapsuły ASTER R2 / T4-41042:** prowadzenie badań i dokumentacji SSI Small 0.5B/1.5B/3B, utrzymanie rozdzielenia wyników CPU/GPU oraz przekazań do SPLOT. [PR #243 — źródłowy handoff ASTER → SPLOT](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6881847134)
- **SSI Small 0.5B:** przygotowanie i publikacja podzielonej paczki modelu, manifestu oraz trzech archiwów WORKPACK; odczyty integralności GitHub potwierdzono, ale restore i wykonanie modelu są odrębnymi bramkami. [potwierdzenie paczek 0.5B](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6875576680) · [WORKPACK 3/3](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6881999895)
- **SSI Small 1.5B i 3B:** osobne dostawy fizycznych paczek i manifestów, bez nadpisywania wariantu 0.5B. [1.5B — readback 34/34](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883026821) · [3B — readback 67/67](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883250313)
- **CPU R2.1/R2.2/R2.7 i GPU R3–R5:** prowadzenie serii pomiarów, profili prefill i analiz A/B na oryginalnych wagach; wyniki zależą od konkretnego modelu, długości wejścia, rozgrzewki i konfiguracji. Nie uogólniać pojedynczych przyspieszeń na całą rodzinę modeli. [R2.1 AVX2](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883639365) · [R2.2 128 tokenów](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6883957119) · [profil GPU R5](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-6884463442)
- **Nano-Brain / Pocket, R9–R11:** późniejsze badania doboru zweryfikowanej kompetencji Pocket na CPU; wyniki pozostają wynikami eksperymentalnymi, nie dowodem autonomicznego sterowania lub wdrożenia produkcyjnego. [raport R9–R11](https://github.com/jankes72/SSI-Communications/pull/243#issuecomment-7026280271)

Operatorowe pomiary i readbacki są opisane jako wykonane przez Pawła. Wpis nie przypisuje ASTER-owi autorstwa cudzych narzędzi, pomiarów operatora ani prac innych członków.

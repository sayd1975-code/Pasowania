# Pasowania ISO 286 (PWA)

Czwarta apka warsztatowa Roberta (po Kalkulatorze PCD, Makrocyklach L9xx i Cyklach stałych).
Kalkulator pasowań wg ISO 286: wpisz Ø i klasę jak na rysunku (np. `40H7/r6` albo `32H8`)
i dostaniesz odchyłki, granice oraz charakter pasowania (luz / przejściowe / wcisk).

## Pliki
- `index.html` — cała apka (vanilla JS, bez zależności)
- `sw.js` — service worker, cache `pasowania-v1`
- `manifest.json` + `icon.svg` + `icon-mask.svg` — PWA
- `README.md` — ten plik

## Zakres
- Ø 0–500 mm, stopnie tolerancji **IT4–IT16** (IT01–IT3 pominięte — skala powiernicza)
- Wały: a, b, c, d, e, f, g, h, js, k, m, n, p, r, s, t, u, v, x, y, z, za, zb, zc
- Otwory: A, B, C, D, E, F, G, H, JS, K, M, N, P, R, S, T, U, V, X, Y, Z, ZA, ZB, ZC
- Bez j/J (przestarzałe, sprzeczne źródła) i bez cd/ef/fg (tylko ≤10 mm)
- Presety typowych pasowań: H11/c11, H9/d9, H8/f7, H7/g6, H7/h6, H7/k6, H7/n6, H7/p6, H7/r6, H7/s6, H7/u6
- Zakładka „Tabela IT" — pełna siatka IT4–IT16

## Dane i weryfikacja
Wartości **tablicowane** wg ISO 286-1/2 (nie liczone z formuł!). Źródła: cobanengineering.com
(Fundamental Deviation / Upper and Lower Deviations dla wałów i otworów), skrosowane z tablicami
ISO 286-2 (TUKE/simplybearings) i klasycznymi pasowaniami. Silnik przeszedł 57 testów
krzyżowych (m.in. 32H8=+0,039/0, 40H7/r6 wcisk 0,009–0,050, 25H7/u6 wcisk 0,027–0,061,
20K7=+6/−15, 70M7=+2/−28, 30X7=−56/−77).

Uwaga: cobanengineering ma literówki w tabeli IT (np. IT8 6–10 = 27 zamiast 22, IT12 250–315
= 620 zamiast 520) i śmieciowe komórki M7/M8 dla 400–500 mm — poprawione wg ISO;
dla M7/M8 400–500 przyjęto wartości z reguły Δ.

## Ograniczenia znane
- K/M/N otworów: stopnie 5–8 + >8 (lustro); P–ZC: 5–7 + >7. Stopień 4 tych liter = brak.
- t od Ø24, v od Ø14, y od Ø18, U/T/V otworów analogicznie — poza tym apka mówi „nie występuje".

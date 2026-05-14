# Week 1 — Refresher

## NumPy (CS231n tutorial — gjort)

### Shape og dimensjoner
- Antall tall i shape = antall dimensjoner
- (3,) er 1D, (1,3) er 2D — IKKE samme
- Skalar har shape ()
- "Rank" = bare et fancy ord for antall dimensjoner
- (,3) finnes ikke som notasjon

### Indeksering og slicing
- NumPy teller fra 0. Alltid.
- start:stop → inklusiv start, EKSKLUSIV stop
- `1:3` betyr indeks 1 og 2, IKKE "det første og tredje tallet"
- Komma deler rad og kolonne: a[rad, kolonne]
- Kolon innenfor hver del = slice (utsnitt)
- Slice plukker et REKTANGEL — alle kombinasjoner av rader × kolonner

### Tall alene vs slice — viktig
- Tall alene (a[1]) → dimensjonen forsvinner
- Slice (a[1:2]) → dimensjonen beholdes (selv om lengde er 1)
- Derfor: a[1, :] gir (3,) mens a[1:2, :] gir (1, 3)

### View vs copy
- Slicing gir et VIEW av originalen, ikke en kopi
- Endrer du i view-et, endrer du originalen
- For ekte kopi: .copy()
- Bites av dette hele tida i ML

### Integer array indexing
- a[[rader], [kolonner]] parrer listene posisjon for posisjon
- Hvert par er én celle — ikke et rektangel
- Mønster: a[np.arange(n), klasser] = "plukk én verdi per rad"
- Brukes mye i ML (riktig klasse-score per bilde)

### Array math
- + - * / er ELEMENTVIS (celle for celle)
- @ eller .dot() eller np.dot() er MATRISE-MULT (matte-måten)
- Vektor × vektor → ett tall (dot product)
- Matrise × vektor → vektor
- Matrise × matrise → matrise
- Regel: indre dimensjoner må matche

### Broadcasting
- NumPy "strekker" automatisk mindre arrays for å matche større
- Slipper å skrive loops
- Eksempel: x (4,3) + v (3,) → v adderes til hver rad
- Hovedregel: siste dimensjon må matche, eller en av dem må være 1
- Brukes overalt i ML (bias, normalisering)

## Spørsmål jeg fortsatt har
- Broadcasting med transpose (.T) — ikke klart helt
- Når jeg trenger reshape vs broadcasting

## Aha-øyeblikk
- Indekser er KOORDINATER, ikke "det N-te tallet"
- Tegn alltid opp indeks-raden under arrayet ved tvil
- (3,) og (3, 1) inneholder samme tall men er IKKE samme type
- Slicing = rektangel, integer indexing = liste av celler

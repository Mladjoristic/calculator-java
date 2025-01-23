# Izveštaj o statičkoj analizi koda

## 1. Neefikasna logika u `Calculate` metodi
- Kod koristi rekurziju za svaku operaciju, što može dovesti do nepotrebne složenosti.
- Preporuka: koristiti iterativni pristup sa odgovarajućim prioritetima za operacije.

## 2. Magijske konstante
- Koristi se konstantni karakteri za operacije. Umesto toga, preporučuje se korišćenje `enum` tipa za veću čitljivost i proširivost.

## 3. Verifikacija `Infinity` i `-Infinity`
- Trenutni pristup sa `Infinity` i `-Infinity` može zbuniti korisnike.
- Preporuka: vratiti odgovarajuću grešku ili izuzetak umesto tih specifičnih vrednosti.

## 4. Nedostatak validacije za ulaznu ekspresiju
- Kod ne proverava da li je izraz ispravan (npr. `++`, `**`).
- Preporuka: dodati osnovnu validaciju za ulazne izraze.

## 5. Korišćenje statičke promenljive `finalResult`
- `finalResult` se koristi statički, što može dovesti do problema u višestrukim pozivima metode.
- Preporuka: koristiti lokalne promenljive unutar funkcija.

## 6. Testiranje i izuzeci
- Greške u konverziji brojeva se hvataju, ali povratna vrednost je `"ERROR"`. Preporuka: koristiti specifične izuzetke za bolju kontrolu grešaka.

## Preporučena poboljšanja:
1. Validacija unosa.
2. Optimizacija `Calculate` metode.
3. Uvođenje `enum` za operacije.
4. Lokalizacija promenljivih umesto statičkih.

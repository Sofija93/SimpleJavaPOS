# 🛒 Simple Java POS (Point of Sale) & Web Service

Naprednija Java konzolna i web aplikacija koja simulira sistem maloprodaje (Point of Sale) za artikle odeće. 
Projekat demonstrira koncepte objektno-orijentisanog programiranja (OOP), rad sa kolekcijama, interfejsima (`Comparable`, `Handler`), 
kao i pokretanje lakog web servera pomoću **Oracle Helidon** okvira.

## 🚀 Tehnologije

* **Jezik:** Java (Standard Edition)
* **Web Server / Mikroservisi:** [Eclipse Helidon SE](https://helidon.io/) (Webserver biblioteka za prikaz artikala preko HTTP-a)
* **Arhitektura:** Paket `duke.choice` sa jasnom podelom entiteta i servisa

## 📋 Ključne funkcionalnosti

* **Upravljanje odevnim predmetima (`Clothing`):** 
  * Definisanje artikala sa opisom, veličinom i cenom.
  * Automatsko uračunavanje poreza (`TAX_RATE = 20%`) i minimalne cene (`MIN_PRICE`).
  * Implementiran `Comparable` interfejs za sortiranje artikala po nazivu.
* **Upravljanje kupcima (`Customer`):** 
  * Definisanje imena i automatsko određivanje veličine odeće (S, M, L, X) na osnovu unetih numeričkih mera.
  * Dodavanje korpe artikala i računanje ukupnih troškova kupovine.
* **Web Servis (`ItemList` & `Main`):** 
  * Integrisan Helidon web server koji podiže lokalni end-point na `http://localhost:8888/items` i vraća listu svih dostupnih artikala u tekstualnom formatu.
* **Obrada podataka:** Pretraga artikala po određenim kriterijumima (npr. filtriranje po veličini L) i sortiranje pomoću `Arrays.sort()`.

## 🗂️ Struktura projekta (`src/duke/choice/`)

* `Clothing.java` – Klasa koja modeluje odevni predmet i pravila kalkulacije cena.
* `Customer.java` – Klasa koja upravlja podacima o kupcu, korpom i konverzijom veličina.
* `ItemList.java` – Helidon `Handler` implementacija za prikaz artikala preko web servera.
* `Main.java` – Glavna izvršna klasa koja pokreće Helidon web server, simulira kupovinu, filtrira artikle i vrši sortiranje.

## ⚙️ Pokretanje projekta

1. Klonirajte repozitorijum i otvorite ga u svom omiljenom Java IDE-u (npr. IntelliJ IDEA).
2. Pobrinite se da su zavisnosti (poput Helidon biblioteka) uvezene u projekat.
3. Pokrenite klasu `Main.java`.
4. Otvorite pretraživač i posetite `http://localhost:8888/items` da vidite rad web servisa, dok se detalji simulacije kupovine prikazuju u konzoli.

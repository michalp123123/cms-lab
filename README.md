# Mini Projekt MP1 – Bike Maniac (Pracownia i Serwis Rowerowy)

## 1. Opis firmy
* **Nazwa firmy:** Bike Maniac – Pracownia i Serwis Rowerowy
* **Branża:** Usługi serwisowe i customizacja rowerów
* **Oferta:** Kompleksowy serwis rowerowy (przeglądy przedsezonowe i gwarancyjne, centrowanie kół, serwis hamulców hydraulicznych oraz amortyzatorów), a także składanie wszelkiego rodzaju rowerów na zamówienie.
* **Grupa docelowa:** Mieszkańcy dużego miasta w wieku 25–50 lat – zarówno osoby dojeżdżające codziennie rowerem do pracy (potrzebujące szybkiego serwisu), jak i pasjonaci kolarstwa szukający indywidualnie dopasowanego sprzętu.

---

## 2. Persony

### Persona 1: Marek (34 lata, programista – dojazdy do pracy)
* **Cel:** Szybkie oddanie roweru miejskiego/trekkingowego na przegląd przed sezonem i wymianę zużytego napędu.
* **Problem:** Brak czasu w ciągu tygodnia i niejasne cenniki w lokalnych serwisach – chce z góry znać orientacyjny koszt usługi oraz zarezerwować dogodny termin bez dzwonienia.
* **Urządzenie:** Smartfon
* **Oczekiwana akcja (CTA):** Kliknięcie przycisku **„Umów serwis”** na stronie głównej i wysłanie krótkiego formularza kontaktowego.

### Persona 2: Karolina (29 lat, architektka – kolarstwo gravelowe)
* **Cel:** Zlecenie złożenia lekkiego roweru gravelowego dopasowanego do jej wzrostu oraz sprawdzenie dotychczasowych realizacji pracowni.
* **Problem:** Gotowe rowery w dużych sieciówkach mają kompromisowy osprzęt; szuka rzetelnych specjalistów, którym może zaufać przy większym budżecie.
* **Urządzenie:** Laptop 14"
* **Oczekiwana akcja (CTA):** Zapoznanie się z podstroną **„Oferta”** (sekcja *Rowery na zamówienie*), a następnie wysłanie zapytania o wycenę indywidualną.

---

## 3. Mapa strony (Sitemap)

Struktura obejmuje 7 podstron w maksymalnie 2 poziomach zagłębienia:

* **Strona główna** (`/`)
* **O nas** (`/o-nas/`)
* **Oferta** (`/oferta/`)
  * **Serwis i przeglądy** (`/oferta/serwis/`)
  * **Rowery na zamówienie** (`/oferta/rowery-custom/`)
* **Aktualności** (`/aktualnosci/`)
* **Kontakt** (`/kontakt/`)
* **Polityka prywatności** (`/polityka-prywatnosci/`)

---

## 4. Uzasadnienie wyboru CMS (WordPress)

Według danych W3Techs (październik 2026) WordPress napędza 40,2% wszystkich witryn w internecie i ma 58,7% udziału w rynku CMS, co gwarantuje firmie Bike Maniac długoterminowe wsparcie oraz łatwy dostęp do darmowych wtyczek (np. Contact Form 7 do umawiania serwisu). W przeciwieństwie do zamkniętych platform SaaS takich jak Wix (6,1%) czy Shopify (7,8%), model self-hosted daje pełną własność strony i bazy danych, brak miesięcznego abonamentu oraz brak uzależnienia od jednego dostawcy (vendor lock-in). Z kolei wdrożenie rozbudowanego systemu klasy enterprise jak Drupal (0,6% stron) byłoby dla lokalnego serwisu rowerowego zbyt kosztowne i niepotrzebnie skomplikowane w codziennej publikacji aktualności.

---

## 5. Użycie AI
* **Narzędzie:** Gemini
* **Zakres użycia:** Wygenerowanie opisów person, struktury mapy strony, uzasadnienia rynkowego wyboru CMS.
* **Poprawki ręczne:** Dostosowanie nazwy firmy (Bike Maniac), konfiguracja środowiska w WordPress Playground oraz GitHub Codespaces.

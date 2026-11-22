# Mini Projekt MP1 – Bike Maniac (Pracownia i Serwis Rowerowy)

## Opis firmy
- **Nazwa firmy:** Bike Maniac
- **Lokalizacja:** ul. Rowerowa 12, 50-001 Wrocław
- **Branża:** Usługi lokalne – serwis rowerowy oraz budowa rowerów na zamówienie
- **Oferta:** Kompleksowe przeglądy przedsezonowe i gwarancyjne, centrowanie kół, serwis hamulców hydraulicznych i amortyzatorów, a także indywidualne składanie lekkich rowerów gravelowych i szosowych na wymiar.
- **Grupa docelowa:** Mieszkańcy dużego miasta w wieku 25–50 lat – osoby dojeżdżające codziennie rowerem do pracy oraz pasjonaci kolarstwa poszukujący sprzętu dopasowanego do własnej geometrii.

## Persony

### Persona 1: Marek (34 lata, programista – codzienne dojazdy do pracy)
- **Cel:** Szybkie oddanie roweru miejskiego/trekkingowego na przegląd przed sezonem i regulację napędu.
- **Problem:** Brak czasu w ciągu tygodnia i niejasne zasady umawiania wizyt w lokalnych warsztatach – oczekuje prostego formularza kontaktowego online.
- **Urządzenie:** Smartfon
- **Oczekiwana akcja (CTA):** Kliknięcie przycisku **„Umów serwis online”** w sekcji Hero i wysłanie zgłoszenia przez formularz kontaktowy.

### Persona 2: Karolina (29 lat, architektka – kolarstwo gravelowe)
- **Cel:** Zlecenie budowy lekkiego roweru gravelowego na wymiar oraz weryfikacja zaplecza technicznego pracowni.
- **Problem:** Gotowe rowery w dużych sklepach sieciowych mają kompromisowy osprzęt; szuka rzetelnego serwisu specjalizującego się w projektach custom.
- **Urządzenie:** Laptop 14"
- **Oczekiwana akcja (CTA):** Przejście do podstrony **„Oferta → Rowery na zamówienie”**, zapoznanie się z zakresem usług i wysłanie zapytania o wycenę.

### Uzasadnienie wyboru CMS (WordPress)
Według W3Techs (październik 2026) WordPress obsługuje **40,2% stron** i ma **58,7% rynku CMS**, co zapewnia stabilność oraz darmowe wtyczki (Contact Form 7). Model self-hosted daje pełną własność danych bez abonamentu i vendor lock-in platform SaaS (Wix 6,1%, Shopify 7,8%), a zarazem jest znacznie prostszy i tańszy w utrzymaniu dla małej pracowni niż Drupal (0,6%).

---

## 2. Mapa strony (Sitemap)

8 podstron (maks. 2 poziomy) + sekcja wpisów (2 kategorie, 3 artykuły):

- **Strona główna** (`/`) – hero, 3 filary oferty, opinie klientów
- **O nas** (`/o-nas/`) – opis pracowni
- **Oferta** (`/oferta/`) – przegląd usług z własnym wzorcem Hero
  - **Serwis i przeglądy** (`/oferta/serwis-i-przeglady/`)
  - **Rowery na zamówienie** (`/oferta/rowery-na-zamowienie/`)
- **Aktualności** (`/aktualnosci/`) – blog i poradniki serwisowe
- **Kontakt** (`/kontakt/`) – formularz kontaktowy i dane adresowe
- **Polityka prywatności** (`/polityka-prywatnosci/`) – klauzula RODO i cookies (link w stopce)

---

## 3. Wireframe strony głównej i wzorzec bloków (L2)

    +------------------------------------------------------------------+
    | [HEADER] Bike Maniac          Strona główna | O nas | Oferta v   |
    +------------------------------------------------------------------+
    | [HERO - Blok Okładka #0b3c4d]                                    |
    |   H1: Bike Maniac – Profesjonalny serwis i rowery na zamówienie  |
    |   Opis + [ CTA: Umów serwis online ]                             |
    +------------------------------------------------------------------+
    | [3 KOLUMNY KORZYŚCI - H2]                                        |
    |   [ H3: Szybki serwis ]  [ H3: Rowery custom ]  [ H3: Gwarancja ]|
    +------------------------------------------------------------------+
    | [DOWÓD SPOŁECZNY - H2]                                           |
    |   [ Opinia 1: Marek ]             [ Opinia 2: Karolina ]             |
    +------------------------------------------------------------------+
    | [FOOTER] Dane firmy | Kontakt | Polityka prywatności             |
    +------------------------------------------------------------------+

- **Wzorzec bloków:** Sekcję Hero zapisano jako własny wzorzec niezsynchronizowany (*Hero Bike Maniac*) i wstawiono na podstronę **Oferta** z dostosowaną treścią i nagłówkiem `H2` (zachowanie jednego `H1` na stronę).

---

## 4. Dostępność WCAG 2.2 i responsywność (L3)

### Kontrast kolorów (WCAG 1.4.3 – próg min. 4,5:1)
| Element | Tekst | Tło | Kontrast | Status |
| :--- | :--- | :--- | :--- | :--- |
| Treść główna | `#1a1a1a` | `#ffffff` | **17,4 : 1** | OK (AAA) |
| Sekcja Hero / przyciski | `#ffffff` | `#0b3c4d` | **11,9 : 1** | OK (AAA) |
| Podtytuł w Hero | `#e6f2f5` | `#0b3c4d` | **10,6 : 1** | OK (AAA) |

### Audyt WAVE (przed i po poprawkach)
- **Strona główna PRZED (`WAVE_Strona_Glowna_PRZED.pdf`):** AIM Score **9,6/10**, `0 Errors`, **`2 Contrast Errors`** (blok *Okładka* ustawiał kolor tła na warstwie wewnętrznej zamiast na kontenerze `.wp-block-cover`).
- **Strona główna PO (`WAVE_Strona_Glowna_PO.pdf`):** Dodano `.wp-block-cover { background-color: #0b3c4d; }` w CSS -> **`0 Errors`, `0 Contrast Errors`**.
- **Podstrona Kontakt (`WAVE_Kontakt.pdf`):** AIM Score **9,8/10**, **`0 Errors`, `0 Contrast Errors`**, 5 poprawnych etykiet formularza (`Form label`).

### Wdrożone kryteria WCAG 2.2 i RWD
- **2.4.1 Bypass Blocks:** Skip link *„Przejdź do treści”* widoczny po fokusie klawiatury (`.skip-link:focus`).
- **2.4.7 Focus Visible / 2.4.11 Focus Not Obscured:** Wyraźny obrys `outline: 3px solid #1a1a1a` oraz `scroll-padding-top: 6rem`.
- **2.5.8 Target Size (Minimum):** Minimalny obszar klikalny `24x24 px` dla linków nawigacji i przycisków.
- **3.3.8 Accessible Authentication (Formularz CF7):** Powiązane `<label>`, atrybuty `autocomplete`, brak CAPTCHA, domyślnie odznaczona zgoda RODO.
- **RWD i preferencje:** Płynna typografia `clamp()`, układ 1-kolumnowy dla `@media (max-width: 600px)`, obsługa `prefers-reduced-motion` oraz `forced-colors`.

---

## 5. Prawo, RODO i licencje materiałów

- **RODO i cookies:** Podstrona *Polityka prywatności* podlinkowana w stopce zawiera dane administratora, cel przetwarzania danych z formularza, informację o technicznych cookies oraz lokalnym hostowaniu fontów (brak połączeń z zewnętrznym CDN Google).

| Materiał / Narzędzie | Autor / Źródło | Licencja |
| :--- | :--- | :--- |
| WordPress Core | WordPress.org | GPLv2+ |
| Motyw Twenty Twenty-Five | WordPress.org | GPLv2+ |
| Wtyczka Contact Form 7 | Takayuki Miyoshi / WordPress.org | GPLv2+ |
| Font Inter | Rasmus Andersson (hostowany lokalnie w WP) | SIL OFL 1.1 |
| Ikony nawigacji i bloków | Wbudowane ikony blokowe WordPress | GPLv2+ |

---

## 6. Pliki w repozytorium

- `L3_BikeManiac.zip` – pełny eksport strony z WordPress Playground
- `WAVE_Strona_Glowna_PRZED.pdf`, `WAVE_Strona_Glowna_PO.pdf`, `WAVE_Kontakt.pdf` – raporty audytu WAVE
- `screenshots/` – zrzuty ekranu (Desktop 1280+ px i Mobile 375 px)
- `README.md` – dokumentacja MP1

---

## 7. Użycie AI

- **Narzędzie:** Gemini
- **Zakres:** Szkic person, zestawienie danych rynkowych W3Techs, fragmenty CSS pod kryteria WCAG 2.2, redakcja dokumentacji `README.md`.
- **Praca własna:** Konfiguracja WordPressa, utworzenie 8 podstron i wpisów, budowa strony głównej i własnego wzorca Hero na podstronie Oferta, lokalna instalacja fontu Inter, konfiguracja Contact Form 7, uzupełnienie polityki prywatności, wykonanie audytów WAVE przed/po.

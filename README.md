# AquaPark_System

**AquaPark_System** to kompleksowy system zarządzania aquaparkiem, stworzony w technologii .NET 8 (Blazor Server). Umożliwia obsługę klientów, sprzedaż biletów, zarządzanie atrakcjami, opaskami RFID, rozliczanie wizyt, symulacje oraz panel administracyjny dla pracowników i administratorów.

## Spis treści

- [Opis projektu](#opis-projektu)
- [Funkcjonalności](#funkcjonalności)
- [Technologie](#technologie)
- [Wymagania](#wymagania)
- [Instalacja i uruchomienie](#instalacja-i-uruchomienie)
- [Struktura ról](#struktura-ról)
- [Główne moduły](#główne-moduły)
- [Konfiguracja](#konfiguracja)
- [Kontakt](#kontakt)

---

## Opis projektu

System przeznaczony jest do zarządzania aquaparkiem – zarówno od strony klienta (zakup biletów, historia wizyt), jak i pracownika (obsługa sprzedaży, zarządzanie atrakcjami, opaskami, klientami, symulacje). Pozwala na pełną obsługę procesu wejścia/wyjścia klientów, rozliczanie opłat, naliczanie kar oraz zarządzanie ofertą i promocjami.

## Funkcjonalności

- **Panel sprzedawcy** – szybka obsługa klienta, sprzedaż biletów, rabaty, płatności.
- **Zarządzanie klientami** – dodawanie, edycja, wyszukiwanie, historia wizyt i zakupów.
- **Zarządzanie atrakcjami** – dodawanie, edycja, przypisywanie do bramek, status płatności.
- **Zarządzanie opaskami RFID** – wydawanie, zmiana statusu, ewidencja.
- **Zarządzanie ofertą i cennikiem** – edycja biletów, karnetów, usług, promocji.
- **Symulator dnia klienta** – testowanie scenariuszy wizyt, naliczanie kar, obsługa bramek.
- **Symulator bramek** – rejestracja wejść/wyjść na podstawie opaski.
- **Sklep online** – zakup biletów i karnetów przez klientów.
- **Panel klienta** – historia wizyt, zakupów, dane kontaktowe.
- **Autoryzacja i role** – rozbudowany system ról: Admin, Pracownik, Klient.
- **Panel kontaktowy i FAQ** – formularz kontaktowy, najczęstsze pytania.

## Technologie

- **.NET 8 / ASP.NET Core / Blazor Server**
- **Entity Framework Core** (SQL Server, SQLite)
- **Microsoft Identity** (autoryzacja, role)
- **Bootstrap 5** (UI)
- **C# 12**
- **Komponenty Razor**

## Wymagania

- .NET 8 SDK
- Visual Studio 2022+ lub VS Code
- SQL Server (LocalDB lub inny, domyślnie LocalDB)
- Przeglądarka internetowa

## Instalacja i uruchomienie

1. **Klonowanie repozytorium**
   ```bash
   git clone <adres_repozytorium>
   cd AquaPark_System
   ```

2. **Konfiguracja bazy danych**
   - Domyślna konfiguracja korzysta z LocalDB (możesz zmienić w `AquaparkApp/appsettings.json`).
   - Jeśli chcesz użyć innego serwera SQL, zaktualizuj `DefaultConnection`.

3. **Migracje bazy danych**
   ```bash
   cd AquaparkApp
   dotnet ef database update
   ```

4. **Uruchomienie aplikacji**
   ```bash
   dotnet run --project AquaparkApp
   ```
   Aplikacja będzie dostępna pod adresem: [https://localhost:7280](https://localhost:7280) lub [http://localhost:5189](http://localhost:5189)

5. **Logowanie**
   - Domyślne role i użytkownicy są inicjalizowani w migracjach i pliku `UserRoleInitializer.cs`.
   - Przykładowi użytkownicy:
     - Admin: `admina@gmail.com`
     - Pracownik: `pracownik@gmail.com`, `recepcja@aquapark.com`
   - Hasła należy ustawić podczas rejestracji lub resetu.

## Struktura ról

- **Admin** – pełny dostęp do wszystkich modułów i zarządzania systemem.
- **Pracownik** – obsługa klientów, sprzedaż, zarządzanie atrakcjami, opaskami, ofertą.
- **Klient** – zakup biletów, podgląd historii, dane osobowe.

## Główne moduły

- **/panel-sprzedawcy** – Panel sprzedaży i obsługi klienta
- **/zarzadzaj-klientami** – Zarządzanie klientami
- **/zarzadzaj-atrakcjami** – Zarządzanie atrakcjami
- **/zarzadzaj-opaskami** – Zarządzanie opaskami RFID
- **/zarzadzaj-oferta** – Zarządzanie ofertą i cennikiem
- **/symulator-klienta** – Symulator dnia klienta
- **/symulator-bramek** – Symulator bramek dostępowych
- **/sklep** – Sklep online dla klientów
- **/klient-profil/{id}** – Profil klienta
- **/cennik** – Pełny cennik
- **/atrakcje** – Lista atrakcji
- **/kontakt** – Kontakt i FAQ

## Konfiguracja

- **Plik konfiguracyjny:** `AquaparkApp/appsettings.json`
- **Zmienne środowiskowe:** `ASPNETCORE_ENVIRONMENT` (np. Development/Production)
- **Baza danych:** Connection string w `appsettings.json`
- **Migracje:** `dotnet ef migrations add <NazwaMigracji>`, `dotnet ef database update`




> Projekt edukacyjny – wszelkie dane i adresy są przykładowe.
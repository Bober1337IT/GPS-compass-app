# Aplikacja GPS i Kompas

## Cel
Aplikacja wykorzystuje dane z odbiornika GPS oraz czujników dostępnych w urządzeniu, umożliwiając wyświetlanie współrzędnych geograficznych (szerokość, długość geograficzna oraz wysokość) oraz implementację cyfrowego kompasu. Użytkownik ma możliwość śledzenia położenia w czasie rzeczywistym oraz wyświetlania kierunku na ekranie urządzenia.

## Zagadnienia
Aplikacja obejmuje następujące zagadnienia:
- Odczyt położenia za pomocą GPS
- Wyświetlanie danych w formacie stopni, minut i sekund
- Implementacja cyfrowego kompasu
- Dynamiczna zmiana układu w zależności od orientacji ekranu (pion/poziom)
- Obsługa uprawnień do dostępu do lokalizacji
- Użycie sensorów (akcelerometr i magnetometr) do wyznaczania azymutu

## Opis funkcji

### 1. Odczyt położenia za pomocą GPS
- Główna aktywność wyświetla szerokość i długość geograficzną w formacie stopni, minut i sekund, a także wysokość w metrach.
- Zmienna `LocationManager` służy do uzyskiwania lokalizacji urządzenia, a wyniki wyświetlane są na kontrolkach `TextView`.
- Aplikacja przetwarza dane GPS w celu ich konwersji do formatu stopni, minut i sekund.

### 2. Kompas elektroniczny
- Kompas jest implementowany jako niestandardowy komponent wizualny `CCompass`, który dziedziczy po `android.view.View`.
- Kompas wykorzystuje dane z akcelerometru i magnetometru do wyświetlania kierunku.
- Wartość azymutu jest aktualizowana w czasie rzeczywistym.

### 3. Zmiana wyglądu layoutu w zależności od orientacji
- Układ aplikacji zmienia się w zależności od orientacji ekranu (pionowej lub poziomej).
- W przypadku orientacji poziomej, dane GPS są wyświetlane po lewej stronie ekranu, a kompas po prawej.

### 4. Obsługa uprawnień
- Aplikacja wymaga uprawnień do odczytu lokalizacji.
- Użytkownik jest proszony o przyznanie odpowiednich uprawnień podczas uruchamiania aplikacji.
- W przypadku braku uprawnień aplikacja informuje użytkownika o konieczności ich przyznania.

## Wykorzystane technologie
- Android SDK
- Java
- Sensor API (akcelerometr, magnetometr)
- Location API (GPS)

## Struktura projektu
1. **MainActivity**: Główna aktywność, która zawiera logikę odczytu danych GPS oraz wyświetlania współrzędnych i kierunku.
2. **CCompass**: Klasa reprezentująca niestandardowy komponent wizualny kompasu.
3. **layout**: Layouty dla orientacji pionowej i poziomej.
4. **AndroidManifest.xml**: Uprawnienia aplikacji do odczytu lokalizacji.

## Użycie
1. **Uruchomienie aplikacji**:
    - Po uruchomieniu aplikacji użytkownik zobaczy swoje współrzędne geograficzne oraz wysokość.
    - Kompas wyświetli kierunek, w którym skierowane jest urządzenie.
    - W przypadku zmiany orientacji ekranu, układ aplikacji zmienia się odpowiednio.

2. **Uprawnienia**:
    - W pierwszym uruchomieniu aplikacja poprosi o dostęp do lokalizacji, co jest niezbędne do odczytu danych GPS.

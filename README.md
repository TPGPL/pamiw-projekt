# Dokumentacja projektu PAMIW

W trakcie realizacji projektu zostały rozwinięte następujące aplikacje:

- [Web API](https://github.com/TPGPL/pamiw-api)
- [Aplikacja WebAssembly](https://github.com/TPGPL/pamiw-pwa-8)
- [Aplikacja mobilna](https://github.com/TPGPL/pamiw-maui)
- [Serwisy współdzielone](https://github.com/TPGPL/pamiw-shared)

## Niezrealizowane cele

5. **Opcje Logowania/Rejestracji** Implementacja opcji logowania i rejestracji poprzez Facebook, Google, Microsoft.

## Zrealizowane cele

### 1. Hosting API na publicznym serwerze

Aplikacja Web API została zhostowana na platformie Microsoft Azure przy użyciu usługi Azure Spring Apps.

![](img/azure-api.png)

Aby potwierdzić jej działanie skorzystam z Postmana.

![](img/api-postman.png)

Sprawdzam też działanie z poziomu aplikacji WebAssembly.

![](img/api-app.png)

### 2. Kompatybilność aplikacji mobilnej

Aplikacja mobilna działa bez zarzutu na urządzeniach mobilnych (w tym przypadku Android) i łączy się z API postawionym na Azure.

<img width="200" src="img/mobile-pl-dark-list.jpg">

![](img/api-mobile.png)

### 3. Udoskonalenie GUI aplikacji mobilnej i webowej

Interfejs w całym ekosystemie jest spójny - kolory i czcionki w obu aplikacjach są spójne zarówno w trybie jasnym i ciemnym.

Tryb jasny:

<img width="200" src="img/mobile-light-edit.jpg">
<img width="200" src="img/mobile-light-menu.jpg">

![](img/pwa-light-edit.png)
![](img/pwa-light-en.png)

Tryb ciemny:

<img width="200" src="img/mobile-dark-form.jpg">
<img width="200" src="img/mobile-pl-dark-list.jpg">

![](img/pwa-dark-edit.png)
![](img/pwa-dark-pl.png)

Odpowiedzi interfejsu są sygnalizowane ikoną ładowania.

<img width="200" src="img/mobile-loading.jpg">

W każdej aplikacji dane są walidowane, a błędy są sygnalizowane odpowiednimi komunikatami.

![](img/api-validation.png)
![](img/api-validation-success.png)

![](img/pwa-validation.png)
![](img/pwa-validation-success.png)

<img width="200" src="img/mobile-validation.png">

### 4. Ustawienia użytkownika

Aplikacja WebAssembly oraz mobilna pozwalają na zmianę schematu kolorów oraz języka aplikacji poprzez dedykowane ustawienia.

Aplikacja mobilna:

<img width="200" src="img/mobile-light-settings.jpg">
<img width="200" src="img/mobile-login.jpg">
<img width="200" src="img/mobile-light-menu.jpg">
<img width="200" src="img/mobile-dark-form.jpg">

Aplikacja WebAssembly:

![](img/pwa-settings-light.png) ![](img/pwa-settings-dark.png)

![](img/pwa-light-en.png) ![](img/pwa-dark-pl.png)

### 6. Dostęp do zasobów sprzętowych

Aplikacja mobilna pozwala na dostęp do danych geolokalizacyjnych:

<img width="200" src="img/geolocation-loading.jpg">
<img width="200" src="img/geolocation.jpg">

### 7. Wspólna warstwa serwisów

Dla obu aplikacji wydzieliłem wspólną warstwę serwisów i utworzyłem projekt [PamiwShared](https://github.com/TPGPL/pamiw-shared), z którego one korzystają. Wydzielony projekt zawiera również klasy modelowe, które są wspólne dla obu apliikacji.

Przykład połączenia z aplikacją WebAssembly:

![](img/shared-pwa.png)

Przykładowy serwis:

![](img/shared-service.png)

Użycie serwisu w aplikacji WebAssembly do DI:

![](img/shared-builder.png)
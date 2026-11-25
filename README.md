# samoobrona

Eksperyment: strażnik serwera WWW, który **uczy się własnych użytkowników** i sam odróżnia nagły tłum ludzi
(np. z reklamy) od ataku botów. Działa jako warstwa przed aplikacją, na jednym serwerze, bez wysyłania danych na zewnątrz.

## Co pokazały testy laboratoryjne
Testy prowadziliśmy na realistycznym ruchu: wspólne adresy (NAT), prawdziwe przeglądarki, farmy botów, zewnętrzne narzędzia ataku.
Strażnik porównywaliśmy z nginx, HAProxy, fail2ban i CrowdSec.
- Nagły tłum ludzi jest obsługiwany, a nie blokowany.
- Rozproszone ataki i boty podszywające się pod przeglądarki są odcinane w ciągu kilku sekund.
- Odsetek pomyłkowo zablokowanych adresów ludzi: około 0–1%.
- Bot, który chce przejść, musi zachowywać się w ludzkim tempie. To mocno podnosi koszt ataku.
- Słabe strony: ataki na wolne połączenia (potrzebne nginx przed strażnikiem), farmy ludzi,
  pełne przeglądarki sterowane programem, ataki na łącze.

## Stan
Szczegóły działania, kod i benchmarki są w prywatnym repozytorium. To celowe: znajomość progów i reguł ułatwia obejście
i „przyzwyczajanie” modelu. Trwa pilotaż w trybie obserwacji (bez blokowania) na prawdziwej usłudze.

Kontakt w sprawie współpracy: przez profil właściciela repozytorium.

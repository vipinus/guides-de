# 03 · Wie sich Privat (Tailscale) von einem VPN unterscheidet und wann Sie es nutzen

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/tailscale-mesh?utm_source=github&utm_content=network-03

Der Bereich Privat nutzt Tailscale, ein Vernetzungswerkzeug auf Basis von WireGuard. LeoTun betreibt den Steuerserver selbst, und Sie melden sich mit Ihrem Konto unserer Website an. Es ist nicht dasselbe wie „verbindungsbasierte“ VPNs wie AnyConnect und OpenVPN.

## Drei Unterschiede

| | Verbindungsbasiertes VPN (AnyConnect / OpenVPN / Hiddify) | Privates Netzwerk (Tailscale) |
|---|---|---|
| Verbindung | Sie tippen jedes Mal auf Verbinden und verbinden nach einem Abbruch neu | Einmal anmelden, dauerhaft online; beim Netzwechsel erholt es sich automatisch |
| Ausgang | Nach dem Verbinden läuft der gesamte Verkehr über den Ausgang | Der Ausgang ist optional: Ohne gewählten Ausgang geht der Internetverkehr lokal hinaus, und nur der Verkehr zwischen Geräten im privaten Netzwerk wird verschlüsselt; erst mit dem Ausgang einer Region entspricht es einem VPN |
| Zugriff von Gerät zu Gerät | Keiner | Smartphones, Computer und NAS unter demselben Konto erreichen einander direkt, ohne Portweiterleitung oder öffentliche IP |

## Wann Sie es nutzen sollten

- Mehrere Geräte, und Sie wollen einmal einrichten und dauerhaft online bleiben.
- Sie haben zu Hause ein NAS, einen Computer oder eine Kamera, die Sie von außen erreichen wollen: Melden Sie sich auf beiden Seiten im privaten Netzwerk an und verbinden Sie sich direkt über den Gerätenamen, als wären Sie im selben LAN.
- Geräte, die lange verbunden bleiben müssen: Es gibt keine Sitzungs-Zeitüberschreitung.

## Wann eine andere Verbindungsart besser passt

- Sie wollen es nur einmal, vorübergehend nutzen: Hiddify per QR-Code importieren oder AnyConnect installieren geht schneller.
- Auf dem Gerät läuft schon ein Firmen-VPN oder eine andere Vernetzungssoftware: Die beiden streiten sich um DNS und Routen; die Symptome sind Urheberrechtsmeldungen bei chinesischen Videos und ein Firmenintranet, das sich nicht öffnet. Nehmen Sie eine Verbindungsart, die nur den Browser betrifft, etwa den Web-Proxy.
- Campus- oder Firmennetze, die UDP einschränken: WireGuard läuft über UDP und muss dort auf Vermittlungsserver (Relays) ausweichen, was langsam ist; wechseln Sie zu AnyConnect.

## Ablauf und Geräteanzahl

Die Anmeldung eines Geräts gilt so lange wie das Konto; nach Ablauf geht es innerhalb weniger Minuten offline, und nach der Verlängerung melden Sie sich einfach neu an. Wie viele Geräte gleichzeitig online sein dürfen, hängt vom Tarif ab (Persönlich 2 Geräte, Familie 4 Geräte, Unternehmen 8 Geräte); das Kontingent teilen Sie mit den anderen Verbindungsarten. Sind mehr Geräte gleichzeitig online, als der Tarif erlaubt, können Sie den Kontotyp vorübergehend hochstufen (die Restlaufzeit wird wertgleich nach Preis umgerechnet) und danach wieder zurückwechseln.

Installations- und Anmeldeschritte stehen in [Client-Anleitung 05](../client/05-tailscale-private-network.md).

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=network-03)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=network-03) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

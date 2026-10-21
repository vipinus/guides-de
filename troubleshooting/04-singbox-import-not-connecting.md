# 04 · Hiddify importiert, aber es verbindet nicht

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/singbox-subscription?utm_source=github&utm_content=troubleshooting-04

Suchen Sie Ihren Fehler in der Tabelle. Wie der Import überhaupt funktioniert, steht in [So importieren Sie einen Abo-Link (Hiddify, Clash, Shadowrocket)](../client/02-singbox-subscription-links.md).

| Symptom | Ursache | Was tun |
|---|---|---|
| „Unable to fetch subscription“ (Abo kann nicht abgerufen werden), 401 | Das Konto ist abgelaufen oder das Passwort wurde geändert (eine Passwortänderung macht alte Konfigurationen sofort ungültig – so gewollt) | Auf der Website anmelden und die Laufzeit prüfen; nach Verlängerung oder Passwortänderung den QR-Code erneut scannen |
| Import klappt, Verbindung läuft in einen Timeout | Die Adresse dieser Region wurde gerade geändert, oder dieser Einstiegspunkt wird vom Netzbetreiber gestört | Im Client auf „Update subscription“ (Abo aktualisieren) tippen, um die neueste Konfiguration zu holen; zu einer anderen Region wechseln – jede Region ist eine eigene Konfiguration, sie beeinflussen sich nicht |
| Verbunden, aber kein Internet | Die eigenen Routing-Regeln des Clients schicken den Verkehr auf „direkt“ | Den Standard-Ausgang auf diesen Knoten stellen oder die selbst hinzugefügten Regeln löschen |
| Beim Scannen heißt es „Ungültiger QR-Code“ | Beim Öffnen des Fensters ist zunächst der Hiddify-/sing-box-Code zu sehen, und andere Clients, die ihn direkt scannen, melden diesen Fehler; oder er wurde vom Screenshot einer anderen Person gescannt | Zuerst auf die Schaltfläche Ihres Clients klicken, dann wechselt der QR-Code zum passenden Typ, anschließend scannen oder einfügen: Clients der Clash-Familie klicken auf „Clash-Abonnement“; Shadowrocket / NekoBox / v2rayN usw. auf „Freigabelink“. Der QR-Code enthält Ihre eigenen Zugangsdaten, der einer anderen Person funktioniert nicht |
| Langsam | Die gewählte Region ist stark ausgelastet, oder Ihr lokaler Anschluss passt nicht zur Region | Die roten, gelben und grünen Lämpchen in der Regionsliste auf der Website ansehen und zu einer Region mit grünem Licht wechseln; ist es weiter langsam, die Region passend zum Netzbetreiber wechseln |
| Ein Client der Clash-Familie kann den Freigabelink nicht importieren | Clash Meta, Clash Verge, FlClash, Stash und Ähnliche können eine einzelne hysteria2://-Zeile nicht als Profil importieren | Auf „Clash-Abonnement“ klicken und die URL in die Abo-Liste des Clients einfügen; dem ursprünglichen Clash und Clash for Windows fehlt hysteria2 im Kern, nutzen Sie stattdessen einen Client mit mihomo-Kern |
| Der Freigabelink lässt sich nicht importieren oder verbindet nicht | Der Freigabelink nutzt ein erweitertes Format, das einige Clients nicht lesen können | Zu Hiddify wechseln |

## Muss ich nach Verlängerung, Tarifwechsel oder Passwortänderung neu importieren?

- **Verlängerung oder Tarifwechsel (Persönlich / Familie / Unternehmen)**: Nein. Die bestehende Konfiguration funktioniert weiter.
- **Passwortänderung**: Die alte Konfiguration funktioniert sofort nicht mehr; scannen Sie den QR-Code erneut. Haben Sie Ihr Smartphone verloren oder ist der Link in falsche Hände geraten, sperren Sie den Zugang genau so.
- **Konto abgelaufen**: Die Konfiguration liefert 401. Nach der Verlängerung brauchen Sie keine neue Konfiguration; einfach neu verbinden.
- **Vor September 2026 importiert**: Die Regel, die IPv6 ablehnt, fehlt; beim Ansehen chinesischer Videos aus dem Ausland erscheint deshalb ein Hinweis auf Urheberrechtsbeschränkungen. Löschen und neu importieren; siehe [03](03-ipv6-and-dns-leak.md).

## Wann Sie den Support kontaktieren

Nennen Sie dem Support drei Dinge: Name und Version des Clients, die Region und den genauen Fehlertext oder einen Screenshot.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=troubleshooting-04)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=troubleshooting-04) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – dauerhaft gültig

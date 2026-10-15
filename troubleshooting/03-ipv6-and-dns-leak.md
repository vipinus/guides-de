# 03 · Verbunden, aber die Videoseite meldet trotzdem Urheberrechtsbeschränkungen: IPv6 und DNS schlüpfen durch

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/overseas-video?utm_source=github&utm_content=troubleshooting-03

Schritt 1 aus [02 · Mit China verbunden, aber Videos laufen trotzdem nicht](02-still-blocked-after-connecting.md) haben Sie bestanden – die Ausgangs-IP wird als Festlandchina erkannt –, und trotzdem meldet die Seite „Kann aufgrund von Urheberrechtsbeschränkungen nicht abgespielt werden“. In neun von zehn Fällen gibt es auf dem Gerät noch einen Weg, der nicht über das VPN läuft: **IPv6** oder **DNS**. Eine Videoplattform entscheidet anhand der Adresse, die sie sieht, wo Sie sich befinden – und solange ein Weg nach außen leckt, sieht sie weiterhin das Ausland.

## Warum es zu Lecks kommt

- Moderne Geräte haben eine IPv4- und eine IPv6-Adresse, und Browser bevorzugen IPv6. Übernimmt das VPN nur IPv4, gehen IPv6-Anfragen direkt über Ihren Internetanschluss zu Hause hinaus.
- Das im Browser eingebaute „sichere DNS“, das „Private DNS“ unter Android oder ein anderes laufendes Mesh-Netzwerk-Tool (Tailscale und Ähnliche) übernehmen alle die Namensauflösung noch vor dem VPN.

„Verbunden“ heißt nur, dass der Tunnel steht. Es heißt nicht, dass der gesamte Verkehr durch den Tunnel geht.

## Prüfung in fünf Schritten

1. **IPv6 prüfen.** Suchen Sie nach dem Verbinden nach „test ipv6“ und öffnen Sie eine Testseite. Zeigt das IPv6-Feld eine Adresse in dem Land, in dem Sie sind → hier liegt das Problem, weiter mit Schritt 2. Zeigen beide Felder Festlandchina oder ist IPv6 nicht verfügbar → weiter mit Schritt 3.
2. **IPv6 abschalten oder zu einem Client wechseln, der IPv6 blockiert.** Windows: In den Eigenschaften des Netzwerkadapters das Häkchen bei „Internetprotokoll, Version 6“ entfernen. macOS: Netzwerkeinstellungen → TCP/IP → IPv6 auf „Nur Link-lokal“ stellen. Smartphone: WLAN ausschalten und einmal mit mobilen Daten testen; Festnetzanschlüsse haben meist IPv6, mobile Daten der Netzbetreiber oft nicht.
3. **DNS prüfen.** In Chrome Einstellungen → Datenschutz und Sicherheit → „Sicheres DNS verwenden“ ausschalten; unter Android „Privates DNS“ ausschalten; andere VPNs, Mesh-Netzwerk-Tools und Proxy-Erweiterungen beenden.
4. **App vollständig beenden und neu öffnen; bei der Webversion die Websitedaten löschen.** Die Plattformen speichern die vorherige Regionsprüfung zwischen.
5. **Zu einem anderen Einstiegspunkt wechseln und erneut versuchen.** Die Adresse eines bestimmten Ausgangs wurde von der Plattform womöglich gerade markiert.

## Wie LeoTun damit umgeht

Seit September 2026 lehnen alle drei Verbindungsarten von LeoTun (Hiddify, Cisco AnyConnect, OpenVPN) IPv6 direkt im Tunnel ab und übermitteln DNS-Einstellungen, die die Namensauflösung im Tunnel erzwingen – auf Ihrem Gerät müssen Sie nichts umstellen. **Hiddify-Konfigurationen, die vor September importiert wurden, enthalten diese Regel nicht. Löschen Sie sie und importieren Sie per QR-Code neu.**

Beim Router gibt es das Leck gar nicht erst: Das ganze LAN geht über den Router hinaus, IPv6 und DNS der Geräte gelangen nie nach außen.

## Fälle, in denen der Hinweis trotzdem erscheint

| Fall | Symptom | Lösung |
|---|---|---|
| Der Ausgang ist nicht Festlandchina | Die IP-Abfrage zeigt Hongkong / Taiwan / Japan | Zu einem Einstiegspunkt in China wechseln; Adressen aus Hongkong und Taiwan gelten für Tencent und iQIYI ebenfalls als Ausland |
| Eigene Routing-Regeln setzen die Video-Domains auf „direkt“ | Webseiten öffnen sich, Videos spielen nicht ab | Die chinesischen Domains über den Knoten leiten; Nutzer im Ausland sollten „China direkt“ nicht einschalten |
| Sie nutzen den Web-Proxy | Funktioniert im Browser, nicht in Apps | Für Videos braucht es einen Tunnel für das ganze Gerät; der Web-Proxy deckt nur den Browser ab |

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=troubleshooting-03)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=troubleshooting-03) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – dauerhaft gültig

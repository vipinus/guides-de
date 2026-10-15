# 01 · Cisco AnyConnect: Installieren, Verbinden und Aktualisieren auf allen Plattformen

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/anyconnect-china?utm_source=github&utm_content=client-01

AnyConnect ist der Unternehmens-VPN-Client von Cisco. Offiziell heißt er inzwischen **Cisco Secure Client**; die Bedienung ist dieselbe. Sie brauchen weder eine Zertifikatsdatei noch ein importiertes Profil: Adresse, Konto und Passwort eingeben, und Sie können verbinden. Ob er in China funktioniert und worauf Sie ausweichen, wenn er nicht verbindet, steht in [Aus China ausländische Dienste erreichen, Anleitung 02](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/02-anyconnect-in-china.md) (auf Chinesisch).

## Installieren

| Plattform | Was Sie installieren | Bezugsquelle |
|---|---|---|
| Windows 10 und neuer | Cisco Secure Client 5.x | [Die Cisco-Seite der Website](https://www.leotun.com/de/anyconnect?utm_source=github&utm_content=client-01) |
| Windows 7 / 8 | AnyConnect 4.9 (die letzte Version, die sie unterstützt; keine Updates mehr) | Wie oben |
| macOS | Cisco Secure Client 5.x | Wie oben |
| iOS | Cisco Secure Client | App Store; führt der Store ihn nicht, installieren Sie das quelloffene OpenConnect, das dasselbe Protokoll nutzt |
| Android | Cisco Secure Client | Google Play oder die APK auf der Seite der Website |
| Linux | Der Installer auf der Seite der Website oder openconnect aus den Paketquellen Ihrer Distribution | Wie oben |

Unter Windows gibt es außerdem das quelloffene OpenConnect-GUI; dasselbe Konto funktioniert auch damit.

## In vier Schritten verbinden

1. Öffnen Sie den Client und geben Sie die Serveradresse in das Adressfeld ein. LeoTun-Nutzer können auf der Website **auf die Flagge einer Region klicken**, um deren Adresse zu kopieren.
2. Geben Sie Ihr Konto (die E-Mail-Adresse, mit der Sie sich registriert haben) und Ihr Passwort ein.
3. Sobald „Connected“ (verbunden) erscheint, öffnen Sie eine Webseite, die Ihre IP anzeigt, und prüfen, ob der Ausgang in der gewählten Region liegt.
4. Für eine andere Region nehmen Sie eine andere Adresse. Der Client merkt sich die verwendeten Adressen, sodass Sie beim nächsten Mal aus der Dropdown-Liste wählen können.

## Aktualisieren

Vorher deinstallieren ist nicht nötig: Installieren Sie die neue Version über die alte, die gespeicherten Adressen bleiben erhalten. Auf dem Smartphone aktualisieren Sie über den App Store bzw. Google Play. Nach einem großen Betriebssystem-Upgrade aktualisieren Sie zuerst den Client und suchen erst dann nach Verbindungsproblemen.

## Häufige Meldungen

| Meldung | Bedeutung |
|---|---|
| Login failed | Konto oder Passwort falsch, oder das Konto ist abgelaufen |
| Untrusted server certificate | Höchstwahrscheinlich stimmt die Systemuhr nicht, oder das aktuelle Netz fängt verschlüsselte Verbindungen ab; ein anderes Netz versuchen |
| Connection attempt has failed | Diese Adresse ist vorübergehend nicht erreichbar; Region wechseln |

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=client-01)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-01) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

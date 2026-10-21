# 04 · OpenVPN: .ovpn-Profil herunterladen, importieren, verbinden – auch für Router, NAS und Linux

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/openvpn-setup?utm_source=github&utm_content=client-04

OpenVPN ist ein altbewährtes Open-Source-Protokoll; fast jedes Betriebssystem, jede Router-Firmware und jedes NAS bringt einen Client dafür mit. Die Profildateien von LeoTun enthalten bereits Ihr Konto, Ihr Passwort und das Schlüsselmaterial, sodass Sie direkt nach dem Import verbinden können. Für den Alltag auf Smartphone und Computer sind AnyConnect oder Hiddify bequemer; die Stärke von OpenVPN liegt bei **Geräten, die nur OpenVPN akzeptieren**: OpenWrt-Router, Synology-/QNAP-NAS, Linux-Server und ältere Geräte.

## Drei Schritte

1. Installieren Sie über die Tabelle auf [der OpenVPN-Seite der Website](https://www.leotun.com/de/openvpn?utm_source=github&utm_content=client-04) den Client für Ihr System (für jede Plattform gibt es das offizielle OpenVPN Connect; unter Windows geht auch OpenVPN GUI, unter macOS Tunnelblick).
2. Nach der Anmeldung **klicken Sie auf die Flagge einer Region**, um die .ovpn dieser Region herunterzuladen. Eine Datei pro Region.
3. Öffnen Sie die Datei im Client und verbinden Sie.

| Plattform | Hinweise |
|---|---|
| Windows / macOS / Android / iOS | Konto und Passwort sind im Profil enthalten; importieren und verbinden |
| Linux | System-VPN-Einstellungen → aus Datei importieren, beim ersten Verbinden E-Mail-Adresse und Passwort der Website eingeben; Kommandozeile `openvpn --config file`; für den Start beim Hochfahren nach `/etc/openvpn/client/` legen |
| OpenWrt-Router | luci-app-openvpn installieren, .ovpn hochladen und aktivieren; bei vorinstallierter Firmware unserer Website nicht nötig |
| Synology-NAS | Systemsteuerung → Netzwerk → Netzwerkschnittstelle → Erstellen → VPN-Profil → OpenVPN (die .ovpn importieren); soll der ausgehende Verkehr des NAS über die Leitung laufen, „Standard-Gateway im Remote-Netzwerk verwenden“ (Use default gateway on remote network) anhaken |
| QNAP-NAS | QVPN → VPN-Client → Hinzufügen → OpenVPN, importieren |

## Nutzer in China: chinesische Websites direkt erreichen

Nach dem Verbinden nehmen auch Aufrufe chinesischer Websites einen Umweg. Die Website bietet ein „Tool für direktes China-Routing“: per Doppelklick starten, dann gehen chinesische IPs direkt und alles andere über die Leitung. Es funktioniert mit Cisco und OpenVPN. Nutzer außerhalb Chinas sollten es nicht verwenden.

## Wenn es nicht verbindet: in dieser Reihenfolge prüfen

| Stichwort im Log / Symptom | Ursache | Was tun |
|---|---|---|
| AUTH_FAILED | Konto oder Passwort falsch, oder abgelaufen | Auf der Website anmelden und das Ablaufdatum prüfen; nach einer Passwortänderung das Profil neu herunterladen |
| Zuerst UDP-Timeout, dann Verbindung über TCP | Das aktuelle Netz schränkt UDP ein, es wurde automatisch auf TCP umgeschaltet | Nutzbar, aber langsamer; ist es zu langsam, Netz wechseln oder AnyConnect nutzen |
| UDP und TCP melden beide TLS handshake failed / key negotiation failed | Der Netzweg zum Server ist unterbrochen | Region oder Netz wechseln |
| Fehler beim Import | Client zu alt (vor OpenVPN 2.5) | Client aktualisieren |
| Bricht während der Verbindung plötzlich ab | Konto abgelaufen, der Server hat getrennt | Verlängern und neu verbinden; das Profil muss nicht ersetzt werden |

## UDP oder TCP

Beides ist enthalten, Sie müssen nicht wählen. UDP steht im Profil an erster Stelle, der Client versucht also zuerst UDP; ist UDP eingeschränkt oder verbindet nicht, wechselt er nach einigen Sekunden automatisch zu TCP. UDP hat geringere Latenz und ist schneller; TCP ist nur die Rückfalllösung und über Landesgrenzen hinweg spürbar langsamer. In Netzen, die UDP dauerhaft einschränken (manche Campus- und Firmennetze), empfehlen wir direkt AnyConnect.

> Profile, die vor dem 15. September 2026 heruntergeladen wurden, enthalten nur UDP; laden Sie sie neu herunter, wenn Sie den automatischen Wechsel möchten.

## Sicherheit

Die Profildatei enthält Ihr Konto und Ihr Passwort und ist damit so viel wert wie das Konto selbst – geben Sie sie nicht weiter. Ist sie in falsche Hände geraten, ändern Sie Ihr Passwort auf der Website; die alte Datei funktioniert dann sofort nicht mehr. Auch der Handshake selbst ist verschlüsselt: Ohne den Schlüssel im Profil lässt sich nicht einmal ein Handshake beginnen, und für Scanner ist der Server unsichtbar.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=client-04)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-04) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

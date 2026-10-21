# 06 · Chinesische Videoseiten im Ausland per Router freischalten

## Warum ein Router statt eines Clients auf jedem Gerät

- Auf Fernsehern, TV-Boxen, Beamern und Spielkonsolen lässt sich kein Client installieren – da bleibt nur der Router.
- Bei vielen Personen im Haushalt ist es unrealistisch, jedes Gerät jeder Person einzurichten; richten Sie einmal den Router ein, wirkt es, sobald sich ein Gerät mit dem WLAN verbindet.
- Das Split-Routing erledigt der Router, sodass lokale Websites und Geräte weiterhin direkt verbinden; nur die Domains chinesischer Videoseiten laufen über die Leitung nach China, und das Tempo leidet nicht.

## Was Sie brauchen

| Was | Hinweise |
|---|---|
| Einen unterstützten Router | Ein vorinstallierter funktioniert sofort; wenn Sie selbst flashen, siehe [Firmware flashen](02-flash-firmware-yourself.md) |
| Ein Konto | Die Tarife Persönlich, Familie und Unternehmen unterstützen alle die Router-Funktion. Fordern Sie nach der Registrierung zuerst den Gratistest an, um den ganzen Ablauf zu prüfen: Ein neues Konto steht im Tarif Persönlich, mit 4 Stunden Test |
| Einen vorgeschalteten Anschluss | Das Modem oder der Router, den Sie zu Hause schon haben; der neue Router kommt dahinter |

## In fünf Schritten erledigt

1. Verbinden Sie den WAN-Port des neuen Routers mit dem vorhandenen Netz, stecken Sie den Strom ein und warten Sie eine Minute.
2. Verbinden Sie Ihr Smartphone mit dem WLAN des neuen Routers, öffnen Sie die Verwaltungsadresse `http://192.168.11.1` und melden Sie sich mit Ihrem Konto an.
3. Wählen Sie als Modus **Split-Routing**. Die Domains chinesischer Videoseiten stehen auf der Liste und laufen automatisch über die Leitung nach China.
4. Stellen Sie Fernseher und TV-Box auf dieses WLAN um oder verbinden Sie sie per Kabel mit einem LAN-Port des neuen Routers.
5. Öffnen Sie iQIYI, Tencent Video oder Yangshipin (CCTV); läuft die Wiedergabe normal, sind Sie fertig.

## Die Liste ist öffentlich

Die Videodomains auf der Split-Routing-Liste werden in einem öffentlichen Repository gepflegt: <https://github.com/vipinus/openwrt-2026-video-domains>. Spielt eine Plattform nicht ab, können Sie nachsehen, ob ihre Domain auf der Liste steht, und sie andernfalls einreichen.

## Bildqualität und Bandbreite

1080p braucht stabile 5 Mbit/s, 4K 25 Mbit/s oder mehr. Ruckelt die Wiedergabe abends zur Spitzenzeit, wählen Sie eine Region mit grüner Ampel; ruckelt es dann immer noch, liegt es meist am lokalen Breitband. Als Einstiegsregion wählen Sie eine, die nah bei Ihnen liegt und eine gute Anbindung nach Festlandchina hat; probieren Sie ein, zwei aus und urteilen Sie danach, ob die Wiedergabe ruckelt.

## Häufige Fragen

- **Auf dem Smartphone läuft es, auf dem Fernseher nicht**: Der Fernseher hängt noch am alten WLAN, oder die App auf dem Fernseher ist die internationale Ausgabe.
- **Manche Plattformen laufen, andere nicht**: Die Domain dieser Plattform steht nicht auf der Split-Routing-Liste. Schalten Sie zur Prüfung vorübergehend auf „Global“ und reichen Sie die Domain dann im Listen-Repository ein.
- **Auf einem alten Router wird das ganze Heimnetz langsam**: Der Prozessor kommt mit dem verschlüsselten Datenverkehr nicht hinterher; wechseln Sie zu einem leistungsstärkeren Modell, siehe [Erste Schritte mit dem vorinstallierten Router](01-plug-and-play-router.md).

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=router-06)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=router-06) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

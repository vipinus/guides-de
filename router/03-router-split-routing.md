# 03 · Was Split-Routing am Router ist

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/router-firmware?utm_source=github&utm_content=router-03

## In einem Satz

Richten Sie das VPN auf dem Router ein, dann läuft jedes Gerät im Haushalt automatisch darüber, sobald es mit dem WLAN verbunden ist. Auch Geräte, auf denen sich kein Client installieren lässt – TV-Boxen, Spielkonsolen, Drucker –, können es nutzen.

## Welches Problem Split-Routing löst

Läuft der gesamte Datenverkehr über das VPN, haben Sie zwei Probleme: Lokale Websites werden langsam (sie nehmen einen Umweg), und lokale Geräte sind nicht mehr erreichbar (Drucker, NAS und die Verwaltungsseite des Routers liegen im lokalen Netz, der Datenverkehr wird aber nach draußen geschickt).

Beim Split-Routing bekommt der Router eine Liste: Domains auf der Liste laufen über das VPN, alles andere verbindet direkt. In welche Richtung, hängt davon ab, wo Sie sind und welche Seite Sie erreichen wollen, und ergibt sich automatisch aus der gewählten Region:

- **Im Ausland, Region China gewählt (Zugriff auf China)**: Chinesische Websites und Apps laufen über das VPN, alles andere verbindet direkt.
- **In China, ausländische Region gewählt (Zugriff auf Auslandsdienste)**: Standardmäßig laufen nur gesperrte Websites und Dienste über das VPN; chinesische Websites und ausländische Websites, die sich in China ohnehin öffnen (Websites ausländischer Firmen, Downloads von Apple und Microsoft, Spieleplattformen und Ähnliches), verbinden direkt ohne Umweg – so schnell wie ohne Router.

## Drei Modi

| Modus | Wohin der Datenverkehr geht | Wann Sie ihn nutzen |
|---|---|---|
| Global | Alles läuft über das VPN | Vorübergehend, zur Fehlersuche |
| Split-Routing | Domains auf der Liste über das VPN, der Rest direkt | Im Alltag |
| Direkt | Nichts läuft über das VPN | Wenn Sie es eine Weile nicht brauchen |

## Aus China auf Auslandsdienste zugreifen: nur gesperrte Websites

Seit dem 14. Oktober 2026 schickt das Split-Routing in Richtung Auslandsdienste aus China standardmäßig nur gesperrte Websites und Dienste über das VPN. Grundlage ist eine Liste gesperrter Websites, die sich täglich automatisch aktualisiert, dazu Dienste wie Telegram, die sich ohne Namensauflösung mit festen Adressen verbinden. Websites, die sich in China ohnehin öffnen, ob chinesisch oder ausländisch, verbinden direkt.

Der Schalter befindet sich in der Verwaltungsoberfläche des Routers unter „VPN settings“ (VPN-Einstellungen) im Abschnitt für intelligentes Split-Routing: das Kontrollkästchen „Blocked sites only“ (nur gesperrte Websites), standardmäßig angehakt. Entfernen Sie das Häkchen, gilt wieder das frühere Verhalten: chinesische Websites direkt, alles andere über das VPN.

Bei Firmware, die vor Oktober 2026 geflasht wurde, erscheint dieses Kontrollkästchen noch nicht; die neue Voreinstellung gilt für diese Router über automatische Updates aber bereits. Möchten Sie sie ändern, wenden Sie sich an den Kundenservice, der das aus der Ferne erledigen kann.

Die Richtung für den Zugriff auf China aus dem Ausland bleibt unverändert.

## Fallstricke

- **Eine Website öffnet sich mit Split-Routing nicht**: Prüfen Sie zuerst, ob sie auf der Liste steht. Websites, die nicht auf der Liste stehen, verbinden direkt – ließ sich die Website ohnehin nicht öffnen, hilft Split-Routing nicht. Schalten Sie zur Prüfung vorübergehend auf „Global“.
- **In China öffnet sich eine ausländische Website nicht**: Entfernen Sie im Abschnitt für intelligentes Split-Routing das Häkchen bei „Blocked sites only“ (oder schalten Sie vorübergehend auf „Global“) und versuchen Sie es erneut. Öffnet sie sich dann, ist die Website gesperrt, steht aber noch nicht auf der Liste; schicken Sie die Adresse an den Kundenservice.
- **Gesperrte Websites öffnen sich nicht, alles andere funktioniert**: Auf dem Gerät ist höchstwahrscheinlich verschlüsseltes DNS eingeschaltet (unter Android „Privates DNS“, im Browser „Sicheres DNS“), sodass der Router nicht sieht, welche Website abgefragt wird. Schalten Sie diese Einstellung aus.
- **Drucker oder NAS sind nach dem Verbinden nicht erreichbar**: Dann werden auch lokale Netzadressen nach draußen geschickt. Prüfen Sie, ob die Split-Routing-Regeln private Bereiche wie 192.168.x.x ausnehmen.
- **Die Leistung des Routers** setzt die Obergrenze. Der Prozessor eines alten Routers ist mit verschlüsseltem Datenverkehr voll ausgelastet, was sich darin zeigt, dass der ganze Haushalt langsamer wird. Dann liegt es nicht an der VPN-Leitung.

## Ein Konto, ein Router

Die meisten Dienste binden den Router (über die MAC-Adresse) an das Konto. Ein Konto ist an einen Router gebunden, und beim Routerwechsel heben Sie zuerst die Bindung auf. So bleibt das Konto allein Ihres.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=router-03)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=router-03) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

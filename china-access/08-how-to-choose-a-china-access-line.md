# 08 · Eine Leitung nach China auswählen: woher die chinesische IP kommt und woran kostenlose Angebote scheitern

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/choose-china-vpn?utm_source=github&utm_content=china-access-08

Eine Leitung nach China tut genau eines: Sie sorgt dafür, dass die Anfragen, die Sie aus dem Ausland schicken, bei Tencent Video, NetEase Cloud Music oder Ihrer Onlinebank mit einer IP aus **Festlandchina** ankommen. Achten Sie deshalb zuerst auf zwei Punkte: ob der Ausgang wirklich eine IP aus Festlandchina ist und ob irgendein Datenverkehr auf dem Gerät daran vorbeiläuft. Tempo, Preis und Client kommen erst danach.

## Woher die chinesische IP kommt

Der Anbieter muss eigene Server in Festlandchina haben. Cloud-Anbieter in China verlangen für jede Maschine eine Registrierung mit Klarnamen und rechnen Bandbreite nach Verbrauch ab, die Kosten liegen also weit über denen ausländischer Maschinen. Deshalb sind fast alle seriösen Dienste mit Zugang nach China kostenpflichtig, und die Zahl der Ausgänge in China ist begrenzt.

Ein verbreiteter Ersatz: Maschinen in Hongkong, Taiwan oder Japan werden als „Zugang nach China“ ausgegeben. Diese Adressen reichen für einige Bereiche von Bilibili, die für Hongkong, Macau und Taiwan freigegeben sind, aber Tencent Video, iQIYI und Youku zeigen weiterhin Urheberrechtsbeschränkungen, und auch Onlinebanking und 12306 behandeln Sie als Nutzer im Ausland. **So erkennen Sie es: Schlagen Sie nach dem Verbinden nach, wo die IP registriert ist; zählt nur, wenn dort „China · (Provinz)“ steht.**

## Fünf Punkte, die Sie vor der Wahl prüfen

| Punkt | So prüfen Sie es | So sieht ein Durchfallen aus |
|---|---|---|
| Ausgangsregion | Nach dem Verbinden nachschlagen, wo die IP registriert ist | Adressen in Hongkong, Taiwan, Japan oder Korea |
| IPv6 und DNS | Nach „test ipv6“ suchen und eine Testseite öffnen | Das IPv6-Feld zeigt das Land, in dem Sie sind → Videoseiten sperren Sie weiterhin, siehe [Fehlerbehebung 03](../troubleshooting/03-ipv6-and-dns-leak.md) |
| Client | Ob es ein Standardprotokoll ist (AnyConnect, OpenVPN, Hiddify) | Es gibt nur eine einzige proprietäre App – wird sie entfernt, haben Sie nichts mehr |
| Bandbreite | Zwischen 20 und 23 Uhr Pekinger Zeit 1080p abspielen | Tagsüber schnell, abends dreht sich das Ladesymbol |
| Mehrere Geräte und Router | Wie viele Geräte pro Konto, und ob ein Router einen ganzen Haushalt anbinden kann | Jedes Gerät muss einzeln gekauft werden |

## Warum kostenlose Leitungen nach China ständig abbrechen

Das Problem ist nicht „kostenlos“, sondern die Kostenstruktur. Ausgangsbandbreite in Festlandchina wird nach Verbrauch bezahlt, und ein Gratisdienst kann nur eines von dreien tun: Tausende Nutzer auf eine Maschine quetschen, sodass zu Spitzenzeiten alle ruckeln; Datenvolumen und Zeit begrenzen, sodass mittendrin eine Zahlungsaufforderung aufspringt; oder auf anderem Weg Geld verdienen – durch eingeschleuste Werbung, das Sammeln des Browserverlaufs oder indem Ihr Gerät als Ausgang für andere dient.

Kostenlose Browser-Erweiterungen „für China“ haben einen weiteren blinden Fleck: Sie leiten nur die Webanfragen des Browsers weiter, während Videoplayer, Apps und System-DNS nicht hindurchgehen. Deshalb ist „Die Webseite öffnet sich, aber das Video läuft nicht“ so häufig.

Um ab und zu etwas nachzuschlagen, reicht kostenlos. Für Serien, Musik und Onlinebanking ist die Zeit, die eine stabile kostenpflichtige Leitung spart, weit mehr wert als die Abogebühr. Fordern Sie zuerst den 4-stündigen Test an, probieren Sie ihn einmal zur abendlichen Spitzenzeit und entscheiden Sie dann.

## Wie sich Auslandsstudierende, Reisende und Familien jeweils einrichten

- **Auslandsstudierende**: Wohnheimnetze haben meist IPv6; nutzen Sie also einen Client, der IPv6 blockiert. Für Onlinebanking, CHSI und 12306 verbinden Sie sich nur bei Bedarf mit der Leitung nach China und trennen danach wieder, um die Risikokontrolle der Konten seltener auszulösen.
- **Kurze Reisen**: Installieren Sie einen Cisco- oder Hiddify-Client auf dem Smartphone und importieren Sie per QR-Code; nach der Landung läuft es sofort.
- **Eine ganze Familie, die dauerhaft im Ausland lebt**: Bringen Sie einen Router mit unserer Firmware an die Leitung, dann brauchen Fernseher, Set-Top-Box und die Smartphones älterer Angehöriger keine Einrichtung; siehe [Chinesische Videoseiten per Router freischalten](../router/06-unlock-chinese-video-with-router.md).

## Selbsttest in 5 Minuten

1. Verbinden Sie sich mit der Leitung nach China; die IP-Abfrage zeigt eine Provinz in Festlandchina.
2. Die IPv6-Testseite zeigt IPv6 als nicht verfügbar oder ebenfalls als Adresse in Festlandchina.
3. Öffnen Sie bei Tencent Video eine beliebige Serie, die es nur in China gibt; sie läuft.
4. Spielen Sie nach 20 Uhr Pekinger Zeit noch einmal 1080p ab; es puffert nicht ständig.
5. Wechseln Sie zu einem anderen Ausgang in China und wiederholen Sie die ersten drei Schritte.

## Häufige Fragen

**Gibt es einen Unterschied zwischen einem VPN nach China und einem „Beschleuniger“ für China?** Keinen grundsätzlichen. Ein „Beschleuniger“ ist meist eine App eines Spiele- oder Videoanbieters, die nur bestimmte Anwendungen abdeckt; ein VPN ist ein Tunnel für das ganze Gerät.

**Kann ich Tencent Video mit einem Knoten in Hongkong schauen?** Nein, die Lizenz gilt nur für Festlandchina.

**Wie viele Geräte pro Konto?** Bei LeoTun richten sich gleichzeitige Verbindungen nach dem Tarif: Persönlich 2 Geräte, Familie 4 Geräte, Unternehmen 8 Geräte. Ein Router zählt als ein Gerät, die Geräte dahinter werden nicht einzeln gezählt. Sind mehr Geräte gleichzeitig online, als Ihr Tarif erlaubt, können Sie den Kontotyp vorübergehend hochstufen (die Restlaufzeit wird wertgleich nach Preis umgerechnet) und danach wieder zurückwechseln.

**Kann ich Clash nutzen?** Ja. LeoTun stellt ein sing-box-Abonnement, ein Clash-Abonnement und einen hysteria2-Freigabelink bereit. Mit Clash Meta, Clash Verge, FlClash, Stash und Ähnlichen klicken Sie auf die Schaltfläche „Clash-Abonnement“ und fügen die URL in die Abo-Liste des Clients ein; ein Abo-Konverter ist nicht nötig, und den Freigabelink nutzen Sie nicht. Das ursprüngliche Clash und Clash for Windows funktionieren nicht, weil ihrem Kern hysteria2 fehlt. Dieses Abo schickt standardmäßig alles außer Ihrem lokalen Netz über den Knoten, für chinesische Videos müssen Sie also nichts ändern; legen Sie eigene Regeln an, stellen Sie chinesische Domains nicht auf „direkt“.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=china-access-08)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=china-access-08) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

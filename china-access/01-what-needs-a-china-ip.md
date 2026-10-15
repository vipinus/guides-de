# 01 · Welche Dienste eine chinesische IP brauchen

Es gibt nur einen Maßstab: Sieht der Dienst, dass Ihre Quell-IP nicht in Festlandchina liegt, weist er Sie ab oder bietet nur einen eingeschränkten Dienst. Die Tabelle unten ist danach geordnet, wie streng gesperrt wird.

| Kategorie | Beispiele | Was ohne chinesische IP passiert | Was außer der IP geprüft wird |
|---|---|---|---|
| Video | iQIYI, Tencent Video, Youku, Mango TV, manche Anime-Serien auf Bilibili | Hinweis, dass es nur in Festlandchina verfügbar ist, oder nur Gratisinhalte | Region des App Stores, Registrierungsort des Kontos |
| Musik | NetEase Cloud Music, QQ Music, Kugou | Sehr viele Songs sind ausgegraut und lassen sich nicht abspielen | Nichts |
| Behördendienste | Die nationale Plattform für Behördendienste, Behördenportale der Provinzen, Steuer, Sozialversicherung, Wohnungsbaufonds | Die Seite öffnet sich nicht, oder der Bestätigungscode kommt nie an | Telefonnummer, Gesichtserkennung |
| Bildung | CHSI, die Website für akademische Abschlüsse, Verwaltungssysteme der Hochschulen | Öffnet sich nicht oder extrem langsam | Nichts |
| Reisen | 12306, Websites von Fluggesellschaften | Öffnet sich nicht, Zahlung schlägt fehl | Telefonnummer, Zahlung |
| Finanzen | Onlinebanking, Banking-Apps, Alipay, WeChat Pay | Anmeldung wird von der Risikokontrolle gestoppt, Überweisungen schlagen fehl | SIM-Karte, Geräte-Fingerabdruck, Gesicht |
| Spiele | PC- und Handyspiele auf chinesischen Servern | Anmeldung möglich, aber hohe Latenz und Verbindungsabbrüche | Klarnamen-Verifizierung |
| Alltag | Meituan, Ele.me, DiDi, manche Taobao-Funktionen | Standortfehler, Bestellungen schlagen fehl | Standort, Telefonnummer |
| Livestreaming | Douyin, Kuaishou, Douyu | In manchen Regionen nicht abrufbar | Nichts |

## Ein wichtiger Unterschied

**„Eine chinesische IP brauchen“ und „eine chinesische Telefonnummer brauchen“ sind zwei verschiedene Dinge.** Video und Musik prüfen nur die IP, eine andere IP genügt. Behördendienste, Banking und Ticketbuchung verlangen außer der IP auch, dass Sie einen SMS-Bestätigungscode empfangen und die Gesichtserkennung bestehen. Die IP löst die Frage „Öffnet es sich?“; die Verifizierung danach hängt von Ihrer eigenen chinesischen Telefonnummer und Ihren Ausweisdokumenten ab.

## Wie Sie das IP-Problem lösen

Schicken Sie den Datenverkehr zuerst an einen Server in Festlandchina, der dann das Ziel aufruft. Dafür gibt es drei Wege: einen Client, den Web-Proxy oder einen Router. Wie Sie wählen, steht in [Welche Verbindungsart zu welcher Situation passt](../network/02-choose-your-connection-method.md) im Bereich Netzwerk.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=china-access-01)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=china-access-01) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – dauerhaft gültig

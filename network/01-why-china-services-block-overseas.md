# 01 · Wie der Zugriff auf China aus dem Ausland funktioniert

## Was Sie sehen

Sie sind im Ausland, öffnen iQIYI, Bilibili oder NetEase Cloud Music und lesen „Dieser Inhalt ist nur in Festlandchina verfügbar“; Onlinebanking und 12306 öffnen sich gar nicht, oder der Bestätigungscode kommt nie an.

## Es gibt nur eine Ursache: wo Ihre IP registriert ist

Geht Ihr Gerät online, weist ihm Ihr Netzbetreiber eine öffentliche IP-Adresse zu. Für diese Adressen gibt es ein weltweites Verzeichnis, aus dem hervorgeht, zu welchem Land und welchem Netzbetreiber jede gehört. Chinesische Video- und Musikplattformen kaufen Rechte nur für **Festlandchina** und dürfen außerhalb davon rechtlich nicht streamen – sie lehnen also ab, sobald sie eine ausländische IP sehen.

Banken und Ticketportale folgen einer anderen Logik. Bei ihnen geht es nicht um Urheberrecht, sondern um Risikokontrolle: Eine Anmeldung von einer ausländischen IP gilt als hohes Risiko und wird direkt blockiert.

## Der Lösungsansatz

Sorgen Sie dafür, dass der Server eine IP aus Festlandchina sieht. Dazu schicken Sie Ihren Datenverkehr zuerst an einen Server in Festlandchina, der die Zielseite dann in Ihrem Auftrag aufruft. Die Zielseite sieht die IP dieses Servers und lässt sie durch.

Genau das leistet eine „Leitung nach China“: Sie schickt Ihren Datenverkehr über eine IP aus Festlandchina hinaus.

## Drei verbreitete Irrtümer

- **Ein anderer DNS hilft nicht.** DNS übersetzt nur Domainnamen in Adressen; die Zielseite prüft Ihre Quell-IP, nicht den DNS, den Sie nutzen.
- **Einige Plattformen prüfen auch die Systemregion.** Außer der IP prüfen manche Plattformen auch die Gerätesprache und die Region des App Stores; stellen Sie in diesem Fall auch die Systemregion um.
- **Das Tempo hängt von der Qualität der Leitung zwischen den beiden Punkten ab.** Die grenzüberschreitende Verbindung vom Ausland nach Festlandchina ist der Engpass; einen Einstiegspunkt zu wählen, der nah bei Ihnen liegt und eine optimierte Leitung nach Festlandchina hat, ist deshalb wichtiger als die Ausstattung des Servers selbst.

## Weiterlesen

- [Welche Verbindungsart zu welcher Situation passt](02-choose-your-connection-method.md)
- [Checkliste bei keiner Verbindung, Langsamkeit und Abbrüchen](../troubleshooting/01-cannot-connect-slow-drops.md)

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=network-01)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=network-01) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; für jeden eingeladenen Freund, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein Angebot ohne Enddatum

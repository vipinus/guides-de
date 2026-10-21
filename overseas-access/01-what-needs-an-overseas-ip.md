# 01 · Welche Dienste eine ausländische IP brauchen und wie die Leitung funktioniert

Der Maßstab ist das Spiegelbild des Zugriffs auf China aus dem Ausland: Sieht der Dienst, dass Ihre Quell-IP in Festlandchina liegt, oder erreichen Sie seine Server überhaupt nicht, öffnet er sich nicht, läuft eingeschränkt oder extrem langsam. Die Tabelle unten ist nach Zweck geordnet.

| Kategorie | Beispiele | Was ohne Leitung passiert | Was Sie außer einer IP brauchen |
|---|---|---|---|
| Arbeit | Google Workspace, Slack, Zoom, Teams, Notion | Öffnet sich nicht oder bricht ständig ab | Ein Firmenkonto |
| Entwicklung | GitHub, npm, Docker Hub, PyPI-Quellen außer Spiegeln, Stack Overflow | So langsam, dass es in einen Timeout läuft | Nichts |
| KI | ChatGPT, Claude, Gemini | Öffnet sich nicht | Registrierungsland des Kontos, eine Telefonnummer |
| Forschung | Google Scholar, Literaturdatenbanken, Uni-E-Mail | Öffnet sich nicht oder extrem langsam | Ein Hochschulkonto |
| Gaming | Steam in ausländischen Regionen, PSN, Switch eShop, ausländische Server | Store öffnet sich nicht, hohe Latenz | Ein Konto für die Server dieser Region |
| Video und Musik | YouTube, Netflix, Disney+, Spotify | Öffnet sich nicht | Ein bezahltes Konto, dessen Region zur IP passen muss |
| Soziale Netzwerke | X, Instagram, Telegram, Discord, WhatsApp | Öffnet sich nicht | Eine Telefonnummer |

## Ein wichtiger Unterschied

**„Eine ausländische IP brauchen“ und „ein ausländisches Konto brauchen“ sind zwei verschiedene Dinge.** Bei GitHub und YouTube genügt eine andere IP; Netflix braucht ein bezahltes Konto mit passender Region; für die Registrierung bei ChatGPT brauchen Sie eine ausländische Telefonnummer, die einen Bestätigungscode empfangen kann. Die Leitung löst die Frage „Lässt es sich öffnen?“; um das Konto kümmern Sie sich selbst.

## Wie die Leitung funktioniert

Ihr Datenverkehr wird zuerst verschlüsselt und an einen Server im Ausland geschickt, der dann das Ziel aufruft. Das Ziel sieht die IP dieses Servers. Es gibt drei Wege: einen Client, den Web-Proxy und einen Router. Wie Sie wählen, steht in [Welche Verbindungsart zu welcher Situation passt](../network/02-choose-your-connection-method.md).

## Drei verbreitete Irrtümer

- **Ein anderer DNS hilft nicht.** Dass keine Verbindung zustande kommt, ist ein Problem des Weges, nicht der Namensauflösung.
- **Das Tempo hängt von der Leitung zwischen den beiden Punkten ab.** Aus China heraus sind die grenzüberschreitende Verbindung und der Auslandsanschluss Ihres Netzbetreibers der Engpass, deshalb ist die Wahl der Region wichtiger als die Ausstattung des Servers; siehe [03](03-which-region-is-fastest.md).
- **Wenn Sie chinesische Apps nutzen, muss nicht alles über die Leitung laufen.** Schalten Sie Split-Routing ein: Standardmäßig laufen nur gesperrte Websites über die Leitung, während chinesische Websites und ausländische Websites, die sich in China ohnehin öffnen, direkt verbinden – beide ohne Umweg; siehe [Split-Routing am Router](../router/03-router-split-routing.md).

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=overseas-access-01)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=overseas-access-01) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – dauerhaft gültig

# 02 · Chinesische Videos im Ausland sehen

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/overseas-video?utm_source=github&utm_content=china-access-02

## Warum Sie nicht schauen können

Die Plattformen kaufen die Rechte nur für Festlandchina, und ausländische IPs werden pauschal gesperrt. Das ist kein technischer Fehler; die einzige Lösung ist eine andere IP.

## Unterschiede zwischen den Plattformen

| Plattform | Webversion | App | Hinweise |
|---|---|---|---|
| iQIYI | IP wechseln genügt | IP wechseln genügt | Die Auslandsversion iQIYI ist eine andere App mit weniger Inhalten; installieren Sie nicht die falsche |
| Tencent Video | IP wechseln genügt | IP wechseln genügt | Dasselbe gilt für die Auslandsversion WeTV |
| Youku | IP wechseln genügt | IP wechseln genügt | |
| Mango TV | IP wechseln genügt | IP wechseln genügt | |
| Bilibili | Die meisten Inhalte lassen sich ohnehin ansehen | Ebenso | Nur einige Anime-Serien und Dokumentationen sind regional beschränkt |
| Yangshipin / CCTV | IP wechseln genügt | Ebenso | Livesender reagieren am empfindlichsten auf die IP |

**Die Falle mit der Auslands-App**: Suchen Sie in einem ausländischen Store nach dem chinesischen Namen von iQIYI, landen Sie meist bei der internationalen Version von iQIYI, deren Angebot völlig anders ist. Für das chinesische Angebot müssen Sie die chinesische Version der App installieren; auf dem iPhone brauchen Sie dafür eine Apple-ID mit Region China, auf Android können Sie die APK direkt installieren.

## Verbunden, aber trotzdem eine Urheberrechtsmeldung

Liegt die Ausgangs-IP schon in Festlandchina und die Seite zeigt trotzdem eine Urheberrechtsbeschränkung, umgehen in neun von zehn Fällen **IPv6 oder das lokale DNS** des Geräts die Leitung. Seit 2026-09 blockieren die drei Verbindungsarten von LeoTun für das ganze Gerät IPv6 auf der Leitungsseite; Hiddify-Konfigurationen, die vor September importiert wurden, müssen Sie löschen und per QR-Code neu importieren. Die Schritte zur Fehlersuche stehen in [IPv6 und DNS schlüpfen durch](../troubleshooting/03-ipv6-and-dns-leak.md).

## Auf dem Fernseher schauen

Auf Fernsehern und Set-Top-Boxen lässt sich kein Client installieren, es gibt also zwei Wege:

1. **Die Router-Lösung**: Richten Sie auf dem Router die Leitung nach China ein und schalten Sie Split-Routing ein; sobald der Fernseher mit diesem WLAN verbunden ist, kann er abspielen. Der ganze Haushalt profitiert; siehe [Für ältere Familienmitglieder und den Fernseher](../router/04-family-tv-and-router.md).
2. **Bildschirmübertragung**: Schalten Sie auf dem Smartphone die Leitung nach China ein und übertragen Sie dann auf den Fernseher. Einfach, aber das Smartphone muss die ganze Zeit an bleiben.

## Bildqualität

1080p braucht stabile 5 Mbit/s oder mehr. Ruckelt es zur Abendspitze, wählen Sie eine Region mit grüner Ampel oder wechseln die Verbindungsart; ruckelt es dann immer noch, liegt es meist am lokalen Breitband. Ein Einstiegspunkt, der nah bei Ihnen liegt und eine optimierte Verbindung nach Festlandchina hat, bringt mehr als ein Plattformwechsel.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=china-access-02)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=china-access-02) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

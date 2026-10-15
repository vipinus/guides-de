# 01 · Erste Schritte mit dem vorinstallierten Router

## Drei Schritte nach dem Auspacken

1. **Strom und Netzwerkkabel anschließen**: Verbinden Sie den WAN-Port des Routers mit Ihrem vorhandenen Modem oder vorgeschalteten Router und warten Sie, bis die Kontrollleuchte ruhig leuchtet – etwa eine Minute.
2. **Mit dem WLAN verbinden**: Name und Passwort des Standard-WLANs stehen auf der beiliegenden Karte (ab Werk ist beides der Domainname der Website). Öffnen Sie nach dem Verbinden einen Browser und rufen Sie die Verwaltungsadresse `http://192.168.11.1` auf.
3. **Mit dem Konto anmelden**: Geben Sie auf der Verwaltungsseite E-Mail-Adresse und Passwort Ihres Kontos ein und speichern Sie (Konten in den Tarifen Persönlich, Familie und Unternehmen können alle einen Router nutzen). Ab dann läuft jedes Gerät, das mit diesem WLAN verbunden ist, automatisch über das VPN.

## Standardpasswörter ändern

Das werkseitige Verwaltungspasswort und das WLAN-Passwort sind öffentlich bekannt; ändern Sie sie also gleich nach der Anmeldung: Verwaltungsseite → „System“ → „Administration“ (Verwaltung); „Wireless“ → „Interfaces“ → „Wireless Security“ (WLAN → Schnittstellen → WLAN-Sicherheit).

## Split-Routing-Modus

Standard ist Split-Routing: Chinesische Domains auf der Liste laufen über das VPN, alles andere verbindet sich direkt. Dieser Modus passt am besten, wenn Sie im Ausland chinesische Videos schauen oder ältere Familienmitglieder den Fernseher nutzen. Sind Sie in China und wählen eine Auslandsregion, dreht sich die Richtung automatisch um: Standardmäßig laufen dann nur gesperrte Websites und Dienste über das VPN, während chinesische Websites und ausländische Websites, die sich in China ohnehin öffnen, direkt verbinden; siehe [03 · Was Split-Routing am Router ist](03-router-split-routing.md). Muss vorübergehend alles über das VPN laufen, schalten Sie auf „Global“ und danach wieder zurück.

## Häufige Fragen

- **Die Kontrollleuchte ist normal, aber verbundene Geräte haben kein Internet**: Prüfen Sie den Kontostatus auf der Verwaltungsseite; ein abgelaufenes Konto oder ein falsches Passwort wird dort angezeigt.
- **Sie wollen auf einen anderen Router wechseln**: Heben Sie zuerst auf der Website die Verknüpfung des alten auf; siehe [MAC-Bindung und Routerwechsel](05-mac-binding-and-replacing.md).

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=router-01)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=router-01) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

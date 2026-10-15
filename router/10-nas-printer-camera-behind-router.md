# 10 · Sind NAS, Drucker und Kameras hinter dem Router betroffen?

Kommt ein VPN-Router ins Haus, gilt die erste Sorge meist dem Rest: Funktionieren NAS, Drucker und Kameras noch, und schickt das NAS dann seinen gesamten Verkehr durch das VPN?

## Die kurze Antwort

Nein. Split-Routing ist standardmäßig an: **Verkehr zwischen den Geräten zu Hause und zu Diensten in China gelangt nie in den Tunnel. Nur die Websites, die das VPN brauchen, laufen darüber.**

## Drei Arten von Verkehr, drei Wege

| Verkehr | Weg | Beispiele |
|---|---|---|
| Zwischen Geräten zu Hause | Bleibt im lokalen Netz, berührt den Tunnel nie | Dateien aufs NAS kopieren, auf den Fernseher streamen, drucken |
| Zu Diensten in China | Direkt, über Ihren eigenen Anschluss | NAS synchronisiert mit einem chinesischen Cloud-Speicher, Kameras laden in eine chinesische Cloud hoch, inländische Downloads |
| Zu gesperrten Websites | Durch den Tunnel | YouTube, Suchmaschinen, KI-Tools |

Dateien aufs NAS zu Hause kopieren läuft also mit voller lokaler Geschwindigkeit, und Backups in einen chinesischen Cloud-Speicher nutzen die ganze Bandbreite Ihres Anschlusses, ohne das VPN zu berühren.

Sind Sie im Ausland und nutzen eine Leitung nach China, ist die Richtung umgekehrt: Die chinesischen Websites auf der Liste gehen durch den Tunnel, alles andere direkt. Siehe [03 · Was Split-Routing ist](03-router-split-routing.md).

## Drei typische Situationen

**Das NAS von außen erreichen (Dateien unterwegs, Foto-Backup vom Smartphone)**
Zwei Wege:
- Das private Netzwerk (Tailscale) nutzen: NAS und Smartphone mit demselben Konto anmelden und das NAS von überall über seinen Gerätenamen erreichen. Keine öffentliche IP, keine Portweiterleitung. Siehe [Privates Netzwerk vs. VPN](../network/03-private-network-vs-vpn.md).
- Weitermachen wie bisher (Fernzugriff des Herstellers, Portweiterleitung). Der Router blockiert das nicht.

**Downloads auf dem NAS**
Downloads aus chinesischen Quellen gehen direkt und sind nicht betroffen. Downloads von ausländischen Websites, die sich in China ohnehin problemlos öffnen (etwa Apple- und Microsoft-Downloads), gehen standardmäßig ebenfalls direkt; nur Downloads von gesperrten Websites laufen durch den Tunnel und mit dessen Tempo. Sollen Downloads den Tunnel gar nicht nutzen, schließen Sie das NAS an den vorgeschalteten Router oder das Modem an – dann umgeht es diesen Router komplett.

**Ein Dienstlaptop, der ins Firmen-VPN muss**
Verbinden Sie ihn mit dem WLAN des vorgeschalteten Routers oder des Modems, getrennt von diesem Router. Zwei übereinander gestapelte VPNs verhindern meist den Zugriff auf das Firmennetz.

## Wenn ein Gerät nicht mitspielt

- Auf dem Gerät ist „Privates DNS“ oder „Sicheres DNS“ eingeschaltet. Dann löst es Namen selbst auf, am Router vorbei, und das Split-Routing sieht es nicht. Schalten Sie diese Einstellung aus.
- Prüfen Sie, in welchem WLAN es hängt. Ist es im WLAN des Modems, ist es nie über diesen Router gelaufen.

## Häufige Fragen

**Belegt das NAS einen Geräteplatz meines Kontos?** Nein. Der Router belegt einen Platz, alles dahinter wird nicht einzeln gezählt.

**Geht mir das Datenvolumen aus, wenn der ganze Haushalt dranhängt?** Konten haben unbegrenztes Datenvolumen, und inländischer Verkehr gelangt ohnehin nicht in den Tunnel.

**Kann ich ein Gerät dauerhaft vom VPN ausnehmen?** Ja, verbinden Sie es mit dem vorgeschalteten Router oder dem Modem. Auf der Verwaltungsseite lässt sich auch der ganze Router auf den Modus „Direkt“ stellen, das gilt dann aber für alle gleichzeitig.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=router-10)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=router-10) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – dauerhaft gültig

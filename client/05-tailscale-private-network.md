# 05 · Privates Netzwerk (Tailscale): installieren, beim Steuerserver unserer Website anmelden, Ausgang wählen

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/tailscale-mesh?utm_source=github&utm_content=client-05

Der Bereich Privat nutzt Tailscale (ein Vernetzungswerkzeug auf Basis von WireGuard). LeoTun betreibt einen eigenen Steuerserver, und Sie melden sich mit **Ihrem Konto unserer Website** an – mit einem offiziellen Tailscale-Konto hat das nichts zu tun. Einmal angemeldet, bleiben Sie online; die Ausgangsregion lässt sich jederzeit im Menü ändern. Wie es sich von einem VPN unterscheidet und für wen es passt, steht in [Netzwerk-Grundlagen 03](../network/03-private-network-vs-vpn.md).

## Installieren

| Plattform | Bezugsquelle |
|---|---|
| Windows / macOS / Linux / Android | Downloadbereich auf [der Seite Privat unserer Website](https://www.leotun.com/de/mesh?utm_source=github&utm_content=client-05) (direkt von unserer Website, Sie müssen nicht zur offiziellen Seite) |
| iPhone / iPad | App Store; dafür ist eine Apple-ID außerhalb der Region China nötig (siehe [Client-Anleitungen 06](06-ios-app-store.md)) |

## Anmelden

1. **Melden Sie sich zuerst vom offiziellen Konto ab** (falls Sie je angemeldet waren): auf dem Smartphone Profilbild → Log Out (abmelden); am Computer `tailscale logout` ausführen. Solange Sie nicht vollständig abgemeldet sind, erscheint die Option für den nächsten Schritt nicht.
2. **Richten Sie die Anmeldung auf unsere Website**:
   - Smartphone: Auf dem abgemeldeten Bildschirm oben rechts auf „⋯“ tippen → Use custom server (eigenen Server verwenden; in manchen Versionen Use an alternate server), die auf der Seite Privat unserer Website angegebene Adresse eingeben und auf Log in (anmelden) tippen.
   - Windows / Linux: Den Befehl `tailscale up --login-server=…` von der Seite unserer Website kopieren und in PowerShell bzw. einem Terminal ausführen.
   - macOS: **Klicken Sie nicht auf Log in.** Im Tailscale-Fenster auf den Pfeil in der Kontozeile klicken → Account Settings… → Accounts → kleiner Pfeil neben „Add Account…“ → Add Account Using Alternate Server (Konto über alternativen Server hinzufügen), Adresse einfügen und auf Add Account… klicken.
3. Der Browser öffnet automatisch die Anmeldeseite unserer Website; bestätigen Sie mit Ihrem Konto unserer Website. Zurück im Client ist das Gerät bereits online.

## Ausgang wählen

- Smartphone: Menü → Exit Node (Ausgangsknoten), Region wählen; das gilt sofort.
- Computer: Symbol in Taskleiste bzw. Menüleiste → Untermenü Exit Node; oder `tailscale set --exit-node=<region-name>` (`tailscale exit-node list` zeigt, was verfügbar ist).
- Ohne Ausgang wählen Sie None (keiner); auf der Kommandozeile lassen Sie den Wert nach dem Gleichheitszeichen leer. Es kann immer nur ein Ausgang gleichzeitig genutzt werden.

## Ablauf und Geräteanzahl

- Die Anmeldung eines Geräts gilt so lange wie das Konto und endet wenige Minuten nach dessen Ablauf; nach der Verlängerung melden Sie sich einfach noch einmal an. Eine Neuinstallation ist nicht nötig.
- Wie viele Geräte gleichzeitig online sein dürfen, hängt vom Tarif ab (Persönlich 2, Familie 4, Unternehmen 8); das Kontingent teilen sich alle Verbindungsarten. Überschreiten Sie das Limit Ihres Tarifs, können Sie den Kontotyp vorübergehend hochstufen (die Restlaufzeit wird wertgleich nach Preis umgerechnet) und danach wieder zurückwechseln.

## Zwei Fälle, in denen eine andere Verbindungsart besser passt

- Auf demselben Gerät läuft ein weiteres VPN (ein AnyConnect der Firma, andere Mesh-Netzwerk-Software): Sie streiten sich um DNS und Routen. Daher kommen Urheberrechtshinweise bei chinesischen Videos und Firmen-Intranets, die sich nicht öffnen.
- In einem Campus- oder Firmennetz, das UDP einschränkt: WireGuard läuft über UDP und kann dann nur über Relays gehen, was sehr langsam ist; wechseln Sie zu AnyConnect.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=client-05)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-05) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

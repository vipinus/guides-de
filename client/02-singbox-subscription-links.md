# 02 · So importieren Sie einen Abo-Link (Hiddify, Clash, Shadowrocket)

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/singbox-subscription?utm_source=github&utm_content=client-02

Der „Abo-Link“, den Ihnen ein Proxy-Anbieter gibt, ist nichts weiter als eine HTTPS-Adresse, von der der Client eine vollständige Konfiguration herunterlädt: Server, Port und Zugangsdaten stecken alle darin, Sie müssen nichts von Hand eintippen. Die Hiddify-Seite von LeoTun gibt Ihnen dasselbe – und zwar direkt in drei Formaten, sodass Hiddify, Clash und Shadowrocket jeweils ihr eigenes bekommen und nichts umgewandelt werden muss.

## Die drei Schaltflächen im Popup

Melden Sie sich auf der Website an → Seite Hiddify → klicken Sie auf die Flagge einer Region. Ein QR-Code erscheint, darunter drei Schaltflächen. Die Schaltflächen sind **nach Abo-Typ** gruppiert, nicht nach Betriebssystem; Smartphone und Computer zeigen also dieselben:

| Clients, die auf der Schaltfläche stehen | Untertitel | Was ein Klick kopiert |
|---|---|---|
| Hiddify / sing-box / GUI.for.SingBox / Karing | sing-box-Abonnement | Auf dem Smartphone den Import-Link `sing-box://import-remote-profile?url=…`, der die App startet; am Computer die reine Konfigurations-URL `https://…` zum Einfügen. Die Konfiguration enthält bereits Routing-Regeln und eine Regel, die IPv6 abweist; Sie müssen sie also nicht in eine „Abo-Vorlage“ packen |
| Clash Meta / Clash Verge / FlClash / Stash / Mihomo Party / Clash Nyanpasu / ClashX Meta / OpenClash | Clash-Abonnement | Eine Abo-URL im Clash-Format (YAML) zum Einfügen in die Abo- bzw. Profilliste des Clients |
| NekoBox / Shadowrocket / v2rayN / v2rayNG / Streisand / V2Box / Loon / Egern / Husi / NekoRay / Pharos Pro / Bedlam / Furious / daed / Lumen KVN / Kitty Pro | Freigabelink | Eine einzelne Zeile `hysteria2://…`, die nur den Knoten enthält, ohne Routing-Regeln |

- Passen die Namen nicht in eine Zeile, laufen sie als Endlosband durch; das ist normal.
- **Ein Klick auf eine Schaltfläche stellt auch den QR-Code darüber auf diesen Typ um**, damit der passende Client ihn scannen kann. Beim Öffnen des Popups zeigt der QR-Code zunächst den Hiddify-/sing-box-Typ; andere Clients, die ihn direkt scannen, melden „Ungültiger QR-Code“. Klicken Sie also zuerst auf die Schaltfläche Ihres Clients und scannen oder fügen Sie dann ein.
- Das Popup „Alle Regionen importieren · automatisch wählen“ oben auf der Seite hat nur die ersten beiden Schaltflächen, ohne Freigabelink.

**Abo-Umwandlung**: Websites von Drittanbietern, die ein Format in ein anderes umwandeln. LeoTun gibt Ihnen alle drei Formate direkt, also ist **keine Umwandlung nötig**; einen Link mit Ihren Zugangsdaten an eine Umwandlungsseite zu geben, heißt, Ihr Konto einem Fremden zu überlassen – lassen Sie das.

## Hiddify / sing-box: die erste Schaltfläche

1. Installieren Sie Hiddify (Android: Downloadseite unserer Website oder Google Play; iOS: App Store; die Desktop-App deckt Windows / macOS / Linux ab). Der sing-box-Kern ist eingebaut.
2. Klicken Sie auf die Flagge einer Region, und der QR-Code erscheint.
3. Smartphone: Tippen Sie auf die erste Schaltfläche und wechseln Sie zu Hiddify, das anbietet, den Link aus der Zwischenablage hinzuzufügen; oder nutzen Sie „QR-Code scannen“ in Hiddify auf einem anderen Gerät. Computer: Klicken Sie auf dieselbe Schaltfläche, die eine https://-Adresse kopiert, dann in Hiddify „+“ → „Add from clipboard“ (aus der Zwischenablage hinzufügen) und speichern.
4. Tippen Sie auf Verbinden und erlauben Sie beim ersten Mal die VPN-Berechtigung. Für eine weitere Region klicken Sie auf eine andere Flagge; jede Region ist ein eigenes Profil.

## Clash: die zweite Schaltfläche

Für Clash Meta (mihomo), Clash Verge, FlClash, Stash und Ähnliche klicken Sie auf die Schaltfläche „Clash-Abonnement“ und fügen die kopierte URL in die Abo- bzw. Profilliste des Clients ein. Ein Abo-Konverter ist nicht nötig.

**Clash-Clients dürfen den Freigabelink nicht nutzen**: Sie können eine einzelne Zeile `hysteria2://` nicht als Profil importieren.

## Andere Clients: die dritte Schaltfläche

Klicken Sie auf die Schaltfläche „Freigabelink“ und nutzen Sie dann in NekoBox / Shadowrocket / v2rayN / v2rayNG usw. „Aus Zwischenablage importieren“, oder scannen Sie nach dem Klick den QR-Code darüber. Ein Freigabelink enthält keine Regeln, Routing und IPv6 müssen Sie also selbst einrichten: Sind Sie im Ausland und möchten Inhalte aus China sehen, leiten Sie chinesische Domains über den Knoten und schalten IPv6 aus.

Die Clients, die auf der Schaltfläche nach v2rayN stehen, unterstützen alle hysteria2, aber der Freigabelink nutzt ein erweitertes hysteria2-Format, das einige Clients nicht lesen können; scheitert der Import oder verbindet es nicht, wechseln Sie zu Hiddify.

## Clients, die nicht funktionieren

| Client | Warum |
|---|---|
| Surge | Unterstützt hysteria2, liest aber nur das eigene Konfigurationsformat; keiner der drei Typen passt |
| Quantumult X | Unterstützt diese Art Leitung nicht |
| Das ursprüngliche Clash, Clash for Windows | Dem Kern fehlt hysteria2; nehmen Sie stattdessen einen Client mit mihomo-Kern |

## Läuft das Abo ab?

- **Es läuft nicht mit der Zeit ab.** Das Token in der Abo-URL ist an Ihr Konto gebunden und funktioniert, solange das Konto gültig ist; nach Verlängerung oder Tarifwechsel müssen Sie nicht neu importieren.
- **Eine Passwortänderung macht die alte URL sofort ungültig.** So entziehen Sie den Zugang, wenn ein Smartphone verloren geht oder ein Link durchsickert; scannen Sie danach den Code neu.
- **Nach Ablauf des Kontos** liefert die URL 401; sobald Sie verlängern, müssen Sie das vorhandene Profil nicht ersetzen.
- **Profilen, die vor September 2026 importiert wurden**, fehlt die Regel, die IPv6 abweist; löschen Sie sie und importieren Sie neu.

Ist alles importiert, aber es verbindet nicht, siehe [Fehlerbehebung 04](../troubleshooting/04-singbox-import-not-connecting.md).

## Häufige Fragen

**Was ist der Unterschied zwischen einem Hiddify-Abo und einem Clash-Abo?** Das Format unterscheidet sich (JSON bzw. YAML), und kein Client erkennt das Abo des jeweils anderen, die Knoten selbst funktionieren aber mit beiden. LeoTun gibt Ihnen beide direkt: Clash-Clients klicken auf die Schaltfläche „Clash-Abonnement“ und dürfen den Freigabelink nicht nutzen.

**Kann ein Profil alle Regionen enthalten?** Ein Import über eine Flagge ergibt ein Profil pro Region, und Sie wechseln in der Profilliste des Clients; so betrifft eine Adressänderung einer Region nur diese Region. Um alle Regionen außerhalb Chinas auf einmal zu importieren und den Client automatisch wählen zu lassen, klicken Sie oben auf der Seite auf „Alle Regionen importieren · automatisch wählen“ (dort gibt es nur die Schaltflächen sing-box-Abonnement und Clash-Abonnement).

**Kann ich den QR-Code an meine Familie schicken?** Der QR-Code enthält Ihre Zugangsdaten; wer ihn bekommt, hat Ihr Konto. Das Teilen mit der Familie ist erlaubt (gleichzeitige Geräte je nach Tarif: Persönlich 2, Familie 4, Unternehmen 8), aber veröffentlichen Sie ihn nirgends; gelangt er nach außen, ändern Sie Ihr Passwort, und er funktioniert nicht mehr.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=client-02)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-02) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

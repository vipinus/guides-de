# 04 · Was uns von anderen VPNs unterscheidet

VPNs auf dem Markt lassen sich grob in drei Gruppen einteilen: große internationale Marken für Nutzer weltweit, die im chinesischsprachigen Raum bekannten Proxy-Anbieter („Jichang“, die Proxy-Abos weiterverkaufen) und allerlei kostenlose Software. LeoTun betreibt seit 2006 eigene Server und macht nur eine Sache: die Verbindung in beide Richtungen stabil zu halten – für Nutzer in Festlandchina ebenso wie für alle, die aus dem Ausland auf China zugreifen. Dieser Artikel stellt uns Punkt für Punkt neben die drei Produktgruppen und zeigt, für wen sich was eignet und wie wir arbeiten, damit Sie vor dem Bezahlen klar sehen.

## Unsere Ausrichtung in einem Satz

Wir sind ein Dienst, der **gezielt auf das Netz in Festlandchina abgestimmt** ist, kein Wiederverkäufer internationaler Leitungen. Die Qualität der Auslandsanbindungen von China Telecom, China Unicom und China Mobile unterscheidet sich stark; wir optimieren für jeden Anbieter getrennt und empfehlen jeweils andere Regionen. Wir haben Zugangsknoten innerhalb Chinas, damit auch Nutzer mit mittelmäßigem Breitband einen stabilen Einstiegspunkt haben. Ports und Protokolle passen wir laufend an, wenn sich das Netz in China verändert, statt einmal einzurichten und es dabei zu belassen.

Umgekehrt gilt: Wer aus dem Ausland chinesische Dienste erreichen will, wählt mit demselben Konto einfach die Region China. Chinesische Seiten gehen dann über eine chinesische IP hinaus, Seiten außerhalb Chinas landen weiterhin im Ausland. Der Zugriff auf China von außen und der Zugriff auf ausländische Dienste aus China sind zwei Richtungen derselben Sache.

## Im Vergleich mit großen internationalen Marken

- Ihre Stärken: Dutzende Länder, Tausende Server, ausgereifte Apps, unabhängig geprüfte No-Logs-Versprechen. Sind Sie in Europa oder Amerika und wollen nur im öffentlichen WLAN verschlüsseln oder Streamingangebote eines anderen Landes sehen, sind sie eine gute Wahl.
- Ihre Schwächen: Das Produkt ist nicht für das chinesische Netz gebaut. Die Signatur eines proprietären Protokolls ist fest, und sobald sie in China erkannt wird, funktioniert die ganze App nicht mehr; Zugangsknoten in China haben sie nicht, sodass sie für chinesische Videos aus dem Ausland die Funktion entweder gar nicht bieten oder IPs aus Hongkong oder Taiwan nutzen, die Tencent Video und iQIYI genauso sperren.
- Was wir tun: nur Standardprotokolle (AnyConnect, OpenVPN, Hiddify, Tailscale, HTTPS-Web-Proxy), mit Clients direkt von den Herstellern oder aus der Open-Source-Community. Gesperrt werden kann immer nur eine bestimmte Adresse, und dann genügt es, die Adresse zu wechseln; der Client selbst kann nicht aus dem Verkehr gezogen werden.
- Unsere Abwägungen: 24 Regionen, hinter jeder mehrere Maschinen, beim Verbinden wird automatisch die am wenigsten ausgelastete gewählt; die Clients sind die offiziellen Versionen der Hersteller und der Open-Source-Community, eingerichtet per QR-Code oder Import mit einem Klick; einen Prüfbericht eines Dritten gibt es nicht – was wir speichern und was nicht, steht auf der Seite „Über uns“. Wir setzen auf klare Worte statt auf ein Prüfsiegel.

## Im Vergleich mit Proxy-Anbietern

- Stärken der Proxy-Anbieter: günstig, viele Knoten, sofort nutzbar, sobald der Abo-Link eingefügt ist; wer gern an Clients herumbastelt, genießt die Freiheit.
- Schwächen der Proxy-Anbieter: Meist mieten Einzelpersonen oder kleine Teams Server im Ausland und verkaufen Datenvolumen weiter, ohne eigenen Ausgang in China; die Qualität der Ausgänge schwankt mit den gemieteten Leitungen. Verschwinden mit dem Geld, Umbenennen und Schließen sind an der Tagesordnung – wer für ein Jahr zahlt, kann es noch lange nicht ein ganzes Jahr nutzen. Um die Clients müssen sich die Nutzer fast ganz allein kümmern, und wenn etwas schiefgeht, ist niemand zuständig.
- Was wir tun: Die Maschinen gehören uns, und die Ausgänge in China sind eigene, auf Klarnamen registrierte Maschinen bei Cloud-Anbietern in Festlandchina. Ein Konto bietet sechs Verbindungsarten; die Router-Lösung für alle Geräte und die rund um die Uhr erreichbare Supportgruppe haben Proxy-Anbieter nicht. Wir sind von 2006 bis heute in Betrieb, und Konten, Laufzeiten und Preise sind vor und nach der Umbenennung unverändert geblieben.
- Unsere Preise: Tarif Persönlich $4 pro Monat, Familie $8, Unternehmen $16 – darin enthalten sind eigene Maschinen, sechs Verbindungsarten und die Supportgruppe rund um die Uhr. Sie wählen nur die Region; hinter jeder Region nimmt das System die am wenigsten ausgelastete Maschine, Sie müssen also keine Knoten selbst testen und aussuchen.

## Im Vergleich mit kostenloser Software

- Stärken von Gratisangeboten: Sie kosten nichts und reichen, um ab und zu etwas nachzuschlagen.
- Schwächen von Gratisangeboten: Bandbreite an Ausgängen in Festlandchina wird nach Verbrauch abgerechnet; ein Gratisdienst hält sich nur, indem er Nutzer zusammenpfercht, drosselt oder Daten verkauft. Browsererweiterungen leiten nur Webanfragen um; Video, Apps und System-DNS laufen nicht darüber. Installationsprogramme unklarer Herkunft sind schon an sich ein Risiko, siehe „Riskante VPN-Software erkennen“.
- Was wir tun: Der 24-stündige Gratistest braucht keine Kreditkarte und ist zum Ausprobieren gedacht; die Tageszahlung (Punkte) ist für Gelegenheitsnutzer; zahlt ein Freund, den Sie eingeladen haben, erhalten Sie beide 20 Tage (Basis Tarif Persönlich) – eine dauerhafte Quelle für Gratiszeit.
- Wie wir es regeln: Gratiszeit kommt aus dem 24-stündigen Test und aus Einladungsboni; für die dauerhafte Nutzung zahlen Sie monats-, jahres- oder tageweise.

## Sechs Verbindungsarten, ein Konto

Privat (Tailscale): einmal anmelden, dauerhaft online, Region im Menü wechseln. Cisco AnyConnect: die beste Kompatibilität, im System eingebaut oder mit offiziellem Client. OpenVPN: für Router, NAS und Linux. Web-Proxy: nur der Browser läuft darüber, und konstruktionsbedingt gibt es keine Verbindung, die abbrechen könnte. Hiddify: robust gegen Paketverlust, mit der besten Geschwindigkeit. Router: Zugang für alle Geräte, für Fernseher, Set-Top-Boxen und die Geräte älterer Angehöriger.

Jedes Netz hat eine Verbindungsart, die am besten passt, deshalb bekommen Sie alle sechs: Mit demselben Konto wechseln Sie jederzeit – von Hiddify zu AnyConnect, wenn ein Campusnetz UDP einschränkt, zum Web-Proxy, wenn das Breitband wackelt. Wie Sie wählen, steht in „Welche Verbindungsart zu welcher Situation passt“.

## Kontoregeln

- Konten gibt es in drei Tarifen – Persönlich, Familie und Unternehmen – mit 2, 4 bzw. 8 Geräten gleichzeitig online; Regionen, Datenvolumen und Verbindungsarten sind in allen dreien gleich. Auf wie vielen Geräten Sie installieren, ist nicht begrenzt, nur die Zahl gleichzeitiger Verbindungen. Sind mehr Geräte gleichzeitig online, als der Tarif erlaubt, können Sie den Kontotyp vorübergehend hochstufen (die Restlaufzeit wird wertgleich nach Preis umgerechnet) und danach wieder zurückwechseln.
- Zwischen den drei Tarifen wechseln Sie jederzeit, die Restlaufzeit wird wertgleich umgerechnet (Familie und Unternehmen kosten das 2- bzw. 4-Fache von Persönlich). Alle drei Tarife unterstützen den Router; für eine Einzelperson reicht Persönlich.
- Erstattungen erfolgen anteilig nach genutzter Zeit und sind jederzeit möglich; sie werden von Hand bearbeitet, einen festen Zeitpunkt für den Zahlungseingang sagen wir nicht zu.
- Geschwindigkeit: Wir versprechen flüssige YouTube-Wiedergabe, auch zur Abendspitze, sofern Ihr Breitband gut ist – China Unicom im Norden oder China Telecom im Süden. Die Ausnahme ist geteiltes Breitband in Wohnanlagen (小区宽带). Ist eine Region langsam, wechseln Sie Region oder Verbindungsart.
- Die Hiddify- und OpenVPN-Konfigurationen enthalten Ihr Konto, und eine Passwortänderung macht die alten Konfigurationen ungültig: Geht ein Smartphone verloren oder gelangt ein Link nach außen, holen Sie mit einer Passwortänderung alles zurück und importieren danach einfach neu.

## Wie wir arbeiten

- Wir speichern nur, was für die Abrechnung nötig ist. Wir protokollieren nicht, was Sie aufrufen, blenden keine Werbung ein und verkaufen keine Daten.
- Alle Clients stammen von offiziellen Herstellern und bekannten Open-Source-Organisationen – Cisco, OpenVPN, Hiddify und Tailscale – und werden unverändert gespiegelt; eingerichtet wird per QR-Code oder Import mit einem Klick.
- Die Region China läuft auf Maschinen in Festlandchina, alle Ausgangs-IPs liegen in Festlandchina.

## Häufige Fragen

**Sind Sie sicherer als die großen internationalen Marken?** Die Verschlüsselung ist vergleichbar stark; beide nutzen Standardprotokolle. Der Unterschied liegt im Vertrauensmodell: Die großen Marken setzen auf Prüfberichte; wir speichern nur, was für die Abrechnung nötig ist, und alle Clients stammen von offiziellen Herstellern und bekannten Open-Source-Organisationen.

**Warum bieten Sie nicht Hunderte Knoten wie Proxy-Anbieter?** Mehr Knoten heißt nicht stabiler. Hinter jeder unserer Regionen stehen mehrere Maschinen, und beim Verbinden wählt das System die am wenigsten ausgelastete – Sie müssen keine Geschwindigkeitstests machen und keine Knoten aussuchen. Wird eine Adresse gesperrt, wird sie automatisch ersetzt; die Adresse in Ihrem Client müssen Sie nicht ändern.

**Geht es noch günstiger?** Der Tarif Persönlich kostet $4 pro Monat, und je länger Sie kaufen, desto höher der Rabatt (5 % → 10 % → 20 %); tageweise mit Punkten sind es etwa $0.32 pro Tag; zahlt ein eingeladener Freund, erhalten Sie beide 20 Tage mehr (Basis Tarif Persönlich), ohne Begrenzung der Personenzahl. Zur Registrierung gehört außerdem ein 24-stündiger Gratistest.

**Wie kann ich Ihre Angaben überprüfen?** Holen Sie sich den 24-stündigen Test, verbinden Sie sich zur Abendspitze mit der Region China und sehen Sie eine Folge auf Tencent Video, verbinden Sie sich mit einer Auslandsregion und öffnen Sie YouTube, und prüfen Sie den registrierten Standort der IP sowie eine IPv6-Testseite. Die Checkliste steht in „Ein VPN für China auswählen“.


## Weiterlesen

- [Welche Verbindungsart zu welcher Situation passt](https://www.leotun.com/de/guides/choose-connection?utm_source=github&utm_content=network-04)
- [Riskante VPN-Software erkennen](https://www.leotun.com/de/guides/risky-vpn-apps?utm_source=github&utm_content=network-04)
- [VPN für China: kostenlos oder kostenpflichtig](https://www.leotun.com/de/guides/free-vs-paid?utm_source=github&utm_content=network-04)
- [Über uns: wie es aufgebaut ist und was wir speichern](https://www.leotun.com/de/about?utm_source=github&utm_content=network-04)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/why-us?utm_source=github&utm_content=network-04

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=network-04)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=network-04) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

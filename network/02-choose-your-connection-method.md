# 02 · Welche Verbindungsart zu welcher Situation passt

Ein LeoTun-Konto bietet sechs Verbindungsarten: Privat (Tailscale), Cisco (AnyConnect), OpenVPN, Web-Proxy, Hiddify und Router. Jede hat die Situationen, für die sie am besten passt, und dieser Artikel antwortet nach Situation: zuerst nach dem Gerät, das Sie nutzen, dann nach dem Netz, in dem Sie sind, und zuletzt danach, was Sie vorhaben. Zu jeder Situation gibt es eine Empfehlung, die Begründung und eine Alternative. Merken Sie sich eines: ein Konto, sechs Verbindungsarten – eine passt immer zu Ihrem Netz.

## Nach Gerät: womit Sie online gehen

- Ein Smartphone, Dienstreisen und Urlaub: Cisco oder Hiddify. Cisco verbindet, sobald Sie die Adresse in der offiziellen App eingeben, und ist am stabilsten; Hiddify wird per QR-Code importiert und ist bei vielen Paketverlusten schneller. Alternative: Privat.
- Ihr eigener Computer (Windows, Mac): Hiddify oder Privat. Hiddify ist schnell und hat einen eingebauten Split-Routing-Schalter; Privat bleibt nach einer einzigen Anmeldung online. Alternative: Cisco.
- Ein Firmenrechner ohne Administratorrechte: Web-Proxy. Sie installieren nur eine Browser-Erweiterung, brauchen keine Administratorrechte und rühren die Netzwerkeinstellungen der Firma nicht an.
- iPhone, ältere Geräte: Cisco. Es verbindet über das im System eingebaute VPN oder den offiziellen Client, ohne Konfigurationsimport, und die Kompatibilität ist am besten.
- NAS (Synology, QNAP), Linux-Server: OpenVPN. Eine .ovpn-Datei importieren, und es verbindet sich beim Hochfahren automatisch; die meisten dieser Geräte haben einen Client eingebaut.
- Fernseher, Set-Top-Boxen, Spielkonsolen, das Smartphone älterer Angehöriger: Router. Alles, was im WLAN ist, läuft über die Leitung, und auf dem Gerät muss nichts installiert werden. Alle drei Tarife können ihn nutzen.
- Viele Geräte einer ganzen Familie oder eines Büros: Router, einmal eingerichtet, gilt er für alle; möchten Sie von unterwegs auch das NAS zu Hause erreichen, nehmen Sie zusätzlich Privat.

## Nach Netzumgebung: in welchem Netz Sie sind

- Wohnheim- oder Campusnetze, Firmennetze, die UDP einschränken: Cisco. Es läuft über TLS – genau wie das Öffnen einer HTTPS-Website – und ist in eingeschränkten Netzen am stabilsten; Hiddify, Privat und OpenVPN laufen alle über UDP und werden langsam oder brechen ab.
- Breitband, das oft abbricht, schwaches WLAN: Web-Proxy. Er arbeitet pro Anfrage ohne dauerhafte Verbindung; es gibt also folgerichtig keine Verbindung, die abbrechen könnte.
- Breitband in älteren Wohnanlagen, mobile Daten, viele Paketverluste: Hiddify. Sein Protokoll ist darauf ausgelegt, Paketverluste zu verkraften, und liefert in solchen Netzen das beste Tempo.
- Der Computer ist schon mit einem Firmen-VPN verbunden: Web-Proxy. Zwei VPNs für das ganze Gerät streiten sich um die Netzwerkeinstellungen; der Web-Proxy kümmert sich nur um den Browser, sodass sich beide nicht stören.
- Breitband von China Mobile, Great Wall und anderen, oder grenzüberschreitende Verbindungen, die ständig instabil sind: jede Verbindungsart mit einem Einstiegspunkt in der Region China. In diesen Netzen ist das meist die stabilste Wahl.

## Nach Zweck: was Sie vorhaben

- Sie sind im Ausland und möchten chinesische Videos schauen: jede Verbindungsart für das ganze Gerät (Cisco, Hiddify, Privat, OpenVPN, Router) mit der Region China; für den Fernseher zu Hause nehmen Sie den Router. Nehmen Sie für Videos nicht den Web-Proxy: Er erreicht den eigenen Netzwerkkanal des Geräts nicht, sodass die Videoseite Sie womöglich weiterhin im Ausland sieht.
- Spiele, Sprach- und Videoanrufe: Hiddify, Privat oder Router, mit der Region mit der niedrigsten Latenz. Der Web-Proxy kümmert sich nur um den Browser; Spiele und Anruf-Apps laufen nicht darüber.
- Büroarbeit und Recherche, nur im Browser: Der Web-Proxy ist am unkompliziertesten; müssen Sie sich mit internen Firmensystemen verbinden, prüfen Sie zuerst, ob das Firmen-VPN neben unserem laufen kann, und wenn nicht, nehmen Sie den Web-Proxy.
- Server, Skripte, Kommandozeile: OpenVPN; auf einem Linux-Desktop können Sie auch Privat oder Hiddify nutzen.
- Von unterwegs auf NAS oder Kameras zu Hause zugreifen: Privat. Geräte desselben Kontos erreichen einander, ohne dass Sie am Router Ports öffnen müssen.

## Die sechs Verbindungsarten auf einen Blick: am besten für / nicht geeignet für

- Privat (Tailscale) – am besten für: mehrere Geräte, einmal anmelden und vergessen, von unterwegs auf Geräte zu Hause zugreifen. Nicht geeignet für: Netze, die UDP einschränken (dann bleiben nur Relays, und die sind langsam), den Betrieb neben einem anderen VPN.
- Cisco AnyConnect – am besten für: eingeschränkte Netze, Firmenrechner, iPhone, ältere Geräte; die beste Kompatibilität. Nicht geeignet für: Nutzer in China, die nicht den gesamten Datenverkehr über die Leitung schicken wollen (dafür muss ein separates Split-Routing-Skript laufen).
- OpenVPN – am besten für: NAS, Linux-Server, OpenWrt-Router; eine Datei importieren, und es verbindet sich beim Hochfahren automatisch. Nicht geeignet für: den Alltag auf Smartphone und Computer, wo es weniger bequem ist als Cisco und Hiddify; Netze, die UDP einschränken.
- Web-Proxy – am besten für: keine Administratorrechte, bereits mit einem Firmen-VPN verbunden, Breitband, das oft abbricht. Nicht geeignet für: Video-Apps, Spiele, Anrufe; er kümmert sich nur um den Browser.
- Hiddify – am besten für: alle, die Tempo wollen, Netze mit vielen Paketverlusten; Import per QR-Code, dieselbe App auf fünf Plattformen, eingebautes Split-Routing. Nicht geeignet für: Netze, die UDP einschränken.
- Router – am besten für: eine ganze Familie, ein Büro, Geräte, auf denen sich kein Client installieren lässt; die Firmware hat Split-Routing eingebaut und aktualisiert sich automatisch. Nicht geeignet für: Menschen mit nur einem Gerät, die oft unterwegs sind (unterwegs brauchen Sie trotzdem einen Client).

## Die Region nach Ihrem Breitband wählen

Dieselbe Verbindungsart kann je nach Region um ein Mehrfaches unterschiedlich schnell sein; das liegt an der Auslandsanbindung Ihres Netzbetreibers in diese Region, nicht am Server. China Unicom im Norden: zuerst Japan und Korea probieren. China Telecom im Süden: zuerst Südostasien (Singapur, Malaysia, Thailand, Philippinen, Indonesien) oder Australien probieren. Anderes Breitband (China Mobile, Great Wall und andere): zuerst den Einstiegspunkt in der Region China probieren.

Die rote, gelbe und grüne Ampel in der Regionsliste zeigt die aktuelle Auslastung jeder Region; gibt es mehrere Einstiege für Japan, nehmen Sie den mit grüner Ampel. Zwischen 20 und 23 Uhr ist landesweit Spitzenzeit; wählen Sie dann eine Region mit grüner Ampel oder wechseln Sie die Verbindungsart. Ist es trotzdem langsam, liegt es meist am lokalen Breitband (geteiltes Breitband in Wohnanlagen, oder Netzbetreiber und Region passen nicht zusammen).

## Split-Routing: in China direkt, ins Ausland über die Leitung

Split-Routing brauchen nur Nutzer in Festlandchina; Nutzer im Ausland nehmen den globalen Modus, und eingeschaltetes Split-Routing würde manche Websites sogar auf Umwege schicken. In Hiddify schalten Sie im Client auf automatisches Split-Routing um, beim Web-Proxy in der Erweiterung auf Split-Routing; der Router übernimmt das Split-Routing für jedes Gerät im Netz, und seine Firmware hat es standardmäßig eingeschaltet. Bei Cisco und OpenVPN läuft nach dem Verbinden der gesamte Datenverkehr über die Leitung, im Bereich „Cisco“ steht ein Split-Routing-Skript zur Verfügung; Privat schickt das ganze Gerät über die Leitung.

Öffnet sich eine Website mit Split-Routing nicht, schalten Sie zur Prüfung vorübergehend auf „Global“: Öffnet sie sich dann, steht sie nicht auf der Liste; öffnet sie sich auch global nicht, liegt das Problem bei der Website selbst.

## Wie Sie wechseln, wenn es nicht klappt

1. Wechseln Sie zuerst die Region. Verbindet eine andere Region, ist dieser Server nur vorübergehend nicht erreichbar.
2. Wechseln Sie dann das Netz. Klappt es über Breitband nicht, wechseln Sie auf mobile Daten und umgekehrt; Störungen bei verschiedenen Netzbetreibern treten nicht gleichzeitig auf.
3. Wechseln Sie dann die Verbindungsart. Klappen die UDP-basierten (Hiddify, Privat, OpenVPN) nicht, wechseln Sie zu Cisco, das über TLS läuft; brechen Verbindungsarten für das ganze Gerät immer wieder ab, wechseln Sie zum Web-Proxy. Die Sperren der verschiedenen Protokolle sind voneinander unabhängig.
4. Klappt es immer noch nicht, lesen Sie die Fehlerbehebung oder fragen Sie in der Supportgruppe und nennen Sie dabei Verbindungsart, Region, den genauen Wortlaut der Fehlermeldung und die Uhrzeit.

## Häufige Fragen

**Welche der sechs Verbindungsarten ist am schnellsten?** In Netzen mit vielen Paketverlusten ist Hiddify am schnellsten; in sauberen Netzen ist der Unterschied gering, und den Engpass bilden Region und Tageszeit, nicht die Verbindungsart.

**Welche für Spiele und Sprachanrufe?** Hiddify, Privat oder Router, mit der Region mit der niedrigsten Latenz. Der Web-Proxy kümmert sich nur um den Browser; Spiele und Anruf-Apps laufen nicht darüber.

**Kann ich die sechs Verbindungsarten gleichzeitig nutzen?** Auf verschiedenen Geräten ja; alle Verbindungsarten eines Kontos teilen sich das Kontingent gleichzeitig verbundener Geräte (Persönlich 2 Geräte, Familie 4 Geräte, Unternehmen 8 Geräte). Betreiben Sie auf demselben Gerät nicht zwei Verbindungsarten für das ganze Gerät gleichzeitig (etwa Privat und Cisco), denn sie streiten sich um die Netzwerkeinstellungen.

**Muss ich mich zwischen Router und Client entscheiden?** Nein. Nutzen Sie zu Hause den Router und schalten Sie unterwegs den Client auf dem Smartphone ein; beide zählen jeweils als ein Gerät.

**Welche für Linux?** Privat, OpenVPN und Hiddify haben alle Linux-Clients; Cisco nutzt unter Linux das quelloffene OpenConnect; OpenVPN verlangt unter Linux bei der ersten Verbindung Konto und Passwort. Für Server und NAS ist OpenVPN am unkompliziertesten.

## Weiterlesen

- [Was uns von anderen VPNs unterscheidet](https://www.leotun.com/de/guides/why-us?utm_source=github&utm_content=network-02)
- [Was das private Netzwerk (Tailscale) ist](https://www.leotun.com/de/guides/tailscale-mesh?utm_source=github&utm_content=network-02)
- [Wie Sie OpenVPN nutzen und wann Sie es wählen](https://www.leotun.com/de/guides/openvpn-setup?utm_source=github&utm_content=network-02)
- [Was der Web-Proxy ist und wann Sie ihn nutzen](https://www.leotun.com/de/guides/web-proxy?utm_source=github&utm_content=network-02)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/choose-connection?utm_source=github&utm_content=network-02

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=network-02)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=network-02) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

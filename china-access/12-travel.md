# 12 · Einrichtung für Dienstreisen und Urlaub

Für eine kurze Auslandsreise oder eine Dienstreise nach China brauchen Sie weder einen Router noch Protokollkenntnisse: Installieren Sie den Cisco-Client (Cisco Secure Client) auf dem Smartphone, verbinden Sie sich vor der Abreise einmal zur Probe, und nach der Landung läuft es sofort. Beide Richtungen funktionieren gleich: Brauchen Sie unterwegs außerhalb Chinas Google, Firmen-E-Mail und Karten, wählen Sie eine nahe gelegene Auslandsregion; sind Sie in China und möchten chinesische Videos schauen oder sich beim Onlinebanking anmelden, wählen Sie die Region China. Dieser Artikel behandelt zehn Minuten Vorbereitung vor der Abreise, zwei typische Fallstricke in Hotel- und Abflughallen-WLANs und den Umgang mit Onlinebanking und Bezahl-Apps.

## Zehn Minuten vor der Abreise

1. Installieren Sie Cisco Secure Client auf dem Smartphone (App Store / Google Play oder das Installationsprogramm von der Cisco-Seite unserer Website), melden Sie sich auf unserer Website an, klicken Sie auf eine Flagge, um die Adresse einer Region zu kopieren, tragen Sie sie ein und verbinden Sie sich einmal mit Konto und Passwort unserer Website, um zu prüfen, dass es klappt.
2. Kopieren Sie die Adressen von zwei weiteren Regionen und speichern Sie sie im Client: eine nahe am Reiseziel und eine als Reserve. Das Netz vor Ort ist ein anderes, und die beste Region ist oft nicht dieselbe.
3. Notieren Sie sich die vier Domains (leotun.com → 7d24hrs.com → 7x24btc.com → anyfq.com) und den Zugang zu mindestens einer Supportgruppe, damit Sie in einem unbekannten Netz jemanden erreichen, wenn etwas schiefgeht.
4. Richten Sie auch auf dem Laptop eine Verbindungsart ein oder nutzen Sie die Web-Proxy-Erweiterung; die funktioniert auch auf einem Firmenrechner, auf dem sich kein Client installieren lässt.

## Nach der Landung

- Haben Sie auf eine lokale SIM-Karte gewechselt oder Roaming eingeschaltet, verbindet der Client einfach, ohne Neueinrichtung; verlassen die Roaming-Daten das Land ohnehin schon, dient die Leitung nur dazu, die Ausgangsregion festzulegen.
- Außerhalb Chinas, wenn Sie Google, Gmail, Firmen-E-Mail und Karten brauchen: Wählen Sie eine nahe gelegene Auslandsregion, das ist am schnellsten.
- In China, wenn Sie Tencent Video und iQIYI schauen, NetEase Cloud Music hören oder sich beim Onlinebanking anmelden möchten: Wählen Sie die Region China. Chinesische Websites gehen dann über eine chinesische IP hinaus, ausländische Websites landen weiterhin im Ausland – mit der Region China in China verbunden zu sein, hindert Sie also nicht daran, Gmail weiter zu nutzen.
- Verbindet eine Auslandsregion aus China heraus nicht: Wechseln Sie die Region, wechseln Sie auf mobile Daten, und klappt es dann immer noch nicht, wechseln Sie zu Hiddify oder OpenVPN; die Sperren der drei Protokolle sind voneinander unabhängig.

## Zwei Fallstricke in Hotel-, Abflughallen- und Café-WLANs

- Anmeldeportal (Captive Portal): Schließen Sie nach dem Verbinden mit dem WLAN zuerst die Anmeldung im Browser ab und schalten Sie erst dann die Leitung ein. Ein Client, der automatisch verbindet, versucht es vor der Anmeldung und scheitert; warten Sie kurz oder verbinden Sie manuell neu.
- UDP-Einschränkungen: Viele Hotel- und Abflughallen-WLANs drosseln oder blockieren UDP. Cisco läuft über TLS und ist nicht betroffen – auch deshalb ist Cisco die erste Empfehlung für Reisen. Nutzen Sie Hiddify oder Privat und es ist langsam oder bricht ab, wechseln Sie zu Cisco.

## Onlinebanking, Zahlungen, 12306

Diese Apps speichern die IP der Anmeldung, und ständiges Hin- und Herspringen zwischen Ausland und China löst am leichtesten die Risikokontrolle aus. Wenn Sie etwas erledigen müssen, verbinden Sie sich zuerst mit der Region China und öffnen dann die App; danach beenden Sie die App und trennen erst dann die Verbindung. Wechseln Sie auf Reisen bei derselben Bank nicht ständig zwischen beiden Netzarten.

SMS-Bestätigungscodes, die nie ankommen, haben nichts mit der Leitung zu tun; das ist ein Roaming-Problem der Telefonnummer. Schalten Sie vor der Abreise Roaming für Ihre chinesische Nummer ein oder wechseln Sie zu einem Tarif, der im Ausland Codes empfangen kann.

## Häufige Fragen

**Die Reise dauert nur ein paar Tage. Muss ich einen ganzen Monat kaufen?** Nein. Fordern Sie den 4-stündigen Gratistest an, oder laden Sie Punkte auf und zahlen Sie tageweise: Im Tarif Persönlich kostet ein Tag 1 Punkt, etwa 0,32 US-Dollar – ideal für ein paar Tage.

**Können Smartphone und Laptop gleichzeitig verbunden sein?** Ja. Je nach Tarif sind mit einem Konto 2 / 4 / 8 Geräte gleichzeitig online (Persönlich / Familie / Unternehmen); der Tarif Persönlich reicht genau für ein Smartphone plus einen Laptop.

**Warum empfehlen Sie für Reisen Cisco statt Hiddify?** In einem fremden Netz ist eingeschränktes UDP die größte Sorge. Cisco läuft über TLS – genau wie der Aufruf einer HTTPS-Website – und kommt fast überall durch; Hiddify ist in Netzen mit vielen Paketverlusten schneller, funktioniert aber nicht, wenn UDP eingeschränkt ist. Am zuverlässigsten ist es, beides zu installieren und zu wechseln, wenn eines nicht geht.

**Werden lokale Websites im Ausland langsamer, wenn ich die Region China nutze?** Lokale Websites laufen direkt am flüssigsten: Trennen Sie die Verbindung, sobald Sie mit den chinesischen Inhalten fertig sind, oder verbinden Sie sich nur bei Bedarf.

## Weiterlesen

- [Cisco AnyConnect: Download und Einrichtung](https://www.leotun.com/de/anyconnect?utm_source=github&utm_content=china-access-12)
- [Wie Auslandsstudierende ein VPN nach China einrichten](https://www.leotun.com/de/guides/students?utm_source=github&utm_content=china-access-12)
- [So erreichen Sie uns – und verlieren nie den Kontakt](https://www.leotun.com/de/guides/stay-in-touch?utm_source=github&utm_content=china-access-12)
- [VPN für China: kostenlos oder kostenpflichtig](https://www.leotun.com/de/guides/free-vs-paid?utm_source=github&utm_content=china-access-12)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/travel?utm_source=github&utm_content=china-access-12

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=china-access-12)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=china-access-12) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

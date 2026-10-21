# 10 · Wie Auslandsstudierende ein VPN nach China einrichten

Studierende im Ausland brauchen keine „Leitung nach China, die ständig verbunden ist“, sondern in einigen bestimmten Situationen zuverlässig eine chinesische IP: um Serien zu schauen und Musik zu hören, sich beim Onlinebanking und in Behörden-Apps anzumelden, Tickets zu ergattern und gelegentlich aus der Ferne nach den Geräten der Familie zu sehen. Jede Situation stellt andere Anforderungen an die Leitung, und Campusnetze haben ihre eigenen Grenzen. Dieser Artikel erklärt Situation für Situation, was nötig ist, wie Sie es einrichten und wann Sie trennen – und schließt mit einer Checkliste, die sich vor Semesterbeginn in zehn Minuten abarbeiten lässt.

## Serien, Musik, Livestreams: Eine chinesische IP genügt, aber IPv6 muss dicht sein

Tencent Video, iQIYI, die Anime auf Bilibili, NetEase Cloud Music und QQ Music bestimmen die Region anhand der Quell-IP; eine Verbindung über die Leitung nach China reicht. Die Falle, in die Auslandsstudierende am häufigsten tappen: Campus- und Wohnheimnetze haben meist IPv6. Das Gerät bevorzugt IPv6, das nicht über die Leitung läuft, und so sieht die Videoseite trotzdem eine ausländische Adresse und meldet „Urheberrechtsbeschränkung“.

Abhilfe schafft eine Leitung oder ein Client, der IPv6 im Tunnel abweist, oder Sie schalten IPv6 auf dem Gerät aus. Alle drei Verbindungsarten von LeoTun blockieren IPv6 bereits auf der Leitungsseite, am Gerät müssen Sie nichts ändern; die ausführliche Fehlersuche steht in „Was tun, wenn Tencent Video im Ausland eine Urheberrechtsmeldung zeigt“.

Die Bildqualität hängt von der grenzüberschreitenden Bandbreite ab. Von 20 bis 23 Uhr Pekinger Zeit ist Spitzenzeit, in Europa und Nordamerika entspricht das dem Vormittag bis Mittag; dreht sich 1080p in dieser Zeit ständig im Kreis, wechseln Sie zu einem anderen Ausgang in China.

## Onlinebanking, Alipay, Behörden-Apps: über die Leitung nach China anmelden, danach trennen

Banking-Apps, Alipay, CHSI (das Portal für Studien- und Abschlussnachweise) und die nationale Plattform für Behördendienste gehen unterschiedlich mit ausländischen IPs um: Manche lehnen die Anmeldung gleich ab, manche schieben mehrere zusätzliche Prüfungen ein, manche lassen Sie zwar hinein, lösen aber bei einer Überweisung die Risikokontrolle aus. Gemeinsam ist ihnen, dass sie Ihre Anmelde-IP speichern – und häufiges Hin- und Herspringen zwischen Ausland und China fällt am schnellsten auf.

So gehen Sie vor: Wenn Sie so etwas erledigen müssen, verbinden Sie sich zuerst mit der Leitung nach China und öffnen dann die App; wenn Sie fertig sind, beenden Sie die App und trennen danach die Leitung. Nutzen Sie dieselbe App nicht, während Sie ständig zwischen der Leitung nach China und dem lokalen Netz wechseln.

Bestätigungscodes per SMS, die nie ankommen, haben mit der Leitung nichts zu tun; das ist ein Roaming-Problem einer chinesischen Telefonnummer im Ausland. Schalten Sie vor der Ausreise internationales Roaming für die Nummer frei oder wechseln Sie zu einem Tarif, der im Ausland Codes empfangen kann.

## 12306 und Konzertkarten: vorher verbinden, beim Bezahlen nicht wechseln

12306 (die chinesische Bahnbuchung) verlangt bei einer ausländischen IP manchmal eine zusätzliche Prüfung, und beim Ansturm auf Tickets bedeutet eine zusätzliche Prüfung, dass das Ticket weg ist. Verbinden Sie sich einige Minuten vor Verkaufsstart mit der Leitung nach China, melden Sie sich an und wählen Sie die Reisenden aus; sobald es losgeht, schicken Sie die Bestellung ab. Leitet die Zahlung zu Alipay oder zum Onlinebanking weiter, lassen Sie die Leitung unverändert.

Für Ticketplattformen wie Damai und Maoyan gilt dasselbe.

## Drei Grenzen von Campus- und Wohnheimnetzen

- IPv6: siehe oben; nutzen Sie eine Leitung, die IPv6 blockiert.
- UDP eingeschränkt oder gedrosselt: Etliche Campusnetze drosseln UDP-Verkehr oder sperren ihn sogar. Das von Hiddify genutzte hysteria2 läuft über UDP und ist in solchen Netzen sogar weniger stabil als AnyConnect, das über TLS läuft; ein Konto kann beides nutzen – funktioniert UDP nicht, wechseln Sie zu AnyConnect.
- Anmeldeportal (Captive Portal): Nachdem Sie sich mit dem Campus-WLAN verbunden haben, schließen Sie zuerst die Anmeldung im Browser ab und schalten dann die Leitung ein. Ist der Client auf „beim Start automatisch verbinden“ eingestellt, versucht er es vor der Anmeldung und scheitert; warten Sie etwas länger oder verbinden Sie von Hand neu.

## In den Ferien in China: dasselbe Konto, nur andersherum

In China brauchen Sie Google, die E-Mail Ihrer Hochschule und Literaturdatenbanken; ändern Sie einfach die Region der Leitung von China auf Japan, die USA oder eine nahe Auslandsregion – ein anderes Konto brauchen Sie nicht. Die 24 Regionen von LeoTun gehören alle zum selben Konto; der Zugriff auf China aus dem Ausland und der Zugriff auf das Ausland aus China sind zwei Richtungen derselben Sache.

Verbinden Sie sich aus China, wechseln die Adressen für AnyConnect und Hiddify automatisch, um Sperren auszuweichen; die im Client gespeicherten Adressen müssen Sie nicht ändern. Verbindet es nicht, wechseln Sie Region oder Protokoll.

## Zehn-Minuten-Checkliste vor Semesterbeginn

1. Installieren Sie einen Client (AnyConnect oder Hiddify) auf dem Smartphone und einen auf dem Computer, und melden Sie sich jeweils an oder importieren Sie per QR-Code.
2. Verbinden Sie sich im Wohnheim-WLAN mit der Leitung nach China und öffnen Sie eine IPv6-Testseite, um zu prüfen, dass IPv6 nicht verfügbar ist oder eine Adresse in Festlandchina zeigt.
3. Öffnen Sie Tencent Video und spielen Sie eine beliebige Folge ab, um zu prüfen, dass keine Urheberrechtsbeschränkung erscheint.
4. Melden Sie sich einmal in Ihrer Banking-App an, um zu prüfen, dass Sie hineinkommen; beenden Sie dann die App und trennen Sie die Leitung.
5. Notieren Sie den Supportkontakt Ihres Anbieters; geht etwas schief, lesen Sie zuerst die Anleitung zur Fehlerbehebung und fragen dann.

## Häufige Fragen

**Wirkt sich ein VPN nach China auf mein Netzwerkkonto an der Hochschule aus?** Nein. Die Leitung schickt nur Ihren Datenverkehr zu einem Ausgang in China; das Campusnetz sieht eine einzige verschlüsselte Verbindung. Die Nutzungsregeln der meisten Hochschulen verbieten nur urheberrechtsverletzende Downloads und Angriffe; der private Zugriff auf Dienste im eigenen Heimatland gehört nicht dazu. Sind Sie unsicher, werfen Sie einen Blick in die Nutzungsordnung Ihrer Hochschule.

**Kann ich ein Konto mit meinem Mitbewohner teilen?** Je nach Tarif können bei einem Konto 2 (Persönlich), 4 (Familie) oder 8 (Unternehmen) Geräte gleichzeitig online sein; das Teilen mit Familie oder Mitbewohnern ist nach den Regeln erlaubt. Für Dinge wie Onlinebanking ist es aber sicherer, wenn jeder sein eigenes Konto nutzt – sonst wechseln mehrere Personen auf derselben Leitung ständig hin und her und lösen die Risikokontrolle aus.

**Warum ist Hiddify im Wohnheim langsam, AnyConnect aber normal?** Höchstwahrscheinlich schränkt das Campusnetz UDP ein. Das hysteria2-Protokoll von Hiddify basiert auf UDP und wird bei Drosselung langsam oder bricht ab; AnyConnect läuft über TLS, genau wie der Aufruf einer HTTPS-Website, und ist nicht betroffen.

**Kann ich über eine Leitung nach China auf chinesischen Servern spielen?** Anmelden können Sie sich, aber die Latenz hängt von Ihrer räumlichen Entfernung zum Ausgang in China ab. Dieser Teil der Latenz ist fest; für rundenbasierte Spiele und MOBAs ist er akzeptabel, bei Shootern spürbar.

**Nützt mir das Konto nach dem Abschluss und der Rückkehr nach China noch?** Ja. Dasselbe Konto funktioniert in China mit einer Auslandsregion weiter – für Google, GitHub, die E-Mail Ihrer Hochschule und Literaturdatenbanken.

## Weiterlesen

- [Was tun, wenn Tencent Video im Ausland eine Urheberrechtsmeldung zeigt](https://www.leotun.com/de/guides/overseas-video?utm_source=github&utm_content=china-access-10)
- [Ein VPN für China auswählen](https://www.leotun.com/de/guides/choose-china-vpn?utm_source=github&utm_content=china-access-10)
- [AnyConnect-Client herunterladen](https://www.leotun.com/de/anyconnect?utm_source=github&utm_content=china-access-10)
- [Hiddify-Client und Abo-Import](https://www.leotun.com/de/singbox?utm_source=github&utm_content=china-access-10)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/students?utm_source=github&utm_content=china-access-10

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=china-access-10)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=china-access-10) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

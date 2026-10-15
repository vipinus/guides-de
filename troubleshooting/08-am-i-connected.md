# 08 · So prüfen Sie, ob Sie wirklich verbunden sind und über welche Region Sie hinausgehen

Zeigt der Client „Verbunden“, heißt das noch nicht, dass die Websites, die Sie besuchen, die Adresse des VPN sehen. Am einfachsten prüfen Sie es direkt in der oberen Leiste unserer Website: Das Feld „Aktuelles Netzwerk“ zeigt **Sie so, wie unsere Website Sie gerade sieht** – aus welchem Land, welcher Provinz bzw. welchem Bundesstaat und welchem Netz Sie kommen. Dieser Artikel erklärt, wie Sie dieses Feld lesen, wie Sie vor und nach dem Verbinden vergleichen, woran Sie bei jeder der sechs Verbindungsarten erkennen, dass sie verbunden ist, was die rote, gelbe und grüne Ampel in der Regionsliste bedeutet und was Sie selbst prüfen können, wenn es „verbunden ist, aber trotzdem lokal anzeigt“.

## Was „Aktuelles Netzwerk“ in der oberen Leiste anzeigt

| Position | Inhalt |
|---|---|
| Vorn | Die Flagge des Landes, in dem der Ausgang liegt; lässt sich das Land nicht bestimmen, erscheint stattdessen ein WLAN-Symbol |
| In der Mitte | Der Name der Provinz bzw. des Bundesstaats in der Sprache der Oberfläche (USA, Kanada, Australien usw. nutzen gängige Abkürzungen wie CA, ON, NSW); bei Hongkong, Macau und Singapur steht direkt der Name der Region |
| Am Ende | Der Netzname: Chinas drei große Netzbetreiber, das Bildungsnetz und Ähnliche erscheinen in der chinesischen Oberfläche mit Kurznamen wie 电信 (China Telecom), 移动 (China Mobile), 联通 (China Unicom) und 教育网 (Bildungsnetz); alle anderen zeigen ihren englischen Markennamen (z. B. Comcast, Bell) |

- **Lässt sich die Provinz bzw. der Bundesstaat nicht ermitteln, erscheint nur „Flagge · Netzname“.** Der Ländername wird nicht als Lückenfüller genutzt; die Flagge sagt Ihnen das Land.
- Am Computer zeigt ein Mauszeiger über diesem Feld ein Popup mit vollständigem Namen der Organisation, Provinz bzw. Bundesstaat, Ländercode und **Ausgangs-IP**. Diese IP sehen nur Sie, und sie ist das Nützlichste, was Sie zur Hand haben können, wenn Sie den Support kontaktieren.
- Chrome / Edge unter Windows haben keine Flaggenschrift, daher erscheint die Flagge als zwei Buchstaben (z. B. JP, US). Die Bedeutung ist dieselbe.
- Am Computer erscheint das Feld in der oberen Leiste erst nach der Anmeldung; auf dem Smartphone wird es auch ohne Anmeldung angezeigt.

## Vorher und nachher vergleichen – auf einen Blick

1. **Bei ausgeschaltetem VPN** öffnen Sie unsere Website und schauen hin: Dort sollte der Netzbetreiber Ihres Heimanschlusses oder Ihrer mobilen Daten stehen, und die Flagge sollte das Land zeigen, in dem Sie sind.
2. **Verbinden Sie das VPN** und gehen Sie zurück in den Browser: Die Flagge wechselt zur gewählten Region, und der Netzname wechselt meist zum Namen eines Rechenzentrums oder Cloud-Anbieters statt Ihres Netzbetreibers.
3. Ist beides gleich, läuft dieser Browser beim Besuch unserer Website nicht über das VPN. Siehe unten „Verbunden, aber es zeigt trotzdem lokal“.

**Sie müssen die Seite nicht ständig neu laden.** Das Feld prüft automatisch neu, wenn Sie ins Browserfenster zurückwechseln, prüft nach einer erkannten Netzänderung innerhalb weniger Sekunden noch einige Male und aktualisiert sich außerdem alle zehn bis zwanzig Sekunden, solange die Seite offen ist. Sehen Sie direkt nach dem Verbinden noch den alten Wert, warten Sie zehn bis zwanzig Sekunden oder wechseln Sie das Fenster; hat er sich dann immer noch nicht geändert, laden Sie von Hand neu.

**Sind Sie in China und haben einen „Einstiegspunkt in China“ gewählt**, ist es normal, dass die obere Leiste ein ausländisches Land zeigt: Die Einstiegspunkte in China nutzen Split-Routing, sodass chinesische Websites innerhalb Chinas hinausgehen und ausländische Websites über die Auslandsstrecke ankommen. Unsere Website steht im Ausland, also wird natürlich das ausländische Ende angezeigt.

## Woran Sie bei jeder Verbindungsart erkennen, dass sie verbunden ist

| Verbindungsart | Worauf Sie im Client achten | Ändert sich die obere Leiste unserer Website? |
|---|---|---|
| Cisco (AnyConnect) | Der Client zeigt „Connected“ (verbunden) | Ja. Ist Cisco verbunden, läuft der gesamte Datenverkehr über das VPN |
| Hiddify | Der Client zeigt „verbunden“ | Im globalen Modus ja; bei automatischem Routing hängt es von der Liste ab |
| OpenVPN | Der Client zeigt „verbunden“ | Ja. Standardmäßig läuft der gesamte Datenverkehr über das VPN |
| Privat (Tailscale) | Der Client ist online **und** als Exit Node (Ausgangsknoten) ist eine Region gewählt | Nur wenn ein Ausgang gewählt ist; mit None (keiner) erreichen sich nur die Geräte untereinander, und der Datenverkehr läuft nicht über das VPN |
| Web-Proxy | Es gibt keinen Zustand „verbunden“; schauen Sie, welcher Regionsmodus im Erweiterungssymbol gewählt ist | Nur der Browser mit der Erweiterung ändert sich; die „Auto Switch“-Regeln (automatisch umschalten) können unsere Website direkt verbinden lassen |
| Router | In der Verwaltungsoberfläche ist der Kontostatus normal und das Ablaufdatum wird angezeigt | Schauen Sie von einem Gerät aus, das im WLAN dieses Routers ist; im Split-Routing-Modus hängt es von der Liste ab |

Split-Routing heißt: Websites auf der Liste laufen über das VPN, alles andere direkt. Zeigt die obere Leiste bei eingeschaltetem Split-Routing lokal an, heißt das nicht unbedingt, dass Sie nicht verbunden sind: **Schalten Sie vorübergehend auf „Global“ und schauen Sie noch einmal.** Ändert es sich dann, funktioniert das VPN, und unsere Website steht einfach nicht auf der Liste.

## Die rote, gelbe und grüne Ampel in der Regionsliste

Auf den Seiten Cisco, Hiddify, Web-Proxy und OpenVPN steht unter der Flagge jeder Region eine kleine Ampel, und dieselbe Ampel erscheint vor den Ausgangsnamen im Client von Privat. Sie wird automatisch nach der durchschnittlichen Echtzeit-Bandbreite der Server dieser Region eingestuft und etwa einmal pro Minute aktualisiert:

| Ampel | Bedeutung |
|---|---|
| Grün (leuchtet) | Frei |
| Gelb (blinkt) | In Benutzung |
| Rot (blinkt) | Ausgelastet |
| Keine Ampel | Im Moment wurden keine Daten abgerufen; das heißt nicht, dass der Server ausgefallen ist |

Am Computer sehen Sie mit dem Mauszeiger über der Ampel die durchschnittliche Auslastung der Region.

**Was tun bei roter Ampel:**

- Rot heißt nicht kaputt, sondern nur, dass gerade viele Menschen dort sind. Sind Sie schon verbunden und das Tempo reicht, lassen Sie es, wie es ist.
- Fühlt es sich langsam an, wechseln Sie zu einer Region mit grüner Ampel. Bei Cisco klicken Sie auf der Webseite auf eine andere Flagge, um die neue Adresse zu kopieren; bei Hiddify importieren Sie die Konfiguration einer anderen Region; bei Privat ändern Sie es unter Exit Node; beim Web-Proxy klicken Sie im Erweiterungssymbol auf eine andere Region.
- Hinter einer Region stehen mehrere Maschinen, und beim Verbinden wird automatisch die am wenigsten ausgelastete gewählt. Sie müssen keine Maschine selbst auswählen.
- Zwischen 20 und 23 Uhr ist Spitzenzeit. Wählen Sie dann eine Region mit grüner Ampel oder wechseln Sie die Verbindungsart; ist es trotzdem langsam, liegt es meist am lokalen Breitband (geteiltes Breitband in Wohnanlagen, oder Netzbetreiber und Region passen nicht zusammen). Wie Sie die Region nach Netzbetreiber wählen, steht unter „Weiterlesen“.

## Verbunden, aber es zeigt trotzdem lokal

In der Reihenfolge, wie häufig es vorkommt:

1. **Routing-Regeln lassen unsere Website direkt verbinden.** Das automatische Routing von Hiddify, „Auto Switch“ der Web-Proxy-Erweiterung und der Split-Routing-Modus des Routers können unsere Website am VPN vorbeiführen. Schalten Sie zur Prüfung vorübergehend auf global; beim Web-Proxy können Sie unsere Website auch in die Regeln aufnehmen.
2. **Der Web-Proxy gilt nur für diesen einen Browser.** Schauen Sie aus einem anderen Browser oder einer Smartphone-App, steht dort natürlich weiterhin lokal.
3. **Kein Ausgang in Privat gewählt.** Online ≠ über das VPN; steht Exit Node auf None, erreichen sich nur die Geräte untereinander.
4. **Sie schauen vom falschen Gerät aus.** Bei der Router-Lösung müssen Sie von einem Gerät schauen, das im WLAN dieses Routers ist – nicht von einem Smartphone im WLAN des Modems oder mit mobilen Daten.
5. **Ein weiteres VPN oder Mesh-Netzwerk-Tool ist gleichzeitig eingeschaltet.** Ein Firmen-VPN oder der Beschleuniger eines anderen Anbieters streitet sich um die Routen. Lassen Sie nur eines laufen.
6. **Es hat sich noch nicht aktualisiert.** Warten Sie zehn bis zwanzig Sekunden, wechseln Sie das Fenster oder laden Sie einmal von Hand neu.

## Die obere Leiste prüft die IP; IPv6 und DNS prüfen Sie getrennt

Die obere Leiste schaut auf die IPv4-Adresse der Verbindung, die bei unserer Website angekommen ist. Zeigt sie das Richtige, heißt das nur, dass dieser Browser beim Besuch unserer Website über das VPN lief:

- **IPv6 und DNS sehen Sie daran nicht.** Besucht der Browser unsere Website über IPv6, wird das Feld einfach nicht angezeigt; es gibt kein falsches Netz als das echte aus. Zeigt eine Videoseite weiterhin einen Urheberrechtshinweis, umgehen höchstwahrscheinlich IPv6 oder DNS das VPN; siehe [03 · IPv6 und DNS schlüpfen durch](03-ipv6-and-dns-leak.md).
- **Apps speichern ihre Regionsprüfung zwischen.** Die obere Leiste wird jedes Mal frisch abgefragt und ist von Zwischenspeichern nicht betroffen; Video- und Musik-Apps merken sich aber die vorige Region. Beenden Sie sie vollständig und öffnen Sie sie erneut; siehe [02 · Mit China verbunden, aber trotzdem kein Video](02-still-blocked-after-connecting.md).

## Häufige Fragen

**Das Feld „Aktuelles Netzwerk“ in der oberen Leiste ist verschwunden?** Melden Sie sich am Computer zuerst an. Erscheint es auch nach der Anmeldung nicht, lief diese Verbindung höchstwahrscheinlich über IPv6, oder sie lässt sich im Moment nicht abfragen; warten Sie zehn bis zwanzig Sekunden oder laden Sie neu. Lieber zeigt es nichts als etwas Falsches.

**Gleiche Region, aber bei zwei Verbindungen eine andere IP?** Normal. Hinter einer Region stehen mehrere Maschinen, und jede Verbindung nimmt die in diesem Moment am wenigsten ausgelastete. Eine bestehende Verbindung wird nicht mittendrin woanders hin verlegt.

**Die angezeigte Provinz ist nicht die erwartete?** Die obere Leiste zeigt die Provinz bzw. den Bundesstaat, in dem die Ausgangs-IP liegt, und ist nur bis zu dieser Ebene genau. Stimmt die Flagge, liegt der Ausgang im gewählten Land bzw. in der gewählten Region.

**Was soll ich dem Support melden?** Fahren Sie mit der Maus über das Feld in der oberen Leiste und schicken Sie, was im Popup erscheint (einschließlich Ausgangs-IP), zusammen mit Verbindungsart, gewählter Region und dem Zeitpunkt des Problems.

## Weiterlesen

- [Keine Verbindung, langsam, Abbrüche: so gehen Sie vor](https://www.leotun.com/de/guides/connect-issues?utm_source=github&utm_content=troubleshooting-08)
- [Welche Region aus China am schnellsten ist](https://www.leotun.com/de/guides/pick-region?utm_source=github&utm_content=troubleshooting-08)
- [Für welche Situationen jede Verbindungsart passt](https://www.leotun.com/de/guides/choose-connection?utm_source=github&utm_content=troubleshooting-08)
- [Was der Web-Proxy ist und wann Sie ihn nutzen](https://www.leotun.com/de/guides/web-proxy?utm_source=github&utm_content=troubleshooting-08)
- [Was die Router-Firmware kann](https://www.leotun.com/de/guides/router-firmware?utm_source=github&utm_content=troubleshooting-08)
- [Was tun, wenn Tencent Video im Ausland einen Urheberrechtshinweis zeigt](https://www.leotun.com/de/guides/overseas-video?utm_source=github&utm_content=troubleshooting-08)

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=troubleshooting-08)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=troubleshooting-08) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

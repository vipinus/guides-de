# 04 · Am Firmenrechner: ohne Adminrechte, Firmen-VPN läuft schon

Ein Firmenrechner hat drei Einschränkungen: Sie dürfen keine nicht freigegebene Software installieren, Sie haben keine Administratorrechte, und oft ist er schon mit dem Firmen-VPN verbunden. Ein VPN für das ganze Gerät lässt sich hier entweder gar nicht installieren oder gerät mit dem Firmen-VPN aneinander. Das richtige Werkzeug ist der Web-Proxy – eine Browsererweiterung, die nur die Anfragen dieses Browsers über die Leitung schickt, während Firmenintranet, E-Mail-Programm und Firmen-VPN genau so bleiben, wie sie sind; Administratorrechte brauchen Sie nicht. Dieser Artikel erklärt, wie Sie ihn einrichten, was er kann, was Sie lassen sollten und wie Sie mit den IT-Richtlinien der Firma auskommen.

## Warum der Web-Proxy

- Kein Client zu installieren: Es ist nur eine Browsererweiterung, und die meisten Firmen erlauben Erweiterungen, aber keine Software.
- Keine Administratorrechte: Die Erweiterung läuft im Benutzerkontext und ändert die Netzwerkeinstellungen des Systems nicht.
- Verträgt sich mit dem Firmen-VPN: Das Firmen-VPN übernimmt die Systemrouten, der Web-Proxy sitzt nur auf Browserebene, die beiden stören sich also nicht; Intranetseiten der Firma laufen weiter über das Firmen-VPN.
- Konstruktionsbedingt keine Verbindung, die abbrechen kann: Der Proxy arbeitet pro Anfrage ohne dauerhafte Verbindung, sodass Sie auch Schwankungen im Firmennetz nicht bemerken.

## In zwei Schritten eingerichtet

1. Installieren Sie im Browser die Erweiterung ZeroOmega (die Fortsetzung von SwitchyOmega); auf der Seite Web-Proxy unserer Website finden Sie den Installationslink für jeden Browser.
2. Melden Sie sich auf unserer Website an, klicken Sie auf der Seite Web-Proxy auf „Wiederherstellungslink der Erweiterung kopieren“ und fügen Sie ihn in der Erweiterung unter „Import/Export“ → „Restore from online“ (online wiederherstellen) ein. Regionen und Adressen werden in einem Rutsch importiert; danach klicken Sie auf das Erweiterungssymbol, wählen eine Region und geben im Anmeldefenster des Browsers Konto und Passwort unserer Website ein.
3. Wir empfehlen ein eigenes Browserprofil (oder einen anderen Browser) nur für den Proxy, während der Arbeitsbrowser lokal bleibt – so vermischt sich nichts.

## Wofür er taugt und wann Sie eine andere Verbindungsart brauchen

- Ja: Nachschlagen, Google, GitHub, Stack Overflow, ausländische Dokumentationsseiten, die Webversion von ChatGPT und Webmail.
- Andere Verbindungsart: Video-Apps, Desktopprogramme und Kommandozeilen-Tools nutzen die Proxyeinstellungen des Browsers standardmäßig nicht (für die Kommandozeile können Sie die Proxyadresse in die Umgebungsvariable http_proxy eintragen; siehe den Linux-Artikel).
- Andere Verbindungsart: chinesische Videoseiten schauen (für Nutzer im Ausland) – Videoseiten prüfen auch IPv6 und DNS, die der Web-Proxy nicht abdeckt; dafür brauchen Sie ein VPN für das ganze Gerät.

## Mit den IT-Richtlinien auskommen

Alles auf einem Firmenrechner kann von der Firma überprüft werden, Erweiterungen eingeschlossen. Lesen Sie zuerst die Nutzungsrichtlinie der Firma: Die meisten Firmen verbieten nicht freigegebene Software und das Umgehen von Sicherheitsrichtlinien; eine Browsererweiterung, die externe Websites aufruft, liegt meist in einer Grauzone. Sind Sie unsicher, fragen Sie die IT.

Installieren Sie auf einem Firmenrechner kein VPN für das ganze Gerät (Cisco, Privat, Hiddify), um Firmenrichtlinien zu umgehen: Diese ändern die Systemrouten, lösen Alarme in der Endpoint-Management-Software aus und tragen außerdem Intranetverkehr der Firma nach draußen. Der Web-Proxy betrifft nur einen Browser und birgt das geringste Risiko.

Halten Sie Arbeits- und Privatkonten getrennt: Melden Sie sich im Browser mit Proxy nicht bei Firmenkonten an und im Firmenbrowser nicht bei privaten Konten.

## Häufige Fragen

**Was, wenn die Firma das Installieren von Erweiterungen verbietet?** Dann nutzen Sie Ihr eigenes Smartphone oder Ihren privaten Computer. Umgehen Sie die Kontrollen nicht mit portabler Software unklarer Herkunft.

**Sieht die Erweiterung meinen Intranetverkehr?** Nein. Nach den Split-Routing-Regeln verbinden sich Intranet-Domains der Firma direkt und laufen nicht über den Proxy; im globalen Modus werden sie lediglich an den Proxyserver und zurück geschickt, und der Proxy sieht den Domainnamen, nicht den Inhalt. Sicherheitshalber geben Sie dem Proxy ein eigenes Browserprofil.

**Funktioniert der Proxy, während das Firmen-VPN läuft?** Ja, die beiden kommen sich nicht in die Quere. Sehr wenige Firmen-VPNs zwingen den gesamten Verkehr über den Firmenausgang und deaktivieren Proxyeinstellungen; dann meldet die Erweiterung, dass sie nicht verbinden kann, und die einzige Möglichkeit ist, das Firmen-VPN auszuschalten.

**Ist es auf einem Firmen-Mac genauso?** Genauso; die Erweiterungen für Chrome, Edge und Firefox gibt es alle auch für den Mac. Für Safari gibt es diese Erweiterung nicht, nehmen Sie also einen anderen Browser.

## Weiterlesen

- [Seite Web-Proxy: Erweiterung installieren und Wiederherstellungslink](https://www.leotun.com/de/httpproxy?utm_source=github&utm_content=overseas-access-04)
- [Was ein Web-Proxy ist und wann er sich eignet](https://www.leotun.com/de/guides/web-proxy?utm_source=github&utm_content=overseas-access-04)
- [Linux-Server und Kommandozeilen-Tools über die Leitung schicken](https://www.leotun.com/de/guides/linux-server?utm_source=github&utm_content=overseas-access-04)
- [Welche Verbindungsart zu welcher Situation passt](https://www.leotun.com/de/guides/choose-connection?utm_source=github&utm_content=overseas-access-04)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/office-laptop?utm_source=github&utm_content=overseas-access-04

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=overseas-access-04)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=overseas-access-04) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

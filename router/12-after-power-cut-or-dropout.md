# 12 · Erholt sich der Router nach einem Stromausfall oder Verbindungsabbruch von selbst?

Wer schon einmal einen selbst gebastelten VPN-Router betrieben hat, kennt das vermutlich: ein Stromausfall oder eine kurze Störung des Internetanschlusses, und nach dem Neustart sieht alles normal aus – nur der Tunnel kommt nicht zurück, bis Sie in der Verwaltungsoberfläche alles neu einrichten.

## Die kurze Antwort

Ja, er erholt sich von selbst. Nach einem Stromausfall mit Neustart, einem Abbruch des Internetanschlusses oder wenn der Tunnel mitten in der Nutzung abreißt, verbindet sich die Firmware selbstständig neu. Sie müssen weder die Verwaltungsoberfläche öffnen noch sich erneut anmelden.

## Wie das funktioniert

Die Firmware lässt ständig eine Prüfung laufen, die etwa alle halbe Minute nach dem Tunnel sieht. Stellt sie fest, dass er unterbrochen ist, verbindet sie neu und stellt das Split-Routing wieder her.

In der kurzen Lücke, bis der Tunnel wieder steht, funktionieren chinesische Websites weiter. Der Haushalt verliert also nicht das Internet, nur weil der Tunnel noch nicht aufgebaut ist.

Auch Ihre Einstellungen bleiben erhalten: Region, Split-Routing-Modus und der Schalter „Automatically pick the fastest line“ (automatisch die schnellste Leitung wählen) überstehen jeden Neustart und jede Neuverbindung. Haben Sie das Split-Routing ausgeschaltet, bleibt es ausgeschaltet.

## Was in welchem Fall passiert

| Was passiert ist | Danach |
|---|---|
| Der Strom kommt nach einem Ausfall zurück | Der Router startet, und der Tunnel verbindet sich von selbst |
| Der Internetanschluss fällt aus und kommt zurück | Der Tunnel verbindet sich, sobald die Leitung wieder da ist |
| Der Tunnel reißt mitten in der Nutzung ab | Die Prüfung bemerkt es und verbindet neu |
| Das Konto läuft ab | Der Datenverkehr geht nicht mehr durch den Tunnel, das Heimnetz läuft weiter. Nach der Verlängerung geht es von selbst weiter, ohne erneute Anmeldung |
| Wir ändern eine Serveradresse | Der Router zieht automatisch nach. Sie müssen nichts neu einstellen |

## Nach ein paar Minuten immer noch nicht zurück? Prüfen Sie Folgendes

1. **Funktioniert der Internetanschluss selbst?** Öffnen Sie eine chinesische Website. Klappt das nicht, liegt das Problem an der Leitung oder am Modem, nicht am Tunnel.
2. **Ist das Konto abgelaufen?** Nach Ablauf verbindet der Tunnel nicht. Melden Sie sich auf der Website an und schauen Sie nach.
3. **Probieren Sie eine andere Region.** Wechseln Sie die Region in der Verwaltungsoberfläche. Manchmal hat eine Region vorübergehend ein Problem.
4. **Starten Sie den Router neu.** Ziehen Sie den Stecker, warten Sie zehn Sekunden und stecken Sie ihn wieder ein.
5. Hilft all das nicht, schicken Sie dem Support einen Screenshot des Status in der Verwaltungsoberfläche.

## Der allererste Start nach dem Flashen

Der erste Start dauert länger als sonst: Die Firmware sucht nach Komponenten-Updates und erkennt das Land, um die Sendeleistung des WLANs einzustellen. **Schließen Sie für diesen ersten Start ein Netzwerkkabel an.** Schwaches WLAN, solange der Router noch nie online war, ist normal.

## Häufige Fragen

**Taugt er für Gegenden mit häufigen Stromausfällen?** Ja. Er verbindet sich jedes Mal neu, wenn der Strom zurückkommt.

**Muss ich den Router regelmäßig neu starten?** Nein.

**Unterbrechen Komponenten-Updates meine Verbindung?** Nein. Updates werden beim Start gesucht und heruntergeladen und greifen erst beim nächsten Start. Der Router startet nicht mitten in der Nutzung neu.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=router-12)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=router-12) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

# 06 · Was tun, wenn der Mac meldet, die App sei „beschädigt“

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-06

Zuerst das Ergebnis: Die Datei ist nicht kaputt, und niemand hat sie manipuliert. Zeigt ein Doppelklick auf Hiddify am Mac „ist beschädigt und kann nicht geöffnet werden“ oder „Entwickler kann nicht überprüft werden“, blockiert sie Gatekeeper, die Schutzfunktion des Systems; mit den Schritten unten lassen Sie sie zu.

Die Installation von Hiddify unter Windows löst in unseren aktuellen Tests keine Virenwarnung mehr aus. Schlägt Ihr installiertes Antivirenprogramm trotzdem an, gehen Sie in derselben Reihenfolge wie hier vor: erst prüfen, dann zulassen.

## Warum sie blockiert wird

**Dateien, die von einer Webseite heruntergeladen werden, erhalten eine Quarantäne-Markierung.** Sieht Gatekeeper unter macOS diese Markierung, blockiert es die App. Die Meldung lautet mal „ist beschädigt“, mal „Entwickler kann nicht überprüft werden“; die Ursache ist dieselbe.

Was wir tun: Der Desktop-Client ist ein **unveränderter Spiegel** des Release-Pakets des Open-Source-Originalprojekts. Wir verändern es nicht, packen es nicht neu und fügen nichts ein; wir stellen es nur auf unserer eigenen Download-Seite bereit, damit das Herunterladen leichter ist.

## Prüfen Sie zuerst selbst – lassen Sie nichts blind zu

Eine App zuzulassen heißt, dass das System sie nicht mehr prüft. Darum gilt: erst prüfen, dann zulassen.

**Laden Sie sie zur Gegenprüfung bei VirusTotal hoch.** Ziehen Sie das Installationsprogramm auf [virustotal.com](https://virustotal.com/gui/home/upload). Schlagen einige heuristische Engines an, während die großen Hersteller alle grünes Licht geben, ist das das typische Muster eines Fehlalarms. Schlagen die meisten großen Engines an, **installieren Sie es nicht** – kommen Sie direkt zu uns.

Machen Sie erst weiter, wenn die Prüfung bestanden ist. Sind Sie unsicher, wenden Sie sich zuerst an den Support, und wir prüfen die Download-Seite.

## Drei Wege zum Zulassen, vom engsten zum weitesten

Nach dem Doppelklick sehen Sie womöglich „„Name des Clients“ ist beschädigt und kann nicht geöffnet werden. Du solltest es in den Papierkorb legen.“ oder „kann nicht geöffnet werden, da der Entwickler nicht überprüft werden kann“. Die drei Schritte unten gehen vom engsten zum weitesten; **klappt der erste, nutzen Sie nicht den dritten**.

1. Suchen Sie die App im Finder unter „Programme“, klicken Sie bei gedrückter ctrl-Taste auf das Symbol (oder mit der rechten Maustaste), wählen Sie „Öffnen“ und klicken Sie im erscheinenden Dialog noch einmal auf „Öffnen“. Das ist eine einmalige Erlaubnis nur für diese eine App.
2. Bietet das Kontextmenü kein brauchbares „Öffnen“, gehen Sie zu „Systemeinstellungen“ → „Datenschutz & Sicherheit“ und scrollen nach unten zum Abschnitt „Sicherheit“. Dort sehen Sie „„Name des Clients“ wurde blockiert, da es nicht von einem verifizierten Entwickler stammt“. Klicken Sie rechts auf „Trotzdem öffnen“ und bestätigen Sie mit Ihrem Passwort.
3. Lautet die Meldung „ist beschädigt“, helfen die ersten beiden Schritte meist nicht. Öffnen Sie das „Terminal“ und führen Sie `sudo xattr -dr com.apple.quarantine` gefolgt vom Pfad der App aus (meist eine `.app` unter `/Applications/`), drücken Sie die Eingabetaste, geben Sie Ihr Anmeldepasswort ein und öffnen Sie die App erneut. Der Befehl entfernt die Quarantäne-Markierung, die die Download-Herkunft kennzeichnet.

Beim ersten Start fragt das System außerdem nach Ihrem Passwort, um die Installation einer Netzwerkerweiterung zu erlauben. Erst wenn Sie zustimmen, kann die App den Datenverkehr übernehmen.

Einige Hinweise:

- Nutzen Sie den Befehl `xattr` **nur für Dateien, deren Herkunft Sie bereits geprüft haben**; wie das geht, steht im vorigen Abschnitt.
- Schalten Sie Gatekeeper **nicht** mit `sudo spctl --master-disable` global ab. Das deaktiviert den Schutz für den ganzen Rechner, während Rechtsklick → Öffnen nur eine App betrifft.
- Seit macOS 15 hat Apple den Weg über Rechtsklick → Öffnen verschärft; meist müssen Sie über den Schritt „Systemeinstellungen“ gehen. Das ist eine Änderung im Systemverhalten, kein Problem mit unserem Paket.
- Firmen-Macs werden oft über ein MDM-Profil verwaltet, und alle drei Schritte oben können gesperrt sein. Erzwingen Sie nichts; nehmen Sie eine der drei Möglichkeiten unten.

## Sie möchten nichts zulassen? Nehmen Sie eine dieser drei

Ihre Clients **laufen unter macOS per Doppelklick** und zeigen keine der Meldungen oben. Es ist dasselbe Konto, ohne Aufpreis:

- **Privat (offizieller Tailscale-Client)**: läuft direkt nach der Installation, eignet sich zum dauerhaften Eingeschaltetlassen
- **OpenVPN Connect**: das eigene Installationsprogramm von OpenVPN; einfach die Konfiguration importieren
- **Cisco Secure Client**: ein Client für Unternehmen, auf vielen Firmenrechnern bereits installiert

## Häufige Fragen

**Enthält Ihr Programm tatsächlich einen Virus?**
Nein. Es ist ein unveränderter Spiegel des offiziellen Release-Pakets des Open-Source-Originalprojekts. Sie sollten uns aber nicht einfach beim Wort nehmen; wie Sie selbst prüfen, steht oben: Laden Sie es bei VirusTotal hoch und sehen Sie sich an, wie sich die Urteile der Engines verteilen.

**Wird es unter Windows weiterhin gemeldet?**
Derzeit meldet die in Windows integrierte Sicherheitszentrale in unseren Tests die Hiddify-Installation nicht mehr. Schlägt Ihr installiertes Antivirenprogramm trotzdem an, laden Sie es zuerst zur Gegenprüfung bei VirusTotal hoch und setzen Sie nach bestandener Prüfung das Installationsverzeichnis von Hiddify im Antivirenprogramm auf vertrauenswürdig. Schalten Sie für die Installation nicht den Echtzeitschutz aus.

**Nach der Installation auf dem Mac öffnet es sich nicht. War der Download beschädigt?**
Nein. Es öffnet sich nicht, weil Gatekeeper es blockiert. Gehen Sie mit den drei Wegen zum Zulassen oben vor.

**Sollte ich dazu Antivirensoftware auf dem Mac installieren?**
Nein. Was Sie unter macOS blockiert, ist der systemeigene Gatekeeper, keine Antivirensoftware. Antivirensoftware von Drittanbietern lässt diese Meldung nicht verschwinden und kann neue Blockaden hinzufügen.

**Tritt das Problem auch auf Smartphones auf?**
Unter iOS gibt es das Problem bei Installation aus dem App Store nicht. Android warnt gelegentlich vor unbekannten Quellen; lassen Sie es einfach zu.

---

Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=troubleshooting-06)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=troubleshooting-06) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

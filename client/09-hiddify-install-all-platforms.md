# 09 · Hiddify auf allen Plattformen installieren: Windows, macOS, Linux, Android, iOS

Der Client für den Bereich Hiddify auf unserer Website ist das quelloffene Hiddify mit eingebautem sing-box-Kern – nach der Installation müssen Sie nichts weiter konfigurieren. Auf allen fünf Plattformen ist es dieselbe App, aber die Hürden beim ersten Start unterscheiden sich: Unter Windows kann ein Virenscanner sie blockieren oder löschen, auf dem Mac heißt es womöglich, sie „ist beschädigt“, und zusätzlich müssen Sie eine Netzwerkerweiterung erlauben; unter Linux ist vor dem VPN-Modus ein Berechtigungsbefehl nötig, und auf dem iPhone ist sie im chinesischen App Store nicht zu finden. Dieser Artikel zeigt für jede Plattform, wo Sie die App laden, wie Sie sie installieren und was beim ersten Start zu tun ist – und zum Schluss die kürzesten Schritte, um ein Abo zu importieren und zu verbinden.

## Wo Sie die App herunterladen

| Plattform | Installationspaket | Bezugsquelle |
|---|---|---|
| Windows | Installer (.exe), nur x64 | Downloadbereich der Hiddify-Seite |
| macOS | .dmg, ein Paket für Apple Silicon und Intel | Downloadbereich der Hiddify-Seite |
| Linux | .deb (Debian-/Ubuntu-Familie), nur x64 | Downloadbereich der Hiddify-Seite |
| Android | .apk, in zwei Varianten: ARM64 und x86-64 | Downloadbereich der Hiddify-Seite oder Google Play |
| iPhone / iPad | Hiddify Proxy & VPN im App Store | App Store; Apple-ID außerhalb der Region China nötig |

Der Downloadbereich der Hiddify-Seite empfiehlt automatisch das Paket für Ihr aktuelles System; die Pakete für andere Systeme stehen darunter. Neben jeder Zeile gibt es außerdem ein Symbol „Offizielle Seite“, das auf die offizielle Release-Seite von Hiddify verweist – so können Sie die Versionen vergleichen. Für die drei Desktop-Systeme (Windows, macOS, Linux) gibt es auch Videoanleitungen.

Die Desktop-Installer sind unveränderte Spiegel der offiziellen Hiddify-Releases, weder bearbeitet noch neu verpackt. Bevor Sie eine Datei freigeben, können Sie sie selbst prüfen: Laden Sie den Installer bei VirusTotal hoch und sehen Sie sich das Ergebnis an; wie das geht, steht in [Fehlerbehebung 06](../troubleshooting/06-antivirus-false-positive.md).

## Windows

1. Laden Sie den Installer im Downloadbereich der Hiddify-Seite herunter und installieren Sie ihn per Doppelklick. (In unseren aktuellen Tests schlägt die Windows-Sicherheit nicht an; meldet ihn Ihr installierter Virenscanner, lesen Sie die FAQ am Ende von [Fehlerbehebung 06](../troubleshooting/06-antivirus-false-positive.md).)

## macOS

1. Laden Sie die .dmg im Downloadbereich der Hiddify-Seite herunter, öffnen Sie sie und ziehen Sie Hiddify in „Programme“.
2. Klicken Sie im „Finder“ → „Programme“ mit gedrückter Ctrl-Taste auf das Hiddify-Symbol, wählen Sie „Öffnen“ und bestätigen Sie im Dialog noch einmal mit „Öffnen“.
3. Öffnet es sich immer noch nicht: „Systemeinstellungen“ → „Datenschutz & Sicherheit“, im Abschnitt „Sicherheit“ auf „Dennoch öffnen“ klicken und mit Ihrem Passwort bestätigen.
4. Heißt es, die App „ist beschädigt und kann nicht geöffnet werden“: Die Datei ist nicht beschädigt, sondern Gatekeeper blockiert sie. Öffnen Sie das „Terminal“, führen Sie den folgenden Befehl aus, drücken Sie die Eingabetaste, geben Sie Ihr Anmeldepasswort ein und öffnen Sie Hiddify erneut:

```bash
sudo xattr -dr com.apple.quarantine /Applications/Hiddify.app
```

Der Befehl entfernt nur die Quarantäne-Markierung, die die Datei als heruntergeladen kennzeichnet, und gilt nur für diese eine App. Verwenden Sie **nicht** `sudo spctl --master-disable`, um Gatekeeper für den ganzen Rechner abzuschalten.

Wenn Sie nach der Installation zum ersten Mal auf Verbinden klicken, verlangt das System außerdem, eine „Netzwerkerweiterung“ zu erlauben. Überspringen Sie diesen Schritt, dreht sich das Symbol endlos und die Verbindung kommt nie zustande:

- **Ab macOS 15 Sequoia**: „Systemeinstellungen“ → „Allgemein“ → „Anmeldeobjekte & Erweiterungen“, ganz unten zu „Erweiterungen“ scrollen, die Ansicht auf „Nach Kategorie“ umstellen, auf das ⓘ neben „Netzwerkerweiterungen“ klicken, den Schalter für Hiddify einschalten und bei Nachfrage Passwort oder Fingerabdruck verwenden.
- **macOS 13 Ventura / 14 Sonoma**: Starten Sie zuerst Hiddify und klicken Sie einmal auf Verbinden; es erscheint „Systemerweiterung blockiert“. Gehen Sie dann zu „Systemeinstellungen“ → „Datenschutz & Sicherheit“, scrollen Sie zu „Das Laden der Systemsoftware vom Entwickler … wurde blockiert“, klicken Sie auf „Erlauben“ und geben Sie Ihr Passwort ein.

Sind diese Schaltflächen auf einem Firmen-Mac ausgegraut, hat eine Geräteverwaltungsrichtlinie sie gesperrt; fragen Sie die IT oder nutzen Sie stattdessen die Clients für Cisco, OpenVPN oder das private Netzwerk.

## Linux

1. Laden Sie die .deb im Downloadbereich der Hiddify-Seite herunter und installieren Sie sie per Doppelklick über die Softwareverwaltung, oder öffnen Sie im Download-Verzeichnis ein Terminal und führen Sie aus (Debian, Ubuntu und Derivate):

```bash
sudo apt install ./downloaded-file-name.deb
```

2. Verbinden Sie direkt nach der Installation, erscheint „operation not permitted“ und der VPN-Modus startet nicht, weil das offizielle deb nach der Installation diese Berechtigung nicht hat. Öffnen Sie ein Terminal, erteilen Sie Hiddify mit dem folgenden Befehl die Berechtigung und starten Sie Hiddify neu:

```bash
echo /usr/share/hiddify/lib | sudo tee /etc/ld.so.conf.d/hiddify.conf && sudo ldconfig && sudo setcap cap_net_admin,cap_net_raw+ep /usr/share/hiddify/hiddify
```

3. **Nach jedem Hiddify-Update erneut ausführen**: Die Berechtigung hängt an der Programmdatei, ein Update ersetzt die Datei, und damit ist die Berechtigung weg.

Das deb-Paket ist x64; auf ARM-Linux-Geräten nutzen Sie OpenVPN – mit demselben Konto.

## Android

1. Laden Sie die .apk im Downloadbereich der Hiddify-Seite herunter. Die Seite empfiehlt automatisch die passende Architektur; die allermeisten Smartphones sind ARM64. Wenn Sie Google Play nutzen können, installieren Sie die App auch direkt aus dem Store.
2. Erscheint bei der Installation ein Hinweis zu „unbekannten Quellen“ oder eine Warnung einer Sicherheits-App, erlauben Sie die Installation.
3. Beim ersten Tippen auf Verbinden fragt das System nach der VPN-Berechtigung; tippen Sie auf Zulassen.

## iPhone / iPad

1. Suchen Sie im App Store nach „Hiddify“ und installieren Sie die App; sie ist kostenlos.
2. Finden Sie sie nicht oder sehen Sie „Diese App ist in deinem Land oder deiner Region derzeit nicht verfügbar“: Unter iOS installieren Sie aus dem App Store mit einer Apple-ID, die nicht der Region China zugeordnet ist (Hiddify gibt es in den Stores der USA, Hongkongs, Taiwans, Japans und Singapurs). Wir empfehlen, eine neue anzulegen: Im App Store bei einer beliebigen Gratis-App auf „Laden“ tippen → „Neue Apple-ID erstellen“, eine Region wie Hongkong oder die USA wählen und als Zahlungsmethode „Keine“ einstellen. Das Konto wechseln Sie nur im App Store, iCloud bleibt unberührt. Alle Schritte finden Sie in [06 · Was tun, wenn iOS eine App nicht installieren lässt](06-ios-app-store.md).
3. Beim ersten Tippen auf Verbinden fragt das System nach der VPN-Berechtigung; tippen Sie auf Erlauben.

Verwenden Sie **keine** Apple-ID, die Ihnen jemand anderes überlässt – damit kann Ihr Gerät aus der Ferne gesperrt werden.

## Nach der Installation: Abo importieren und verbinden

1. Melden Sie sich auf der Website an und öffnen Sie die Hiddify-Seite.
2. Klicken Sie auf die Flagge der gewünschten Region, dann erscheint ein QR-Code; oder klicken Sie oben auf der Seite auf „Alle Regionen importieren · automatisch wählen“, um alle Regionen außerhalb Chinas auf einmal zu importieren und den Client automatisch wählen zu lassen. **Die Region China importieren Sie separat**: Wollen Sie aus dem Ausland chinesische Videos sehen oder chinesisches Onlinebanking nutzen, klicken Sie auf die chinesische Flagge.
3. Unter dem QR-Code stehen drei Schaltflächen, nach Abo-Typ gruppiert. Hiddify nutzt die erste (sie zeigt Hiddify / sing-box / GUI.for.SingBox / Karing mit dem Untertitel „sing-box-Abonnement“), auf Smartphone und Computer dieselbe Schaltfläche. Smartphone: antippen, zu Hiddify wechseln und wie angezeigt hinzufügen – oder den Code mit Hiddify auf einem anderen Gerät scannen. Computer: anklicken, um eine https://-Adresse zu kopieren, dann in Hiddify auf „+“ → „Add from clipboard“ (aus der Zwischenablage hinzufügen) klicken.
4. Klicken Sie auf Verbinden.

Den Unterschied der drei Schaltflächen, den Import in Clash und andere Clients und die Frage, ob ein Abo abläuft, erklärt [02 · So importieren Sie einen Abo-Link (Hiddify, Clash, Shadowrocket)](02-singbox-subscription-links.md). Ist alles importiert, aber es verbindet nicht, siehe [Fehlerbehebung 04](../troubleshooting/04-singbox-import-not-connecting.md).

## Häufige Fragen

**Haben Sie die Installer verändert?** Nein. Die Desktop-Installer sind unveränderte Spiegel der offiziellen Hiddify-Releases. Jede Zeile auf der Hiddify-Seite verlinkt die offizielle Release-Seite, sodass Sie die Versionen selbst vergleichen können; zur Sicherheit können Sie die Datei auch bei VirusTotal hochladen.


**Ich habe auf dem Mac den xattr-Befehl schon ausgeführt, und es verbindet trotzdem nicht?** Höchstwahrscheinlich ist die „Netzwerkerweiterung“ noch nicht erlaubt; folgen Sie dem macOS-Abschnitt oben und schalten Sie in den Systemeinstellungen den Schalter für Hiddify ein.

**Nach einem Hiddify-Update unter Linux funktioniert der VPN-Modus wieder nicht?** Das ist normal; führen Sie den Berechtigungsbefehl nach dem Update noch einmal aus.

**Funktioniert es auf Windows- oder Linux-Rechnern mit ARM?** Ja, mit einer anderen Zugangsart wie OpenVPN und demselben Konto; die Desktop-Pakete von Hiddify gibt es derzeit nur für x64.

**Keine Lust auf das Freigeben?** Cisco (Cisco Secure Client), OpenVPN (OpenVPN Connect) und das private Netzwerk (Tailscale) starten per Doppelklick, werden von Virenscannern nicht gemeldet, der Mac hält sie nicht für „beschädigt“ – und das Konto ist dasselbe.

## Weiterlesen

- [Hiddify-Seite: Client-Downloads und QR-Codes für jede Region](https://www.leotun.com/de/singbox?utm_source=github&utm_content=client-09)
- [So importieren Sie einen Abo-Link (Hiddify, Clash, Shadowrocket)](https://www.leotun.com/de/guides/singbox-subscription?utm_source=github&utm_content=client-09)
- [Client vom Virenscanner gemeldet / Mac sagt „beschädigt“: erst prüfen, dann freigeben](https://www.leotun.com/de/guides/antivirus-false-positive?utm_source=github&utm_content=client-09)
- [Was die „Netzwerkerweiterung“ unter macOS ist und wie Sie sie erlauben](https://www.leotun.com/de/guides/macos-network-extension?utm_source=github&utm_content=client-09)
- [Was tun, wenn iOS eine App nicht installieren lässt](https://www.leotun.com/de/guides/ios-app-store?utm_source=github&utm_content=client-09)

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=client-09)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-09) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

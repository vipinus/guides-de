# 05 · Riskante VPN-Software erkennen

Ihr gesamter Datenverkehr geht durch die Hände einer VPN-App, und sie kann sich ansehen, was sie will. Zwei Arten verdienen besondere Vorsicht: zum einen das, was in der Szene „rotes VPN“ heißt – mit staatlichem Hintergrund, das im Namen der Compliance Ihre echte Identität verlangt und die Aufzeichnungen weitergibt; zum anderen kostenlose „Beschleuniger“ unbekannter Herkunft, die mit Ihren Daten, Ihrem Gerät oder etwas Eingeschleustem Geld verdienen. Beide haben gemeinsam, dass „sie im Alltag tadellos funktionieren“; das Problem liegt dort, wo Sie nicht hinsehen. Unten finden Sie zehn Warnsignale, die Sie selbst prüfen können, was zu tun ist, wenn Sie schon so etwas installiert haben, und einen Selbsttest in drei Minuten.

## Warum VPN-Software riskanter ist als eine gewöhnliche App

Ein VPN arbeitet auf Systemebene: Es bekommt den Datenverkehr jedes Programms auf dem Gerät, auch von solchen, von denen Sie nicht wissen, dass sie im Hintergrund laufen. Eine gewöhnliche App gibt die Daten preis, die sie selbst gesammelt hat; ein VPN gibt alles preis, was Sie auf diesem Gerät tun. Der Maßstab für VPN-Software muss deshalb viel strenger sein als für eine gewöhnliche App.

„Ich habe es benutzt, und nichts ist passiert“ beweist keine Sicherheit. Aufzeichnen, Weitergeben und Einschleusen geschehen auf der Serverseite oder im Hintergrund und sind für Nutzer nicht spürbar; geht etwas schief, dann oft erst Monate später, und es lässt sich nicht mehr zurückverfolgen, welche Software es war.

## Zehn Warnsignale

- Unbekannte Herkunft: Das Installationsprogramm kommt über einen Gruppenchat, einen Cloud-Speicher oder einen QR-Code, ohne offizielle Website oder App-Store-Seite. Ein seriöser Client kommt entweder aus einem App Store, von der offiziellen Website des Entwicklers oder von einer Release-Seite, auf der sich die Signatur prüfen lässt.
- Verlangt die Installation eines Root-Zertifikats: Bei der Installation sollen Sie „dem Zertifikat vertrauen“ oder „das Profil installieren“ und einer Zertifizierungsstelle (CA) vertrauen. Ist das Root-Zertifikat installiert, kann sie Ihren gesamten HTTPS-Datenverkehr öffnen, einschließlich Onlinebanking und E-Mail. Ein normales VPN braucht diesen Schritt nicht.
- Zu viele Berechtigungen: Ein VPN verlangt Zugriff auf Kontakte, SMS, Anrufliste, genauen Standort und Fotomediathek. Ein VPN braucht nur die Berechtigung, einen Tunnel aufzubauen; mit dem Rest kann es nichts anfangen.
- Verlangt Klarnamen-Registrierung: Für die Anmeldung braucht es einen Personalausweis, einen Gesichtsscan oder die Bindung an eine Mobilnummer aus Festlandchina. So verknüpft ein sogenanntes konformes VPN Ihre Identität mit Ihren Verkehrsdaten; ein seriöser Dienst braucht nur eine E-Mail-Adresse.
- Proprietäres Protokoll + Closed-Source-Client: Sie können nur die eigene App nutzen, und sie unterstützt kein Standardprotokoll (AnyConnect, OpenVPN, WireGuard, Hiddify) – Sie können also mit keinem Open-Source-Client eines Dritten prüfen, was sie tatsächlich überträgt.
- Kostenlos, ohne erkennbare Einnahmequelle: kein Bezahltarif, keine Werbung, keine Geschäftskunden, und trotzdem läuft es Jahr für Jahr. Ausgangsbandbreite in Festlandchina wird nach Verbrauch abgerechnet, und ein Dienst, der nichts verlangt, holt es sich immer anderswo zurück.
- Keine Firma, kein Support, keine Geschichte: Der Betreiber ist nicht auffindbar, es gibt niemanden zum Kontaktieren, die Domain ist weniger als ein Jahr alt, und Name und Fassade wechseln häufig.
- Ungewöhnlicher Hintergrundverkehr: Das Gerät lädt ständig hoch, auch wenn Sie es nicht benutzen, und Akku und Datenvolumen schwinden schnell. Möglicherweise dient Ihr Gerät als Ausgang für andere, oder Ihre Daten werden synchronisiert.
- Die Werbung betont „offiziell“, „registriert“, „legal und konform“ und deutet an, alles andere sei illegal: Das ist die typischste Masche eines „roten VPN“, und seine Konformität besteht aus Aufzeichnen und Weitergeben.
- Die Bewertungen im App Store sind einseitig, die Rezensionen klingen alle gleich, und die Zahl der Downloads passt nicht zur Zahl der Bewertungen: Sie sind gekauft.

## So prüfen Sie es

1. Schauen Sie auf das Protokoll: ob die offizielle Website angibt, welches Protokoll genutzt wird, und ob sich ein Client eines Drittanbieters verwenden lässt. Bei einem Dienst, mit dem Sie sich über Open-Source- oder Standard-Clients wie OpenVPN, AnyConnect, Hiddify und Tailscale verbinden können, können Sie selbst Pakete mitschneiden und sehen, was übertragen wird.
2. Schauen Sie auf die Berechtigungen: Prüfen Sie nach der Installation in den Systemeinstellungen, welche Berechtigungen angefordert wurden, schalten Sie alles außer VPN ab und sehen Sie, ob es noch funktioniert. Wenn nicht, deinstallieren Sie es.
3. Schauen Sie auf die Zertifikate: iOS „Einstellungen“ → „Allgemein“ → „VPN und Geräteverwaltung“; Android „Einstellungen“ → „Sicherheit“ → „Verschlüsselung und Anmeldedaten“ → „Vertrauenswürdige Anmeldedaten“ → „Nutzer“; unter Windows „Vertrauenswürdige Stammzertifizierungsstellen“ in der Zertifikatverwaltung. Finden Sie ein Zertifikat, das sie installiert hat, löschen Sie es und deinstallieren Sie die App.
4. Prüfen Sie auf Lecks: Öffnen Sie nach dem Verbinden einen DNS-Leak-Test und eine IPv6-Testseite und sehen Sie nach, ob Namensauflösung und Adresse beide über die Server des Dienstes laufen; öffnen Sie dann eine HTTPS-Website und prüfen Sie, ob der Aussteller des Zertifikats die ursprüngliche CA ist.
5. Prüfen Sie den Betreiber: ob die offizielle Website die Firma oder das Team vorstellt, wie viele Jahre der Dienst schon läuft und wo der Support sitzt; ob Erstattungsregeln schriftlich festgehalten sind; ob die Datenschutzerklärung klar sagt, was aufgezeichnet wird.

## Was tun, wenn Sie so etwas schon installiert haben

1. Deinstallieren Sie die Software und prüfen Sie dann die oben genannten Stellen; löschen Sie die Zertifikate und Profile, die sie installiert hat.
2. Ändern Sie Passwörter: Onlinebanking, E-Mail, häufig genutzte Konten, vor allem jene, bei denen Sie sich während der Nutzung angemeldet haben.
3. Prüfen Sie bei Konten mit Zwei-Faktor-Authentifizierung den Anmeldeverlauf und entfernen Sie unbekannte Geräte.
4. War es auf einem Router installiert, setzen Sie ihn auf Werkseinstellungen zurück und flashen Sie dann offizielle oder vertrauenswürdige Firmware neu.

## Wie wir Ihnen die Prüfung ermöglichen

Alle LeoTun-Clients stammen von offiziellen Herstellern und bekannten Open-Source-Organisationen: Cisco, OpenVPN, Hiddify und Tailscale, unverändert gespiegelt, und Sie können die Kopie von unserer Website jederzeit durch den offiziellen bzw. Open-Source-Client ersetzen. Die Protokolle sind durchweg Standardprotokolle und lassen sich per Paketmitschnitt prüfen.

Für die Registrierung genügt eine E-Mail-Adresse, ohne Telefonnummer und ohne Ausweis. Wir speichern nur, was für die Abrechnung nötig ist; wir zeichnen nicht auf, was Sie aufrufen, schleusen keine Werbung ein und verkaufen keine Daten.

Wir installieren keine Zertifikate und fragen weder nach Kontakten noch nach Standort. Sollte Sie unser Client eines Tages auffordern, ein Root-Zertifikat zu installieren, sind das ganz sicher nicht wir.

## Häufige Fragen

**Ist alles Kostenlose unbrauchbar?** Die Clients aus der Open-Source-Community (OpenVPN, Hiddify, Tailscale) sind selbst kostenlos und vertrauenswürdig; das Risiko liegt bei einem „kostenlosen Dienst“, nicht bei „kostenloser Software“. Bei einem kostenlosen Dienst fragen Sie, wovon er lebt.

**Ist etwas sicher, weil es im App Store steht?** Die Aufnahme zeigt nur, dass es die automatische Prüfung des Stores bestanden hat; sie heißt nicht, dass auf der Serverseite nichts aufgezeichnet wird. Schauen Sie bei den zehn Warnsignalen oben auf Berechtigungen, Klarnamen-Registrierung, Protokoll und Betreiber; das prüft der Store nicht für Sie.

**Was ist ein sogenanntes „rotes VPN“?** So heißt in der Szene ein VPN mit staatlichem Hintergrund, das im Namen der Compliance eine Klarnamen-Registrierung verlangt und Aufzeichnungen aufbewahrt. Solche Dienste werben meist mit „offiziell“ und „legal“ und funktionieren im Alltag normal; das Problem ist, dass Ihre Identität und Ihr gesamter Datenverkehr miteinander verknüpft sind.

**Wie erkenne ich, ob ein VPN meine Inhalte aufgezeichnet hat?** Von der Nutzerseite aus gar nicht; Sie können nur darauf schauen, wie viele Prüfmöglichkeiten es Ihnen gibt: ob das Protokoll Standard ist, ob der Client Open Source ist, ob die Datenschutzerklärung konkret ist, ob sich der Betreiber nachschlagen lässt. Trifft keines der vier zu, gehen Sie davon aus, dass aufgezeichnet wird.

**Birgt Router-Firmware dasselbe Risiko?** Ja; „Firmware zum Umgehen der Firewall“ unbekannter Herkunft kann das ganze Heimnetz kapern. Flashen Sie nur offizielles OpenWrt oder Firmware, deren Quelle sich prüfen lässt; die Firmware unserer Website ist aus OpenWrt kompiliert, ergänzt nur um die Komponenten für die Verbindung zur Leitung und die Split-Routing-Regeln.

## Weiterlesen

- [Was uns von anderen VPNs unterscheidet](https://www.leotun.com/de/guides/why-us?utm_source=github&utm_content=network-05)
- [VPN für China: kostenlos oder kostenpflichtig](https://www.leotun.com/de/guides/free-vs-paid?utm_source=github&utm_content=network-05)
- [Was tun, wenn Tencent Video im Ausland Urheberrechtsbeschränkungen anzeigt](https://www.leotun.com/de/guides/overseas-video?utm_source=github&utm_content=network-05)
- [Über uns: wie es aufgebaut ist und was wir aufzeichnen](https://www.leotun.com/de/about?utm_source=github&utm_content=network-05)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/risky-vpn-apps?utm_source=github&utm_content=network-05

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=network-05)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=network-05) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

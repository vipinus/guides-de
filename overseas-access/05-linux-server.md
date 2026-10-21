# 05 · Linux-Server und Kommandozeilen-Tools über die Leitung schicken

Unter Linux führen zwei Wege auf die Leitung; wählen Sie nach Bedarf. Soll der ganze Rechner darüber laufen (Docker-Images ziehen, Dienste betreiben, die ein ausländisches Netz brauchen, unbeaufsichtigter Betrieb), nehmen Sie OpenVPN: eine Konfigurationsdatei in /etc/openvpn/client/ ablegen und beim Systemstart starten lassen. Sollen nur einige Befehle darüber laufen (git, pip, npm, curl), nehmen Sie den Web-Proxy: Proxy-Adresse in die Umgebungsvariable http_proxy eintragen, der übrige Datenverkehr bleibt unberührt. Auf Desktop-Linux können Sie die Konfiguration auch im NetworkManager importieren. Dieser Artikel behandelt alle drei Wege, samt Passwortdatei und Befehlen zur Überprüfung.

## Weg eins: der ganze Rechner über die Leitung (OpenVPN)

1. Client installieren: Debian / Ubuntu sudo apt install openvpn, Fedora sudo dnf install openvpn, Arch sudo pacman -S openvpn.
2. Melden Sie sich auf unserer Website an und klicken Sie auf der OpenVPN-Seite auf die Flagge einer Region, um die .ovpn herunterzuladen. Die Konfiguration für Linux enthält Konto und Passwort nicht (NetworkManager akzeptiert keine Dateien mit eingebetteten Zugangsdaten), legen Sie also eine eigene Passwortdatei an: zwei Zeilen, in der ersten Ihre E-Mail-Adresse für unsere Website, in der zweiten Ihr Passwort, chmod 600.
3. Kopieren Sie die .ovpn nach /etc/openvpn/client/<region>.conf und tragen Sie in der Datei hinter auth-user-pass den Pfad der Passwortdatei ein.
4. sudo systemctl enable --now openvpn-client@<region>. Den Status prüfen Sie mit systemctl status openvpn-client@<region>; kontrollieren Sie, dass curl -s https://ipinfo.io/country die gewählte Region zeigt.
5. Für eine andere Region laden Sie eine weitere Konfiguration herunter und aktivieren eine weitere Unit; lassen Sie immer nur eine laufen.

## Weg zwei: nur Kommandozeilen-Tools über die Leitung (Web-Proxy)

Die Proxy-Adresse von der Seite Web-Proxy unserer Website können Sie zusammen mit Konto und Passwort direkt in Umgebungsvariablen eintragen: export https_proxy=https://username:password@proxy-address export http_proxy=$https_proxy. Sonderzeichen im Passwort müssen URL-kodiert werden. Danach laufen curl, wget, git, pip und npm in diesem Terminal über die Leitung, andere Programme sind nicht betroffen.

Der Docker-Daemon liest keine Shell-Umgebungsvariablen; tragen Sie den Proxy unter Environment= in /etc/systemd/system/docker.service.d/proxy.conf ein und starten Sie docker neu. Für apt schreiben Sie Acquire::https::Proxy in /etc/apt/apt.conf.d/proxy.conf.

Auf diesem Weg gibt es konstruktionsbedingt keine Verbindung, die abreißen kann; er braucht kein root und ändert keine Routen. Er eignet sich für Firmenserver und für Fälle, in denen Sie nur Downloads beschleunigen wollen; er wirkt nur auf Programme, die die Proxy-Variablen beachten, der übrige Datenverkehr bleibt unberührt.

## Weg drei: NetworkManager auf Desktop-Linux

1. Installieren Sie network-manager-openvpn-gnome (ein Klick auf der OpenVPN-Seite unserer Website kann die Softwareverwaltung öffnen).
2. Einstellungen → Netzwerk → VPN → „+“ → „Aus Datei importieren“, die .ovpn wählen, E-Mail-Adresse und Passwort für unsere Website eingeben und speichern.
3. Das VPN schalten Sie über die obere Leiste oder das Benachrichtigungsfeld ein und aus. Für die automatische Verbindung beim Start setzen Sie in den Einstellungen der Kabel- bzw. WLAN-Verbindung das Häkchen bei „Automatisch mit VPN verbinden“.

## Überprüfen und Fehler suchen

- Ausgang prüfen: Das Land in curl -s https://ipinfo.io ist die gewählte Region.
- DNS prüfen: In resolvectl status sollte beim VPN-Interface der von der Leitung übermittelte DNS stehen; gibt es ein Leck, ergänzen Sie dhcp-option DNS in der Konfiguration oder nutzen Sie das Skript update-systemd-resolved.
- AUTH_FAILED: Die Passwortdatei stimmt nicht oder das Konto ist abgelaufen; haben Sie Ihr Passwort geändert, aktualisieren Sie die Passwortdatei.
- TLS handshake timeout: UDP zum Server kommt nicht durch; wechseln Sie Region oder Netz. Auf einem Cloud-Server muss die Sicherheitsgruppe ausgehendes UDP erlauben.
- Der Server steht in China und chinesische Quellen sollen direkt erreichbar bleiben: Sobald OpenVPN verbunden ist, läuft der gesamte ausgehende Verkehr über die Leitung. Stellen Sie die Quellen von apt / pip / npm auf chinesische Spiegel um, oder nutzen Sie stattdessen Weg zwei, damit nur bestimmte Befehle darüber laufen.

## Gut zu wissen

- Ein Linux-Rechner zählt als ein Gerät und teilt sich das Kontingent gleichzeitig verbundener Geräte mit Ihren anderen Geräten (Persönlich 2 Geräte, Familie 4 Geräte, Unternehmen 8 Geräte); der Web-Proxy aus Weg zwei wird pro Verbindung gezählt und ist ebenfalls enthalten.
- Konfigurationsdatei und Passwortdatei sind so viel wert wie Ihr Konto; committen Sie sie nicht in ein Git-Repository und packen Sie sie nicht in ein Image.
- Ändern Sie Ihr Passwort, funktioniert die alte Konfiguration sofort nicht mehr – das ist der vorgesehene Sperrmechanismus. Es genügt, die Passwortdatei zu aktualisieren.
- Betreiben Sie die Leitung auf einem Cloud-Server, halten Sie sich an die Nutzungsbedingungen des Anbieters; die Leitung protokolliert nur Verbindungsdauer und Gesamtdatenvolumen.

## Häufige Fragen

**Warum enthält die Linux-Konfiguration Konto und Passwort nicht?** NetworkManager akzeptiert beim Import keine Datei mit eingebetteten Zugangsdaten und meldet einen Importfehler; deshalb tragen Sie sie bei der Linux-Version selbst ein – bei der systemd-Variante in die Passwortdatei.

**Kann ich nur Docker über die Leitung schicken?** Ja: Setzen Sie die Proxy-Variablen nur für den Docker-Daemon (Weg zwei), oder betreiben Sie einen Container mit OpenVPN darin (gluetun), damit bestimmte Container über die Leitung laufen.

**Und das private Netzwerk (Tailscale) unter Linux?** Das offizielle Skript installiert es mit einer Zeile, und tailscale up --login-server=<Steuerserver unserer Website> meldet Sie an. Das eignet sich, wenn Sie den Rechner von außen erreichen müssen oder ihn einmal einrichten und dauerhaft online haben wollen; zum bloßen Beschleunigen von Downloads sind OpenVPN oder der Proxy einfacher.

**Gilt das auch für OpenWrt auf einem Router?** Unter OpenWrt installieren Sie luci-app-openvpn und laden die .ovpn hoch, dann läuft das ganze LAN über die Leitung; ein Router mit unserer Firmware braucht das nicht – dort melden Sie sich einfach mit Ihrem Konto an.

## Weiterlesen

- [OpenVPN-Seite: Client-Downloads und Konfigurationsdateien](https://www.leotun.com/de/openvpn?utm_source=github&utm_content=overseas-access-05)
- [OpenVPN nutzen und wann Sie es wählen](https://www.leotun.com/de/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-05)
- [Ein Synology- oder QNAP-NAS über die Leitung schicken](https://www.leotun.com/de/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-05)
- [Was der Web-Proxy ist und wann Sie ihn nutzen](https://www.leotun.com/de/guides/web-proxy?utm_source=github&utm_content=overseas-access-05)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/linux-server?utm_source=github&utm_content=overseas-access-05

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=overseas-access-05)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=overseas-access-05) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – dauerhaft gültig

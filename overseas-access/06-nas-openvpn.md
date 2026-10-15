# 06 · Ein Synology- oder QNAP-NAS über die Leitung schicken

Das NAS ist das Gerät im Haushalt, das die Leitung am dringendsten braucht und am wenigsten beachtet wird: Der Downloader muss Quellen im Ausland erreichen, Docker muss Images ziehen, Cloud Sync muss ausländische Cloudspeicher synchronisieren, und Plex muss Metadaten abrufen. Hiddify läuft auf einem NAS nicht, aber Synology und QNAP haben beide einen OpenVPN-Client eingebaut: Laden Sie auf der OpenVPN-Seite unserer Website eine .ovpn-Datei herunter, importieren Sie sie, und es verbindet sich – auch nach jedem Neustart automatisch. Dieser Artikel zeigt, wo der Import bei Synology und bei QNAP sitzt, erklärt die entscheidende Option „Standard-Gateway verwenden“, was nach einer Passwortänderung zu tun ist und warum „von außen aufs NAS zugreifen“ eine andere Sache ist, für die Sie Privat brauchen.

## Zuerst zwei Dinge auseinanderhalten

Das NAS selbst über die Leitung schicken (Downloads, Images ziehen, ausländische Cloudspeicher synchronisieren): Dafür nehmen Sie OpenVPN, darum geht es in diesem Artikel.

Von außen aufs NAS zugreifen (unterwegs Freigaben öffnen, Kameras ansehen): Dafür nehmen Sie das private Netzwerk (Tailscale), das NAS und Smartphone in dasselbe private Netz bringt; siehe „Heimkameras und NAS in China aus dem Ausland ansehen“. Überlassen Sie diese Aufgabe dem privaten Netzwerk – OpenVPN verbindet das NAS mit unserer Leitung, das private Netzwerk verbindet Sie mit Ihrem Zuhause.

## Synology

1. Melden Sie sich auf unserer Website an und klicken Sie auf der OpenVPN-Seite auf die Flagge einer Region, um die .ovpn-Datei dieser Region herunterzuladen.
2. Systemsteuerung → Netzwerk → Netzwerkschnittstelle → Erstellen → VPN-Profil erstellen → OpenVPN (über Import einer .ovpn-Datei) (Control Panel → Network → Network Interface → Create → Create VPN profile → OpenVPN (via importing a .ovpn file)), und geben Sie E-Mail-Adresse und Passwort Ihres Kontos bei uns ein.
3. „Standard-Gateway verwenden“ (Use default gateway): Angehakt läuft der gesamte ausgehende Verkehr des NAS über die Leitung (Downloads, Docker und Cloud Sync profitieren alle); ohne Häkchen wird nur der Tunnel aufgebaut, und ausgehender Verkehr geht weiterhin lokal hinaus. In den allermeisten Fällen sollte es angehakt sein.
4. Haken Sie „Erneut verbinden, wenn die VPN-Verbindung unterbrochen wird“ (Reconnect when the VPN connection is lost) an, damit sich die Verbindung nach einem Neustart des NAS oder bei Schwankungen der Leitung von selbst erholt. Verbinden Sie, und probieren Sie dann in einem Paket einen Download aus.

## QNAP

1. Laden Sie die .ovpn-Datei auf dieselbe Weise herunter.
2. QVPN Service → VPN-Client → Hinzufügen → OpenVPN (VPN Client → Add → OpenVPN), importieren Sie die Datei und geben Sie Konto und Passwort ein.
3. Haken Sie in den Verbindungseinstellungen „VPN als Standard-Gateway des NAS verwenden“ (Use VPN as the default gateway of the NAS) und die automatische Wiederverbindung an, dann verbinden Sie.

## Welcher Verkehr darüber läuft und welcher nicht

- Läuft darüber: BT- und HTTP-Aufgaben in Download Station / Download Station, Docker-Image-Downloads, Cloud Sync mit Google Drive / Dropbox / OneDrive, Metadatenabruf von Plex und Emby sowie Updates aus dem Paketzentrum.
- Läuft nicht darüber: Ihr eigener Zugriff auf das NAS im LAN – der bleibt ohnehin im LAN und ist nicht betroffen.
- Sie sind in China und wollen chinesische Seiten direkt erreichen: Das NAS hat kein Split-Routing-Skript; ist OpenVPN verbunden, läuft der gesamte ausgehende Verkehr des NAS über die Leitung. Sind chinesische Downloadquellen langsam, nutzen Sie in den Downloadaufgaben chinesische Spiegeladressen oder verbinden Sie die Leitung nur, wenn Sie sie brauchen.

## Gut zu wissen

- Die Konfigurationsdatei enthält Ihr Konto, und das Passwortfeld auf dem NAS funktioniert nach einer Passwortänderung nicht mehr: Laden Sie die .ovpn-Datei neu herunter und ersetzen Sie sie, oder ändern Sie im VPN-Profil nur das Passwort.
- Läuft das Konto ab, wird das NAS getrennt; nach der Verlängerung verbindet es sich automatisch wieder, die Konfiguration müssen Sie nicht ersetzen.
- Das NAS zählt als ein Gerät und teilt sich das Kontingent gleichzeitig verbundener Geräte mit Ihren anderen Geräten (Persönlich 2 Geräte, Familie 4 Geräte, Unternehmen 8 Geräte).
- Die Leitung läuft über UDP; ein NAS am Heimanschluss stößt so gut wie nie auf UDP-Beschränkungen.

## Häufige Fragen

**Ist das NAS im LAN noch erreichbar, wenn „Standard-Gateway verwenden“ angehakt ist?** Ja. LAN-Verkehr läuft nicht über das Gateway; Freigaben, Plex-Wiedergabe und die Verwaltungsseite sind nicht betroffen.

**Ist die Plex-Fernwiedergabe langsamer, seit das NAS über die Leitung läuft?** Die Plex-Fernwiedergabe nutzt den ausgehenden Verkehr des NAS und macht daher mit angehaktem Standard-Gateway einen Umweg über die Leitung. Für die Fernwiedergabe ist der Zugriff auf das NAS über das private Netzwerk direkter; oder verbinden Sie OpenVPN nur, wenn Sie etwas herunterladen müssen.

**Kann nur Download Station über die Leitung laufen?** Synology und QNAP haben kein Split-Routing pro App. Für feinere Kontrolle betreiben Sie in Docker einen Download-Container mit OpenVPN (etwa qbittorrent + gluetun) und schicken nur diesen über die Leitung.

**Und ein NAS mit Linux-System (TrueNAS, Unraid)?** Gehen Sie wie unter Linux vor: das Paket openvpn plus eine Konfigurationsdatei in /etc/openvpn/client/; siehe „Linux-Server und Kommandozeilen-Tools über die Leitung schicken“.

## Weiterlesen

- [OpenVPN-Seite: Client-Downloads und Konfigurationsdateien](https://www.leotun.com/de/openvpn?utm_source=github&utm_content=overseas-access-06)
- [OpenVPN nutzen – und wann es die richtige Wahl ist](https://www.leotun.com/de/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-06)
- [Heimkameras und NAS in China aus dem Ausland ansehen](https://www.leotun.com/de/guides/home-camera?utm_source=github&utm_content=overseas-access-06)
- [Linux-Server und Kommandozeilen-Tools über die Leitung schicken](https://www.leotun.com/de/guides/linux-server?utm_source=github&utm_content=overseas-access-06)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-06

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=overseas-access-06)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=overseas-access-06) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

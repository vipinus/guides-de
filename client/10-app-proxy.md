# 10 · Was tun, wenn Dropbox und andere Programme einen HTTP-/SOCKS-Proxy verlangen

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/app-proxy?utm_source=github&utm_content=client-10

**Vorab die Lage: Ein Proxy muss verschlüsselt sein.** Unverschlüsselte Proxys (reines HTTP, SOCKS4, SOCKS5) werden in Netzen in China erkannt und gestört; nach kurzer Zeit wird die Verbindung langsam oder bricht ab, und Konto und Passwort gehen obendrein im Klartext über die Leitung. Dauerhaft nutzbar sind nur verschlüsselte Verbindungen, deshalb verwendet der Web-Proxy unserer Website durchgehend Verschlüsselung; **für Programme, die nur HTTP / SOCKS5 annehmen, lassen Sie Hiddify den ganzen Rechner übernehmen** (siehe unten).

Eigenständige Programme wie Dropbox, Telegram Desktop, Steam, Cloud-Speicher-Clients und Entwicklerwerkzeuge lesen die Einstellungen des Browsers nicht, und ihre eigenen Proxy-Einstellungen akzeptieren nur unverschlüsseltes HTTP / SOCKS5. Die beiden Seiten passen nicht zusammen, deshalb verbindet sich nichts, wenn Sie einen Proxy eintragen. Die Lösung lautet: **keinen Proxy eintragen**, sondern mit Hiddify den ganzen Computer über die Leitung schicken und im Programm „Kein Proxy“ einstellen.

## Warum es trotz eingetragenem Proxy nicht verbindet

| Ursache | Erklärung |
|---|---|
| Typ passt nicht | Das Programm bietet nur HTTP, SOCKS4 und SOCKS5, alle unverschlüsselt; der Proxy unserer Website muss verschlüsselt sein und lässt sich dort nicht eintragen |
| Ein unverschlüsselter Proxy aus dem Netz | Er verbindet eine Weile, wird dann gestört und funktioniert nur noch mal ja, mal nein |
| Deckt nur einen Teil des Verkehrs ab | Bei vielen Programmen nutzen nur Anmeldung und Synchronisierung den Proxy, Updates, Anrufe und LAN-Sync gehen weiter direkt; den UDP-Verkehr von Spielen und Anrufen leitet ein HTTP-Proxy überhaupt nicht weiter |
| In jedem Programm einzeln gepflegt | Bei einem Wechsel von Region oder Passwort müssen Sie alles einzeln ändern, und was Sie vergessen, funktioniert nicht mehr |

## Empfohlen: Hiddify übernimmt den ganzen Rechner

1. Installieren Sie Hiddify nach [09 · Hiddify auf allen Plattformen installieren](09-hiddify-install-all-platforms.md) und importieren Sie ein Profil nach [02](02-singbox-subscription-links.md).
2. Verbinden Sie im Modus „VPN“ (Standard). Unter Windows braucht die erste Verbindung Administratorrechte.
3. Stellen Sie den Proxy im Programm zurück auf „Kein Proxy“: In Dropbox unter „Einstellungen → Netzwerk → Proxys“ „Kein Proxy“ oder „Automatisch erkennen“ wählen; in Telegram Desktop unter „Einstellungen → Erweitert → Verbindungstyp“ „Proxy deaktivieren“ wählen. In jedem anderen Programm mit Proxy-Option schalten Sie sie aus.
4. Prüfen: Das Dropbox-Symbol im Infobereich zeigt „Aktuell“ und die Synchronisierung startet; öffnen Sie im Browser eine Seite, die Ihre IP anzeigt – der Ausgang liegt in der gewählten Region.

Mit eingeschaltetem „automatischem Routing“ laufen ausländische Dienste wie Dropbox über die Leitung, während WeChat, Onlinebanking und chinesische Websites wie gewohnt direkt verbinden.

## Gängige Programme

| Programm | Einstellung |
|---|---|
| Dropbox | Proxy „Kein Proxy“ oder „Automatisch erkennen“; steht es auf „Manuell“ mit irgendeiner anderen Adresse, bleibt es offline, sobald Hiddify aus ist |
| Telegram Desktop | Verbindungstyp „Proxy deaktivieren“; das eingebaute MTProto / SOCKS5 zusätzlich über dem Tunnel macht es nur langsamer |
| OneDrive, Google Drive, iCloud für Desktop | Folgen dem Systemnetz; nichts einzustellen |
| Steam, Epic, Battle.net | Kein Proxy nötig; sind Downloads langsam, wechseln Sie zu einer näheren Region |
| Zoom, Teams, Slack, Discord | Sprache und Video laufen über UDP, das nur eine Methode für den ganzen Rechner transportiert |
| VS Code, JetBrains, Cursor | Folgen dem Systemnetz; einen im Tool separat gesetzten Proxy löschen |

## Wenn Sie keinen Client installieren dürfen (Firmenrechner)

- Nutzen Sie die Webversion von Dropbox und Cloud-Speichern: Öffnen Sie dropbox.com in einem Browser mit dem [Web-Proxy](03-web-proxy-extension.md); Hoch- und Herunterladen geht, automatische Synchronisierung nicht.
- Kommandozeilen-Tools (git, pip, npm, curl) akzeptieren einen verschlüsselten Proxy: Tragen Sie die Web-Proxy-Adresse in `https_proxy` ein; siehe [Aus China ausländische Dienste erreichen 05 · Linux und die Kommandozeile](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/05-linux-server.md) (auf Chinesisch).
- Andere Desktop-Programme, die nur HTTP / SOCKS5 akzeptieren, nutzen Sie besser auf Ihrem eigenen Computer oder Smartphone; installieren Sie dafür kein VPN für den ganzen Rechner auf einem Firmencomputer – das löst Sicherheitsalarme der Firma aus.

## Häufige Fragen

**Können Sie mir eine SOCKS5- oder HTTP-Proxy-Adresse geben?** Der Proxy unserer Website nutzt durchgehend verschlüsselte Verbindungen; ein unverschlüsselter funktioniert nach kurzer Zeit nur noch mal ja, mal nein. Hiddify den ganzen Rechner übernehmen zu lassen ist stabiler und deckt alle Programme auf einmal ab.

**Muss ich bei eingeschaltetem Hiddify noch einen Proxy im Programm eintragen?** Nein. Das wäre ein doppelter Umweg: bestenfalls langsamer, schlimmstenfalls verbindet es gar nicht.

**Und Dropbox auf dem Smartphone?** Smartphone-Apps haben keine Proxy-Einstellungen. Installieren Sie Hiddify oder nutzen Sie Cisco (AnyConnect); sobald die Verbindung steht, laufen alle Apps über die Leitung.

**Geht es auch ohne Hiddify?** Ja. Cisco, das private Netzwerk und OpenVPN übernehmen ebenfalls den ganzen Rechner, und auch dann stellen Sie im Programm „Kein Proxy“ ein. Der Vorteil von Hiddify ist das eingebaute Routing und das bessere Tempo in Netzen mit viel Paketverlust.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=client-10)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-10) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

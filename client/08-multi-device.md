# 08 · Viele Geräte einmal einrichten – und beim Handywechsel nicht von vorn anfangen

Wer viele Geräte hat, ärgert sich vor allem darüber, jedes einzeln einzurichten, nach einem Handywechsel alles noch einmal zu machen und unterwegs auf jedem Gerät auf Verbinden zu tippen. Das private Netzwerk nimmt Ihnen all das ab: Jedes Gerät meldet sich einmal mit Ihrem Konto unserer Website an und bleibt dann online – nach einem Neustart oder WLAN-Wechsel ist nichts zu tun. Jedes Gerät wählt seine eigene Ausgangsregion, der Laptop kann also Japan nutzen und das Smartphone die Region China, ohne sich gegenseitig zu stören. Geräte unter demselben Konto erreichen einander, sodass ein Laptop unterwegs direkt die Freigaben des NAS zu Hause öffnen kann. Ein neues Smartphone muss sich nur anmelden. Dieser Artikel erklärt, wie Sie alle Geräte eines Haushalts einbinden, wie das Kontingent gezählt wird und was bei Ablauf und Gerätewechsel zu tun ist.

## Was Sie pro Gerät nur einmal erledigen

1. Installieren Sie den Tailscale-Client (Android, Windows, macOS und Linux aus dem Downloadbereich der Seite „Privat“ unserer Website; iPhone / iPad aus dem App Store, dafür ist eine Apple-ID außerhalb der Region China nötig).
2. Waren Sie bei einem offiziellen Tailscale-Konto angemeldet, melden Sie sich zuerst ab und richten Sie die Anmeldung dann auf den Steuerserver unserer Website (Smartphone: „⋯“ auf dem abgemeldeten Bildschirm → „Use custom server“ (eigenen Server verwenden); Computer: Befehl von der Seite kopieren; macOS: „Account Settings“ → „Accounts“ → Pfeil neben „Add Account…“ → „Add Account Using Alternate Server“ (Konto über alternativen Server hinzufügen)).
3. Bestätigen Sie im Browser mit Ihrem Konto unserer Website. Ab dann ist das Gerät im privaten Netzwerk und braucht keine weitere Aufmerksamkeit.
4. Wählen Sie einen Ausgang: Jedes Gerät wählt im eigenen Menü, unabhängig von den anderen. Ohne Ausgang wählen Sie „None“ (keiner) – dann bleibt nur der Zugriff von Gerät zu Gerät.

## Wie gleichzeitig verbundene Geräte gezählt werden

Ein Konto lässt sich auf beliebig vielen Geräten installieren; begrenzt ist nur, wie viele gleichzeitig online sind: Persönlich 2, Familie 4, Unternehmen 8 – ein gemeinsames Kontingent mit Cisco, Hiddify und den anderen Verbindungsarten. Überschreiten Sie das Limit Ihres Tarifs, können Sie den Kontotyp vorübergehend hochstufen (die Restlaufzeit wird wertgleich nach Preis umgerechnet) und danach wieder zurückwechseln.

Ein Router zählt als ein Gerät, die Geräte dahinter werden nicht mitgezählt. Ein Router oder NAS zu Hause plus Smartphone und Laptop für unterwegs reicht meist aus.

## Geräte erreichen einander

- Jedes Gerät unter demselben Konto hat eine Adresse im privaten Netzwerk und ist auch über seinen Gerätenamen erreichbar – ohne öffentliche IP oder Portweiterleitung.
- Vom Laptop unterwegs einen freigegebenen Ordner auf dem NAS zu Hause öffnen, vom Smartphone den Videorekorder zu Hause ansehen oder per Remotedesktop auf den Heimcomputer zugreifen – all das verbindet sich direkt über die Adressen im privaten Netzwerk.
- Ein Heimrouter mit unserer Firmware kann das ganze LAN ins private Netzwerk freigeben, sodass auch Geräte ohne Client, etwa Drucker und Fernseher, von außen erreichbar sind.
- Geräte anderer Kunden tauchen in Ihrem privaten Netzwerk überhaupt nicht auf – nicht nur, dass Sie sie nicht sehen.

## Ablauf, Gerätewechsel, Deinstallation

- Konto abgelaufen: Alle Geräte gehen innerhalb weniger Minuten offline; nach der Verlängerung melden Sie sich auf jedem noch einmal an, die Ausgangseinstellungen bleiben erhalten.
- Handywechsel: Melden Sie sich auf dem neuen Smartphone nach den Schritten oben an; heißt es, das Limit sei erreicht, melden Sie sich auf dem alten Smartphone ab oder stufen den Kontotyp vorübergehend hoch und wechseln danach zurück.
- Soll ein Gerät nicht im privaten Netzwerk bleiben: Melden Sie sich im Client ab; um ein Gerät zwangsweise offline zu schalten, wenden Sie sich an den Support.
- Betreiben Sie auf demselben Gerät nicht gleichzeitig ein weiteres VPN (einen Cisco-Client der Firma, andere Mesh-Netzwerk-Software); sie streiten sich um DNS und Routen.

## Häufige Fragen

**Kann jedes Gerät eine andere Ausgangsregion wählen?** Ja, jedes Gerät wählt seinen eigenen Ausgang. Der Laptop kann Japan für Videos nutzen, während das Smartphone die Region China fürs Onlinebanking nutzt, ohne sich gegenseitig zu stören.

**Leert das dauerhaft eingeschaltete private Netzwerk den Akku?** Ohne gewählten Ausgang fließt fast kein Datenverkehr; er entsteht nur bei der Kommunikation mit Geräten im privaten Netzwerk. Der Akkuverbrauch ist vergleichbar mit dem des System-VPN.

**Wie installiere ich es auf einem NAS zu Hause?** Synology und QNAP haben ein Tailscale-Paket, Linux-Systeme nutzen das offizielle Installationsskript; bei der Anmeldung richten Sie es auf dieselbe Weise auf den Steuerserver unserer Website. Ein Router mit unserer Firmware braucht keine Installation: Melden Sie sich mit Ihrem Konto an, dann ist er im privaten Netzwerk.

**Warum nicht einfach auf jedem Gerät Cisco einrichten?** Das geht, aber bei Cisco müssen Sie jedes Mal auf Verbinden tippen, nach einem Abbruch neu verbinden und für einen anderen Ausgang die Adresse ändern; bei vielen Geräten ist das private Netzwerk deutlich bequemer. Die Ausnahme ist ein Gerät in einem Campusnetz, das UDP einschränkt – dort nehmen Sie Cisco.

## Weiterlesen

- [Seite Privat: Download und Anmeldeschritte](https://www.leotun.com/de/mesh?utm_source=github&utm_content=client-08)
- [Was das private Netzwerk (Tailscale) ist](https://www.leotun.com/de/guides/tailscale-mesh?utm_source=github&utm_content=client-08)
- [Heimkameras und NAS in China aus dem Ausland ansehen](https://www.leotun.com/de/guides/home-camera?utm_source=github&utm_content=client-08)
- [Was die Router-Firmware kann](https://www.leotun.com/de/guides/router-firmware?utm_source=github&utm_content=client-08)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/multi-device?utm_source=github&utm_content=client-08

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=client-08)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-08) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

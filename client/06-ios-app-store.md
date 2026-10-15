# 06 · Was tun, wenn iOS eine App nicht installieren lässt

Finden Sie Hiddify, Tailscale oder Telegram auf Ihrem iPhone nicht, oder sehen Sie „Diese App ist in deinem Land oder deiner Region derzeit nicht verfügbar“, ist die App nicht verschwunden: Der App Store ist nach der Region Ihrer Apple-ID in Länder-Stores aufgeteilt, und der chinesische Store führt die meisten Netzwerk-Apps nicht. Unter iOS installieren Sie aus dem App Store mit einer Apple-ID außerhalb der Region China; die Schritte stehen auf dieser Seite. Wir empfehlen, eine neue anzulegen, statt Ihr bestehendes Konto umzustellen. Unten finden Sie die Schritte, den Trick mit der Zahlungsmethode „Keine“ und den Grund, warum Sie niemals ein Konto nutzen sollten, das Ihnen jemand anderes überlässt.

## Warum das passiert

Der App Store ist nach der Region Ihrer Apple-ID in Länder-Stores aufgeteilt, und jede Region führt andere Apps. Im chinesischen Store gibt es weder Hiddify noch Tailscale, Telegram und Discord tauchen mal auf und verschwinden wieder; Cisco Secure Client und OpenVPN Connect gibt es in den meisten Regionen. Das ist ein Unterschied im Angebot, kein Problem der Apps – mit einem Konto aus einer anderen Region lassen sie sich installieren.

Auf dem iPhone werden sowohl Hiddify als auch das private Netzwerk (Tailscale) unserer Website aus dem App Store installiert; wechseln Sie einfach nach den Schritten unten zu einer Apple-ID in einer anderen Region. Die Installationsdateien für Android, Windows und macOS stellt unsere Website direkt bereit, sie sind nicht betroffen.

## Möglichkeit 1 (empfohlen): eine neue Apple-ID außerhalb der Region China anlegen

1. Melden Sie sich vom aktuellen App-Store-Konto ab: Einstellungen → Ihr Profil oben → Medien & Käufe → Abmelden. Damit melden Sie sich nur vom App Store ab, nicht von iCloud – Fotos, Backups und Kontakte sind nicht betroffen.
2. Suchen Sie im App Store eine Gratis-App, tippen Sie auf „Laden“ und folgen Sie dem Hinweis zu „Neue Apple-ID erstellen“. Wählen Sie als Region die USA, Hongkong, Japan oder Singapur und als Zahlungsmethode „Keine“. Dieses „Keine“ erscheint nur auf dem Weg, bei dem Sie sich beim Laden einer Gratis-App registrieren; bei der direkten Registrierung im Web fehlt es oft.
3. Melden Sie sich mit dem neuen Konto im App Store an, suchen Sie dann nach Hiddify, Tailscale und Telegram und laden Sie sie herunter.
4. Nach der Installation können Sie wieder zu Ihrem ursprünglichen Konto wechseln; die installierten Apps funktionieren und aktualisieren sich weiter wie gewohnt. Für eine neue App wechseln Sie bei Bedarf erneut.

## Möglichkeit 2: die Region Ihres bestehenden Kontos ändern

Melden Sie sich bei account.apple.com an und ändern Sie Land oder Region. Dafür müssen Sie zuerst alle Abos kündigen und Ihr Guthaben aufbrauchen, teils zusätzlich eine lokale Zahlungsmethode hinterlegen, und das Zurückwechseln ist genauso mühsam. Nicht empfohlen, es sei denn, Sie wollen die Region ohnehin dauerhaft wechseln.

## Was Sie niemals tun sollten

- Nutzen Sie keine Apple-ID, die Ihnen jemand anderes überlässt – auch keine „geteilten Konten“ aus Gruppen oder dem Netz. Der Kontoinhaber kann Ihr Gerät aus der Ferne sperren, und ein gesperrtes iPhone kann nur er wieder entsperren; ist die Zwei-Faktor-Authentifizierung einmal aktiv, lässt sie sich nicht mehr abschalten, und Risiko wie Streitigkeiten tragen Sie. Auch der Support unserer Website stellt keine geteilten Konten bereit.
- Installieren Sie keine Konfigurationsprofile unbekannter Herkunft und keine Installationsdateien, die „mit einem Unternehmenszertifikat signiert“ sind. Das sind gängige Wege, den Store zu umgehen – und zugleich ein Einfallstor, um Zertifikate unterzuschieben und Datenverkehr abzufangen.

## Nach der Installation

Hiddify: Gehen Sie zurück auf die Hiddify-Seite unserer Website und scannen Sie den Code, oder tippen Sie auf die Schaltfläche „sing-box-Abonnement“, um zu kopieren, wechseln Sie dann zu Hiddify und fügen Sie es hinzu. Tailscale: Melden Sie sich zuerst vom offiziellen Konto ab und tragen Sie dann nach den Schritten auf der Seite Privat die Adresse des Steuerservers unserer Website ein. Telegram, Discord: Gehen Sie auf die Kontaktseite unserer Website und scannen Sie den Code, um der Gruppe beizutreten.

## Häufige Fragen

**Brauche ich für die Registrierung in einer anderen Region eine Kreditkarte?** Nein. Auf dem Weg aus Möglichkeit 1 (Registrierung beim Laden einer Gratis-App) können Sie als Zahlungsmethode „Keine“ wählen.

**Beeinflusst das neue Konto mein iCloud und meine Fotos?** Nein. Sie wechseln das Konto nur im App Store; iCloud bleibt bei Ihrem ursprünglichen Konto.

**Ist es auf dem iPad genauso?** Ja, iPadOS folgt denselben App-Store-Regeln.

**Haben Android-Smartphones dieses Problem auch?** Nein. Die Installationsdateien für Android, Windows, macOS und Linux verteilt unsere Website direkt, sie hängen von keinem App Store ab.

## Weiterlesen

- [Kontaktseite: Client-Downloads und die drei Gruppen](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-06)
- [Hiddify: per Code-Scan importieren](https://www.leotun.com/de/singbox?utm_source=github&utm_content=client-06)
- [Privates Netzwerk (Tailscale): Anmeldeschritte](https://www.leotun.com/de/mesh?utm_source=github&utm_content=client-06)
- [Wie Sie uns erreichen und den Kontakt nicht verlieren](https://www.leotun.com/de/guides/stay-in-touch?utm_source=github&utm_content=client-06)

Website-Version dieses Artikels (auch auf Deutsch): https://www.leotun.com/de/guides/ios-app-store?utm_source=github&utm_content=client-06

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=client-06)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-06) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

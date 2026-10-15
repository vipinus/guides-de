# 09 · Den Support aus der Ferne auf Computer und Router schauen lassen

Manche Probleme lassen sich auch nach einem Dutzend hin- und hergeschickter Screenshots in der Gruppe nicht klären, während der Support sie mit einem direkten Blick auf den Bildschirm in zwei Minuten eingrenzt. Dieser Artikel erklärt, wann sich Fernhilfe lohnt, welche Software Sie auf dem Computer nutzen, wie Sie die Serverkonfiguration unserer Website importieren, wie Sie dem Support die Verbindungsdaten sicher übergeben, was Sie während der Sitzung in der Hand haben, wie Sie den Zugriff danach zurücknehmen und was Sie bei einem Router mit unserer Firmware tun müssen.

## Wann sich Fernhilfe lohnt

- Sie haben [01 · Checkliste: keine Verbindung, langsam, Abbrüche](01-cannot-connect-slow-drops.md) einmal durchgearbeitet und mit Verbindungsart, Region, genauem Wortlaut der Fehlermeldung oder Screenshot und Zeitpunkt des Problems gefragt, und es lässt sich trotzdem nicht lösen.
- Sie können die Schritte selbst nicht beschreiben: Die Einstellung ist tief vergraben, Sie können die Systemsprache nicht lesen, oder die Fehlermeldung verschwindet zu schnell für einen Screenshot.
- Sie helfen einem Familienmitglied mit dessen Computer, sind nicht vor Ort und kommen am Telefon nicht weiter.

In folgendem Fall **nutzen Sie keine Fernhilfe**, sondern klären es schriftlich in der Gruppe:

- Zentral von einer Firma verwaltete Computer. Gruppenrichtlinien verbieten meist das Ausführen solcher Programme, und es kann gegen Firmenregeln verstoßen.

## Welche Software: RustDesk

Die Website empfiehlt [RustDesk](https://rustdesk.com): Es ist Open Source (AGPL-3.0), der Code kann also von jedem geprüft werden; und wann eine Sitzung beginnt und endet, bestimmen Sie mit Ihrem eigenen Klick. Es unterstützt Windows, macOS, Linux, Android und iOS (ein iPhone / iPad kann nur andere steuern, sich aber nicht steuern lassen).

Laden Sie es auf der [Kontaktseite](https://www.leotun.com/de/contact#downloads) unter „Download-Center“ → „Fernhilfe“ herunter oder von der offiziellen Website rustdesk.com. Nutzen Sie keine Download-Seiten Dritter aus Suchergebnissen. Beide Seiten der Sitzung müssen es installieren.

## Was Sie nach der Installation erlauben

| System | Was zu tun ist |
|---|---|
| macOS | Haken Sie unter „Systemeinstellungen → Datenschutz & Sicherheit“ RustDesk sowohl bei „Bildschirmaufnahme“ als auch bei „Bedienungshilfen“ an, beenden Sie es dann vollständig und öffnen Sie es erneut. Wird nur eines erteilt, gilt „sehen ja, steuern nein“ oder der Bildschirm bleibt ganz schwarz. Heißt es „ist beschädigt“, siehe [06](06-antivirus-false-positive.md) |
| Android | Tippen Sie bei der Hilfe in RustDesk auf „Dienst starten“ und erlauben Sie die Bildschirmaufnahme; damit der Support auf Ihrem Bildschirm tippen kann, schalten Sie RustDesk zusätzlich unter „Bedienungshilfen“ des Systems ein |
| Windows / Linux | Funktioniert meist direkt nach der Installation |

## Mit unserem eigenen Server verbinden

Die Fernhilfe läuft über den selbst betriebenen RustDesk-Server unserer Website, der sich auch aus China zuverlässig erreichen lässt. **Beide Seiten der Sitzung müssen ihn einmal importieren**; die beiden Enden finden sich nur, wenn sie denselben Server nutzen:

1. Melden Sie sich zuerst auf der Website an, gehen Sie dann auf der [Kontaktseite](https://www.leotun.com/de/contact#downloads) zu „Download-Center“ → „Fernhilfe“ → Verbindung mit unserem Server und klicken Sie auf „Kopieren“.
2. Öffnen Sie am Computer in RustDesk „Einstellungen → Netzwerk“ (Settings → Network), klicken Sie zuerst auf „Netzwerkeinstellungen entsperren“ und dann auf „ID/Relay-Server“; auf dem Smartphone ist es „Einstellungen → ID/Relay-Server“.
3. Klicken Sie im erscheinenden Fenster oben rechts auf das Zwischenablage-Symbol (auf dem Smartphone auf „Importieren“). Die Konfiguration wird automatisch eingetragen; klicken Sie auf „OK“.

**Fügen Sie die Konfiguration nicht in die Eingabefelder ein**; das führt zu „failed to lookup address“ (Adresse nicht auflösbar). Diese Konfiguration ist nur für Konten unserer Website gedacht. Leiten Sie sie nicht weiter.

## ID und Einmalpasswort an den Support übergeben

Öffnen Sie RustDesk, zeigt der Hauptbildschirm die ID dieses Geräts und ein Einmalpasswort. Prüfen Sie vor der Übergabe drei Dinge:

1. **Sie haben zuerst gefragt.** Sie haben das Problem in einer offiziellen Gruppe beschrieben, die auf der [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=troubleshooting-09) aufgeführt ist, und der Support hat entschieden, dass Fernhilfe nötig ist – erst dann geht es weiter. Unsere Supportmitarbeiter sprechen Sie nicht von sich aus an, fordern Sie nicht auf, Fernwartungssoftware zu installieren, und fragen nicht nach einem Verbindungscode; wer auch immer Sie danach fragt, prüfen Sie es zuerst in der offiziellen Gruppe.
2. **Schicken Sie sie nur über offizielle Supportkanäle**: die auf der Kontaktseite genannten Kontakte des menschlichen Supports. Jeder Privatchat außerhalb der Gruppen, der sich als „LeoTun-Support“ ausgibt, sind nicht wir.
3. **Posten Sie sie nicht in der Gruppe.** Eine Gruppe sehen viele Menschen; ID plus Passwort ist, als klebten Sie den Schlüssel Ihres Computers an die Tür.

## Während der Sitzung

- Während der ganzen Sitzung sehen Sie auf dem Bildschirm, was getan wird, und können im RustDesk-Fenster jederzeit trennen.
- Bittet Sie jemand, das Fenster zu minimieren, den Computer zu verlassen oder Onlinebanking- oder Bezahl-Apps zu öffnen, **trennen Sie sofort**.
- Muss Ihr Kontopasswort eingegeben werden, tippen Sie es selbst ein; lesen Sie es dem Support nicht vor.

## Den Zugriff danach zurücknehmen

1. Klicken Sie im RustDesk-Fenster auf Trennen und vergewissern Sie sich, dass die Gegenseite offline ist.
2. Erneuern Sie das Einmalpasswort, damit das eben verschickte ungültig wird.
3. Beenden Sie RustDesk. Brauchen Sie es nicht mehr, können Sie es einfach deinstallieren und beim nächsten Mal neu herunterladen.

## Router: was Sie tun müssen

Bei einem Router mit der Firmware unserer Website müssen Sie weder auf dem Router noch auf dem Computer Fernwartungssoftware installieren, und Sie müssen dem Support nicht das Verwaltungspasswort des Routers schicken. Sie müssen nur:

- Den Router eingeschaltet und mit eingestecktem Netzwerkkabel lassen, mit angemeldetem Konto auf dem Router.
- Dem Support in der offiziellen Gruppe Ihr Konto, das Routermodell und die Symptome nennen; den Rest erledigt der Support.
- Ihn nicht wiederholt ausstecken und neu starten, während daran gearbeitet wird – außer der Support bittet Sie darum.

## Häufige Fragen

**Schreibt mich der Support von sich aus privat an und fordert mich auf, Fernwartungssoftware zu installieren?** Nein. Spricht Sie jemand unaufgefordert an, prüfen Sie seine Identität immer zuerst in der offiziellen Gruppe.

**„failed to lookup address“ beim Import?** Höchstwahrscheinlich wurde die Konfiguration in die Eingabefelder eingefügt. Leeren Sie diese Felder, gehen Sie zurück ins Fenster „ID/Relay-Server“ und importieren Sie über das Zwischenablage-Symbol oben rechts.

**Unter macOS verbunden, aber der Bildschirm ist schwarz, oder Sie sehen, können aber nicht steuern?** Die Berechtigungen sind unvollständig. Haken Sie „Bildschirmaufnahme“ und „Bedienungshilfen“ an, beenden Sie RustDesk vollständig und öffnen Sie es erneut.

**Was muss ich nach dem Ende der Sitzung noch tun?** Trennen, Einmalpasswort erneuern, Programm beenden. Sind diese drei Schritte erledigt, kann sich die Gegenseite nie wieder verbinden.

## Weiterlesen

- [Fernhilfe mit RustDesk (Anleitung auf der Website)](https://www.leotun.com/de/guides/rustdesk-certificate?utm_source=github&utm_content=troubleshooting-09)
- [Was tun, wenn der Mac meldet, die App sei „beschädigt“](https://www.leotun.com/de/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-09)
- [Kontaktseite: Supportgruppen, menschlicher Support und E-Mail](https://www.leotun.com/de/contact?utm_source=github&utm_content=troubleshooting-09)
- [05 · So erreichen Sie uns – und verlieren nie den Kontakt](05-how-to-reach-us.md)
- [01 · Checkliste: keine Verbindung, langsam, Abbrüche](01-cannot-connect-slow-drops.md)

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=troubleshooting-09)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=troubleshooting-09) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

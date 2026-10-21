# 03 · Web-Proxy: die Erweiterung ZeroOmega in zwei Schritten einrichten

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/web-proxy?utm_source=github&utm_content=client-03

Der Web-Proxy schickt nur **diesen einen Browser** über die Leitung; andere Programme auf dem System bleiben unberührt. Sie installieren keinen Client, brauchen keine Administratorrechte, und es gibt keinen Zustand „verbunden“ – folglich auch keine Verbindung, die abbrechen könnte. Er eignet sich für einen Firmenrechner, einen Rechner, der schon mit einem Firmen-VPN verbunden ist, oder wenn nur ein Browser die Leitung nutzen soll. Wann er reicht und wann ein VPN nötig ist, steht in [Netzwerk-Grundlagen 02](../network/02-choose-your-connection-method.md).

## Zwei Schritte

1. **Erweiterung installieren**: Installieren Sie ZeroOmega (die Fortsetzung von SwitchyOmega) in Chrome / Edge / Firefox. [Die Seite Web-Proxy auf unserer Website](https://www.leotun.com/de/httpproxy?utm_source=github&utm_content=client-03) enthält den Installationslink für jeden Browser.
2. **Importieren**: Melden Sie sich auf der Website an und klicken Sie auf der Seite Web-Proxy auf die Flagge der gewünschten Region (oder auf „Import-Link für alle Regionen kopieren“, um alle Regionen auf einmal zu importieren); damit ist der Einstellungslink kopiert. Öffnen Sie in der Erweiterung „Import/Export“, fügen Sie den Link unter „Restore from online“ (online wiederherstellen) ein und klicken Sie auf „Restore“ (wiederherstellen). Regionen, Adressen und Verschlüsselungsverfahren werden in einem Rutsch importiert, ohne dass Sie etwas von Hand eintippen.

Danach klicken Sie auf das Erweiterungssymbol, wählen eine Region und geben im Anmeldefenster des Browsers Konto und Passwort unserer Website ein. Für eine andere Region klicken Sie im Menü des Symbols auf eine andere; um wieder direkt lokal zu verbinden, wechseln Sie auf „Direct“ (direkt).

## In diesen Fällen nehmen Sie eine Verbindungsart für das ganze Gerät

- Video- und Musik-Apps und Player: Die meisten nutzen den Proxy des Browsers nicht, und Sie landen bei „Webseiten öffnen sich, aber Videos laufen nicht“.
- Smartphone-Apps, Spiele und Desktop-Software. Die Proxy-Einstellungen in Programmen wie Dropbox akzeptieren nur unverschlüsseltes HTTP / SOCKS5, in der Praxis muss ein Proxy aber verschlüsselt sein – der Web-Proxy unserer Website lässt sich dort also nicht eintragen. Lassen Sie stattdessen Hiddify das ganze Gerät übernehmen; siehe [10](10-app-proxy.md).
- Tencent Video oder iQIYI aus dem Ausland schauen: Videoseiten prüfen auch IPv6 und DNS, die der Web-Proxy nicht abdeckt; nehmen Sie ein VPN für das ganze Gerät.

## Häufige Fragen

| Symptom | Ursache |
|---|---|
| Das Anmeldefenster taucht immer wieder auf | Das Konto ist abgelaufen oder das Passwort ist falsch |
| Manche Websites öffnen sich nicht, andere schon | Die „Auto Switch“-Regeln (automatisch umschalten) der Erweiterung haben sie auf direkt geschickt; probieren Sie einmal den globalen Proxy-Modus |
| In China öffnen sich nur HTTPS-Websites | Unverschlüsseltes HTTP wird unterwegs verändert, nur verschlüsselte Verbindungen kommen durch; fast alle Websites nutzen heute ohnehin HTTPS |
| Langsam | Wechseln Sie die Region; Proxy und VPN nutzen dieselben Server |

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=client-03)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=client-03) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

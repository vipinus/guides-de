# 02 · Funktioniert Cisco AnyConnect in China?

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/anyconnect-china?utm_source=github&utm_content=overseas-access-02

Ja. AnyConnect ist das Unternehmens-VPN-Protokoll von Cisco. Firmen in aller Welt verlassen sich im Homeoffice darauf, und die China-Niederlassungen ausländischer Firmen nutzen es täglich – es pauschal zu verbieten, wäre zu teuer. **Gesperrt wird in Wirklichkeit eine bestimmte Serveradresse, nicht das Protokoll.** Ob „es funktioniert“, hängt also davon ab, ob der Anbieter genug Adressen hat und sie schnell genug ersetzt.

## Warum es Sperren besser widersteht als proprietäre VPN-Apps

| | AnyConnect | Proprietäre VPN-App |
|---|---|---|
| Erkennungsmerkmal des Datenverkehrs | Standard-TLS, genau wie der Aufruf einer HTTPS-Website | Eigenes Protokoll mit festem Erkennungsmerkmal |
| Einmal erkannt | Nur diese eine Adresse verbindet nicht mehr | Die ganze App funktioniert nicht mehr |
| Client | Von Cisco veröffentlicht; die Open-Source-Alternative OpenConnect gibt es für jede Plattform | Weg, sobald sie aus dem App Store entfernt wird |

LeoTun betreibt eigene Maschinen in 24 Regionen. Wird eine Adresse auffällig, wird sie durch eine neue ersetzt, der Domainname wird automatisch umgeleitet, und die in Ihrem Client gespeicherte Adresse müssen Sie nicht ändern.

## So installieren Sie es

1. Laden Sie auf der Cisco-Seite der Website das Installationsprogramm für Ihr System herunter. Windows 10 und neuer, macOS, iOS, Android und Linux sind alle abgedeckt; Windows 7/8 kann nur Version 4.9 nutzen, die letzte, die diese Systeme unterstützt.
2. Öffnen Sie den Client und tragen Sie die Serveradresse ins Adressfeld ein – auf der Website klicken Sie auf die Flagge einer Region, um sie zu kopieren.
3. Geben Sie Konto und Passwort ein und verbinden Sie. Weder eine Zertifikatsdatei noch ein Konfigurationsimport ist nötig.
4. Sobald „Connected“ (verbunden) erscheint, prüfen Sie Ihre Ausgangs-IP.

## Wenn es nicht verbindet, in dieser Reihenfolge

1. **Wechseln Sie die Region.** Verbindet eine andere Region, ist nur dieser Server vorübergehend nicht erreichbar.
2. **Wechseln Sie das Netz.** Scheitert das Breitband, nehmen Sie mobile Daten und umgekehrt; die Störungen bei verschiedenen Netzbetreibern laufen nicht synchron.
3. **Lesen Sie die Fehlermeldung.** `Login failed` betrifft Konto, Passwort oder Ablauf; `Untrusted server certificate` ist meist eine falsche Systemzeit oder ein Netz, das TLS abfängt – wechseln Sie das Netz; nur `Connection attempt has failed` bedeutet, dass die Adresse nicht erreichbar ist.
4. **Aktualisieren Sie den Client.** Das ist besonders nach einem großen Systemupgrade wichtig.
5. **Wechseln Sie die Verbindungsart.** Mit demselben Konto verbinden Sie sich per OpenVPN oder Hiddify mit denselben Servern, und die Sperren der drei Protokolle sind voneinander unabhängig; siehe [02 · Welche Verbindungsart zu welcher Situation passt](../network/02-choose-your-connection-method.md).

## Cisco AnyConnect aktualisieren

Cisco hat ihn in Cisco Secure Client umbenannt; die Bedienung ist dieselbe. Vorher deinstallieren müssen Sie nicht: Installieren Sie die neue Version über die alte, die gespeicherten Adressen bleiben erhalten. Auf Smartphones aktualisieren Sie im App Store / bei Google Play; findet die Suche im Store ihn nicht, nehmen Sie das quelloffene OpenConnect, das dasselbe Protokoll und dasselbe Konto nutzt (zum Wechsel der iOS-Store-Region siehe [Client 06](../client/06-ios-app-store.md)).

## Häufige Fragen

**Ist langsames Tempo ein Zeichen von Drosselung?** Wechseln Sie zuerst die Region: Achten Sie auf die roten, gelben und grünen Ampeln in der Regionsliste auf der Website und nehmen Sie eine grüne. Ist es dann noch langsam, liegt es meist am lokalen Breitband: geteiltes Breitband in Wohnanlagen oder Netzbetreiber und Region passen nicht zusammen (China Unicom im Norden: Japan oder Korea; China Telecom im Süden: Südostasien oder Australien; andere Anbieter: die Einstiegsregionen in China).

**Warum ist dieselbe Adresse mal gut und mal schlecht?** Die Adresse ist ein Domainname, und die Maschinen dahinter werden je nach Sperren und Auslastung automatisch ausgetauscht. Warten Sie ein, zwei Minuten und versuchen Sie es erneut – meist haben Sie gerade einen Wechsel erwischt.

**Trennt es sich nach langer Verbindungsdauer von selbst?** Nicht wegen der Dauer. Läuft das Konto ab, trennt der Server die Verbindung; verlängern Sie und verbinden Sie neu.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=overseas-access-02)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=overseas-access-02) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

# 02 · Firmware selbst flashen: Schritt für Schritt von der Original- zu unserer Firmware (mit Video)

> Videoanleitung (etwa zweieinhalb Minuten, Sprecher auf Englisch oder Chinesisch): https://www.leotun.com/de/video/router-flash?utm_source=github&utm_content=router-02
>
> Version auf der Website: https://www.leotun.com/de/guides/router-flash?utm_source=github&utm_content=router-02

Diese Anleitung richtet sich an alle, die bereits einen Router besitzen, dessen Modell auf der Liste der unterstützten Geräte steht. Ihr Router läuft noch mit der Original-Firmware, und wir gehen den ganzen Weg vom Öffnen der Website bis zum Moment, in dem der ganze Haushalt verbunden ist – was Sie bei jedem Schritt anklicken, was Sie sehen und wo es typischerweise hakt. Vorgeführt wird es an einem GL.iNet GL-MT3000. Andere Modelle folgen denselben Schritten, nur die Original-Verwaltungsoberfläche sieht anders aus. Wenn Sie das nicht selbst machen möchten, ist ein vorinstallierter Router bequemer: siehe [01](01-plug-and-play-router.md). Welches Modell sich eignet, steht in [07](07-which-router-to-buy.md).

## Bevor Sie anfangen

- **Prüfen Sie, ob Ihr Modell unterstützt wird.** Melden Sie sich an, öffnen Sie den Bereich **Router** und suchen Sie Ihr Modell nach Hersteller. Auch die Hardware-Revision hinter dem Modellnamen (v1, v2 usw.) muss übereinstimmen.
- **Ihr Konto muss aktiv sein.** Alle Tarife – Persönlich, Familie und Unternehmen – können einen Router nutzen.
- **Legen Sie ein Netzwerkkabel bereit.** Der WAN-Port des Routers kommt an Ihr Modem bzw. den vorgeschalteten Router. Beim Flashen verbinden Sie am besten auch den Computer per Kabel mit dem Router; das ist zuverlässiger als WLAN.
- **Sichern Sie die Original-Firmware.** Laden Sie die Original-Firmware Ihres Modells von der Herstellerseite herunter, falls Sie einmal zurückwechseln wollen.

## Schritt 1: Firmware auf der Website bauen

1. Melden Sie sich an und klicken Sie in der Navigationsleiste auf **Router**.
2. Suchen Sie Ihr Modell und klicken Sie auf **Firmware**, oder scrollen Sie zu „Firmware bauen“ und wählen Sie das Modell in der Herstellerliste.
3. Klicken Sie auf **Bauen starten**.

Vorab ein paar Hinweise:

- **Ein Build dauert 3 bis 5 Minuten.** Die Firmware wird in diesem Moment für Ihr Konto erstellt, es ist keine fertige Datei. Zu Stoßzeiten kann der Build in einer Warteschlange stehen. Die Seite sagt Ihnen das – warten Sie einfach, erneutes Klicken ist nicht nötig.
- **Sie erhalten eine E-Mail, wenn er fertig ist.** Der Eintrag unter „Letzte Builds“ wechselt auf „Abgeschlossen“, und eine Benachrichtigung landet in Ihrem Postfach.
- **Die Sprache der Firmware-Oberfläche richtet sich nach der Sprache der Website.** Nutzen Sie die Website auf Deutsch, ist auch die Verwaltungsoberfläche des Routers auf Deutsch. Für eine andere Sprache stellen Sie zuerst die Website um und bauen dann.
- **Der Download-Link gilt einen Tag.** Ist er abgelaufen, bauen Sie einfach neu.

## Schritt 2: Herunterladen und entpacken

1. Klicken Sie unter „Letzte Builds“ auf **Download**. Sie erhalten eine ZIP-Datei.
2. Öffnen Sie Ihren Download-Ordner und **entpacken** Sie sie.
3. Im entpackten Ordner liegt die Firmware-Datei.

Welche Datei Sie verwenden:

| Ihr Router läuft derzeit mit | Datei verwenden |
|---|---|
| GL.iNet-Original-Firmware (wie im Video) | endet auf `sysupgrade.bin` |
| Original-Firmware eines anderen Herstellers | mit `factory` im Namen |
| Bereits unserer Firmware, Sie aktualisieren | mit `sysupgrade` im Namen |

Enthält die ZIP-Datei nur eine Datei, ist es diese.

> ⚠️ **Diese Firmware gehört nur Ihnen.** Sie enthält Ihre Kontodaten, damit sich der Router nach dem Flashen selbst anmelden kann. Schicken Sie die Datei niemandem und teilen Sie sie nicht öffentlich.

## Schritt 3: In der Original-Verwaltungsoberfläche flashen

Am Beispiel GL.iNet:

1. Verbinden Sie den Computer mit dem Router, öffnen Sie die Original-Verwaltungsoberfläche im Browser (bei GL.iNet `http://192.168.8.1`) und melden Sie sich mit dem Admin-Passwort an.
2. Öffnen Sie im linken Menü **System** → **Upgrade**.
3. Wechseln Sie zum Tab **Firmware Local Upgrade** (lokales Firmware-Update).
4. Klicken Sie auf den Upload-Bereich und wählen Sie die entpackte Firmware-Datei.
5. Warten Sie, bis die Prüfung **Pass** (bestanden) anzeigt.
6. **Schalten Sie „Keep Settings“ (Einstellungen behalten) aus.** Diesen Schritt vergessen die meisten. Die beiden Systeme haben kein gemeinsames Konfigurationsformat, und alte Einstellungen führen zu allerlei seltsamen Problemen.
7. Klicken Sie auf **Install** (Installieren).

Die Seite wechselt zu „Upgrading and rebooting…“ (wird aktualisiert und neu gestartet) mit einem Fortschrittsring. **Das dauert zwei bis drei Minuten. Ziehen Sie in dieser Zeit nicht den Stecker und schließen Sie die Seite nicht.** Dass die Seite nach Abschluss nicht mehr lädt, ist normal – auf dem Router läuft jetzt ein anderes System, Adresse und WLAN haben sich geändert. Siehe nächster Schritt.

Andere Hersteller: Suchen Sie in der Original-Verwaltungsoberfläche nach „Firmware-Upgrade“, „System-Upgrade“ oder „Lokales Upgrade“, laden Sie die Datei hoch und behalten Sie auch hier keine Einstellungen.

## Schritt 4: Mit dem neuen WLAN verbinden

Nach dem Flashen ist der alte WLAN-Name verschwunden, und ein neuer erscheint:

- **WLAN-Name: `www.anyfq.com`**
- **WLAN-Passwort: `www.anyfq.com`** (identisch mit dem Namen)

Computer und Smartphones müssen **in dieses WLAN wechseln**, bevor sie ins Internet kommen oder die Verwaltungsseite des Routers öffnen können. Ein per Kabel angeschlossener Computer muss nichts umstellen.

Die neue Verwaltungsadresse lautet `http://192.168.11.1` (das `http://` am Anfang selbst eintippen).

## Schritt 5: Warten, bis er sich selbst verbindet

Keine Anmeldung, keine Regionswahl. **Solange Ihr Konto aktiv ist, verbindet sich der Router innerhalb von 10 Minuten selbst.** Danach läuft jedes Gerät in diesem WLAN automatisch über den Dienst – auch Fernseher, Set-Top-Boxen und Spielkonsolen.

Ob die Verbindung steht, prüfen Sie, indem Sie auf einem Gerät am Router eine Website öffnen, die Sie sonst nicht erreichen, oder den Status auf der Verwaltungsseite ansehen.

## Zwei Dinge, die sich danach lohnen

1. **Standardpasswörter ändern.** WLAN- und Admin-Passwort sind ab Werk öffentlich bekannte Standardwerte. Ändern Sie beide auf der Verwaltungsseite.
2. **Ein schwaches WLAN-Signal direkt nach dem Flashen ist normal.** Der Router muss einmal online gehen und feststellen, in welcher Region er steht, bevor er die Sendeleistung auf das dort erlaubte Niveau anhebt. Stecken Sie das Netzwerkkabel ein und lassen Sie ihn zuerst online gehen.

## Einen alten Router durch einen neuen ersetzen

Ein Konto ist immer nur an einen Router gleichzeitig gebunden. Wurde Ihr Konto schon an einem anderen Router genutzt:

1. Melden Sie sich an, öffnen Sie den Bereich **Router**; unter der Überschrift „Firmware bauen“ sehen Sie das Modell mit dem Status **Verknüpft** und daneben **Verknüpfung aufheben**.
2. Klicken Sie auf Verknüpfung aufheben. Das geht auch, wenn der alte Router defekt oder nicht zur Hand ist.
3. Am neuen Router ist nichts zu tun: Er **verbindet sich automatisch** und wird mit Ihrem Konto verknüpft.

Haben Sie den neuen Router schon vor dem Aufheben geflasht, ist das auch kein Problem. Er wartet und verbindet sich von selbst, sobald Sie die Verknüpfung aufheben.

Mehr zu den Regeln in [05 · MAC-Bindung und Routerwechsel](05-mac-binding-and-replacing.md).

## Was passiert, wenn mein Konto abläuft

Nach Ablauf leitet der Router nichts mehr über den Dienst, Ihr Heimnetz funktioniert aber ganz normal weiter. **Sobald Sie verlängern, erholt sich der Router von selbst – ohne erneute Anmeldung und ohne neues Flashen.**

## Er verbindet sich nicht von selbst – so prüfen Sie es

Klappt es nach etwa zehn Minuten immer noch nicht, gehen Sie diese Punkte der Reihe nach durch:

1. **Funktioniert der Internetanschluss selbst?** Öffnen Sie auf einem Gerät am Router eine beliebige normale Website. Geht das nicht, liegt es an Kabel oder Modem: Prüfen Sie, ob das Kabel im WAN-Port richtig steckt.
2. **Ist das Konto abgelaufen?** Melden Sie sich auf der Website an und prüfen Sie das Ablaufdatum. Nach einer Verlängerung ein paar Minuten warten.
3. **Ist das Konto noch mit dem alten Router verknüpft?** Sehen Sie im Bereich Router nach, welches Modell verknüpft ist. Ist es nicht dieser Router, klicken Sie auf Verknüpfung aufheben.
4. **Router einmal neu starten.** Stecker ziehen, zehn Sekunden warten, wieder einstecken und zwei bis drei Minuten Zeit geben.
5. **Manuell anmelden.** Öffnen Sie `http://192.168.11.1` und melden Sie sich mit dem Benutzernamen `root` und dem Passwort `www.anyfq.com` am Router an. Gehen Sie dann zu **Services** → **VPN** (Dienste → VPN), geben Sie die E-Mail-Adresse und das Passwort Ihres Kontos ein und speichern Sie.

Kommen Sie nicht weiter? Fragen Sie in der Gruppe und nennen Sie das Routermodell und den Punkt, bis zu dem Sie in der Liste gekommen sind.

## Wann Sie besser nicht selbst flashen

Das Modell steht nicht auf der Liste, die Hardware-Revision passt nicht, oder es ist ein alter Router ohne Wiederherstellungsmodus. In diesen drei Fällen ist ein vorinstallierter Router bequemer.

## Wenn beim Flashen etwas schiefgeht

Die meisten Router haben einen Wiederherstellungsmodus: Stromstecker ziehen, Reset-Taste gedrückt halten und dabei den Strom wieder einstecken, einige Sekunden weiter halten, dann den Computer per Kabel anschließen und die Original-Firmware nach Anleitung des Herstellers hochladen. Bei GL.iNet suchen Sie in der Dokumentation nach „uboot“. Genau dafür haben Sie vorher die Original-Firmware gesichert.

## Häufige Fragen

**Erlischt durch das Flashen die Garantie?** Das hängt vom Hersteller ab. GL.iNet-Router basieren von vornherein auf einem Open-Source-System und lassen sich auf die Original-Firmware zurückflashen.

**Kann ich zur Original-Firmware zurück?** Ja. Laden Sie die Original-Firmware über den Wiederherstellungsmodus hoch, wie unter „Wenn beim Flashen etwas schiefgeht“ beschrieben.

**Kann ich eine Firmware-Datei für zwei Router verwenden?** Nein. Die Firmware wird pro Konto gebaut, und ein Konto ist immer nur an einen Router gleichzeitig gebunden.

**Brauche ich einen neuen Build, wenn ich das Konto wechsle?** Nein. Melden Sie sich auf der Verwaltungsseite ab und mit dem neuen Konto an.

**Muss ich für künftige Updates neu flashen?** Normale Updates holt sich der Router selbst; Sie müssen nichts tun. Nur bei einer neuen Hauptversion ist ein neuer Build und einmaliges Flashen der sysupgrade-Datei nötig – die Website kündigt das dann an.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=router-02)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=router-02) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – dauerhaft gültig

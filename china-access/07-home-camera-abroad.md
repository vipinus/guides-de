# 07 · Heimkameras in China aus dem Ausland ansehen

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/home-camera?utm_source=github&utm_content=china-access-07

## Drei Fälle, jeder mit einer anderen Lösung

| Welche Art Kamerasystem Sie zu Hause haben | Direkt aus dem Ausland ansehen? | Lösung |
|---|---|---|
| Hersteller-App mit Cloud (EZVIZ, Xiaomi, TP-Link, Imou und andere) | Meist ja; in einigen Regionen eingeschränkt oder extrem langsam | Auf eine chinesische IP wechseln und die chinesische Version der App nutzen |
| Ein Netzwerk-Videorekorder (NVR), der nur im Heimnetz einsehbar ist | Nein, es gibt keinen öffentlichen Zugang | Ein Gerät zu Hause in ein privates Netzwerk aufnehmen und das Gerät im Ausland über dieses private Netzwerk ins Heimnetz holen |
| Hersteller-App, aber die Version im ausländischen Store ist ein eigenes System mit eigenen Servern | Die Konten passen nicht zusammen | Die chinesische Version der App installieren und das chinesische Konto nutzen |

## Fall eins: Cloud des Herstellers

Die Kamera schickt das Bild an den Server des Herstellers, und die App holt es vom Server ab. Die Verbindung aus einem ausländischen Netz zum Server eines chinesischen Herstellers ist schlecht, was sich als langsames Laden und abreißende Streams zeigt. Nach dem Wechsel auf eine chinesische IP sind Sie auf einer Verbindung innerhalb Chinas, und es wird spürbar besser.

Beachten Sie, dass die gleichnamige App in einem ausländischen Store meist mit ausländischen Servern verbunden ist und die Konten nicht austauschbar sind. Installieren Sie die chinesische Version der App; bei Problemen mit der Store-Region siehe die [Anleitung zur Installation und Fehlerbehebung](../client/06-ios-app-store.md).

## Fall zwei: Der Rekorder ist nur im Heimnetz

Das ist der häufigste und zugleich schwierigste Fall. Der NVR hat keine öffentliche IP, und Portweiterleitung ist bei Heimanschlüssen in China meist nicht möglich. Was funktioniert, ist ein **privates Netzwerk**:

1. Lassen Sie zu Hause ein Gerät dauerhaft eingeschaltet; ein Computer, ein NAS, ein Raspberry Pi oder ein unterstützter Router tun es alle. Installieren Sie darauf den Client des privaten Netzwerks, nehmen Sie es in Ihr privates Netzwerk auf und schalten Sie „LAN freigeben“ (share LAN) ein.
2. Nehmen Sie auch das Smartphone oder den Computer im Ausland in dasselbe private Netzwerk auf.
3. Ab dann erreicht das Gerät im Ausland den NVR direkt unter seiner Adresse im Heimnetz, als wären Sie zu Hause.

„Privat“ von LeoTun ist genau so ein privates Netzwerk. Auf wie vielen Geräten Sie es mit einem Konto installieren, ist nicht begrenzt; die Zahl gleichzeitig verbundener Geräte richtet sich nach dem Tarif: Persönlich 2 Geräte, Familie 4 Geräte, Unternehmen 8 Geräte. Ein Gerät zu Hause plus einige im Ausland – dafür passt der Tarif Familie genau.

## Fall drei: Die Konten passen nicht zusammen

Ein in China gekauftes Gerät ist an ein chinesisches Konto gebunden, und die App aus dem ausländischen Store kann sich dort nicht anmelden. Die einzige Lösung ist, die chinesische Version der App zu installieren. Binden Sie das Gerät nicht neu, sonst fliegt das Konto Ihrer Familie heraus.

## Ein Hinweis zur Privatsphäre

Das Bild Ihrer Heimkameras sollte nur zwischen Ihren Geräten und Ihrem Zuhause fließen. Das private Netzwerk bevorzugt eine direkte Verbindung von Gerät zu Gerät und leitet nur dann über einen Vermittlungsserver weiter, wenn keine direkte Verbindung zustande kommt; das Bild wird auf keinem Server gespeichert. Bei der Cloud des Herstellers läuft es dagegen über den Hersteller. In keinem Fall sollten Sie „Tunnel-Tools“ unklarer Herkunft nutzen – das hieße, Ihre Heimkameras jemand anderem zu überlassen.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=china-access-07)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=china-access-07) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

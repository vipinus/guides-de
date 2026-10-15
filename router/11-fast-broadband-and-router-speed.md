# 11 · Gigabit- oder 2-Gbit/s-Anschluss mit Router: Was über das Tempo entscheidet

Heimanschlüsse werden immer schneller, und so kommt oft die Frage: Mein Anschluss hat ein Gigabit, sogar 2 Gbit/s – was kommt davon über einen VPN-Router an?

## Die kurze Antwort

Für den Verkehr, der durch den Tunnel läuft, entscheidet die Strecke, die China verlässt. **Der Engpass ist nicht Ihr Heimanschluss, sondern die Strecke aus China hinaus.** Wir versprechen flüssige YouTube-Wiedergabe. Das genaue Tempo hängt von den Punkten unten ab.

Verkehr zu chinesischen Diensten nutzt den Tunnel nicht und läuft weiter mit der vollen Geschwindigkeit Ihres Anschlusses. Siehe [10 · Sind NAS, Drucker und Kameras betroffen?](10-nas-printer-camera-behind-router.md)

## Vier Dinge, die über das Tempo entscheiden

**1. Die grenzüberschreitende Strecke**
Die internationale Kapazität teilen sich alle, und sie hat nichts damit zu tun, wie schnell Ihr Tarif zu Hause ist. Von 20 bis 23 Uhr Pekinger Zeit ist landesweit Spitzenzeit; wählen Sie dann eine Region mit grüner Ampel. Ist es immer noch langsam, liegt es meist am lokalen Breitband (geteiltes Breitband in Wohnanlagen oder Netzbetreiber und Region passen nicht zusammen; siehe nächster Punkt). Siehe [Warum es manchmal schnell und manchmal langsam ist](../network/06-why-sometimes-fast-sometimes-slow.md).

**2. Ihr Netzbetreiber und die gewählte Region**
Jeder Netzbetreiber verlässt China auf einem anderen Weg, und die richtige Region zu wählen ist wichtiger als alles andere:
- China Unicom im Norden: zuerst Japan und Korea probieren
- China Telecom im Süden: zuerst Südostasien probieren
- Andere Netzbetreiber: zuerst die Einstiegsregionen in China probieren

**3. Der Router selbst**
Der Verkehr muss verschlüsselt werden, bevor er in den Tunnel geht, und das ist Arbeit für den Prozessor des Routers. Die Modelle unterscheiden sich stark:
- GL-MT300N-V2 (Mini): 100-Mbit/s-Ports. Reicht für 1080p auf Smartphone oder Laptop, einem schnellen Anschluss aber nicht gewachsen
- GL-MT3000 (Reiserouter): schafft einen kleinen Haushalt. Für die meisten der erste Router
- GL-MT6000 (Desktop): 2,5G-Port. Für viele Geräte, 4K und Spielkonsolen

Bei schnellem Anschluss und vollem Haushalt nehmen Sie den MT3000 oder MT6000, nicht den Mini.

**4. Die letzten Meter zu Hause**
Schließen Sie Fernseher und Desktop-PC per Kabel an, wo immer es geht. WLAN in einem dicht bewohnten Mehrfamilienhaus leidet unter starken Störungen, und vieles, was nach „die Leitung ist langsam“ aussieht, liegt in Wahrheit in der eigenen Wohnung.

## Wenn es sich langsam anfühlt, probieren Sie der Reihe nach

1. Wechseln Sie die Region. Probieren Sie zwei, drei und finden Sie die, die zu dieser Tageszeit durchhält.
2. Schalten Sie auf der Verwaltungsseite „Automatically pick the fastest line“ (automatisch die schnellste Leitung wählen) ein. Es wählt die Leitung mit der geringsten Latenz und dem geringsten Paketverlust und wechselt, wenn sich das ändert. Beachten Sie, dass das Ausgangsland dann von der gewählten Region abweichen kann.
3. Hängen Sie das Gerät, auf dem Sie Videos schauen, ans Kabel.
4. Prüfen Sie, ob es nur diese eine Website betrifft. Sind andere Websites im selben Moment schnell, liegt das Problem bei der Gegenseite.

## So wissen Sie es vor dem Kauf

Registrieren Sie sich und nutzen Sie den 24-stündigen Gratistest, ohne Kreditkarte. Verbinden Sie sich zu der Tageszeit, zu der Sie es am meisten nutzen, etwa am Abend, und sehen Sie ein YouTube-Video in HD. Was Sie auf Smartphone oder Laptop sehen, kommt dem nahe, was der Router liefern wird. Über den Router entscheiden Sie danach.

## Häufige Fragen

**Warum sagen Sie mir nicht einfach, wie viele Megabit?** Weil die Zahl für jeden Menschen und zu jeder Stunde anders ist. Wir versprechen flüssige YouTube-Wiedergabe, auch zur Abendspitze, sofern Ihr Breitband gut ist: China Unicom im Norden oder China Telecom im Süden. Die Ausnahme ist geteiltes Breitband in Wohnanlagen (小区宽带). Der 24-stündige Gratistest, einmal selbst ausprobiert, ist der genaueste Test.

**Die Speedtest-Seite zeigt einen niedrigen Wert, aber Videos laufen flüssig?** Das ist normal. Speedtest-Server haben selbst ruhige und volle Phasen, und zwei Messungen im Abstand von einer Minute können sich um das Doppelte unterscheiden. Maßgeblich ist das, was Sie tatsächlich tun wollen.

**Wird es mit einem teureren Router schneller?** Nur wenn der Router der Engpass ist, etwa ein Mini-Modell an einem schnellen Anschluss. Ist der Engpass die grenzüberschreitende Strecke, bringt ein neuer Router nichts, eine andere Region dagegen schon.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=router-11)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=router-11) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

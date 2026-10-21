# 08 · Nach dem Flashen: Was die Firmware von selbst erledigt und welche Schalter Sie kennen sollten

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/router-firmware?utm_source=github&utm_content=router-08

Nachdem Sie unsere Firmware geflasht oder ein vorinstalliertes Gerät gekauft haben, müssen Sie sich nur noch auf der Verwaltungsseite mit Ihrem Konto anmelden. Dieser Artikel behandelt, was die Firmware **von selbst erledigt**, und die wenigen Schalter, die Sie eventuell anfassen müssen; für den Einstieg siehe [01](01-plug-and-play-router.md), für Split-Routing [03](03-router-split-routing.md), für Bindung und Routerwechsel [05](05-mac-binding-and-replacing.md).

## Was sie von selbst erledigt

| Was | Wie es funktioniert | Was Sie tun müssen |
|---|---|---|
| Updates von Komponenten und Split-Routing-Liste | Prüft beim Start und lädt Updates herunter, die **beim nächsten Start wirksam werden**; die Liste gesperrter Websites für den Zugriff auf ausländische Dienste aus China aktualisiert sich außerdem täglich automatisch | Nichts; geänderte Leitungsadressen und neu in die Liste aufgenommene Websites werden automatisch übernommen |
| WLAN-Ländercode | Erkennt nach dem ersten Onlinegang das Land, in dem er steht, und stellt Sendeleistung und Kanäle automatisch ein | Direkt nach dem Flashen **zuerst ein Netzwerkkabel einstecken**, damit er einmal online geht; ein schwächeres Signal davor ist normal |
| Verhalten bei Ablauf | Läuft das Konto ab, geht nichts mehr über das VPN; das lokale Netz funktioniert normal weiter | Nach der Verlängerung erholt er sich automatisch, ohne erneute Anmeldung |
| Router-Bindung | Bei der ersten Anmeldung wird dieser Router beim Konto hinterlegt | Vor einem Routerwechsel auf der Website die Verknüpfung aufheben |

Nur ein Hauptversions-Upgrade der gesamten Firmware erfordert das Flashen der sysupgrade-Datei. Das kommt nur ein paar Mal im Jahr vor, und die Website informiert Sie darüber.

## Was Sie eventuell anfassen müssen

- **Split-Routing-Modus**: Split-Routing (Standard) / Global / Direkt. Öffnet sich eine Website nicht, schalten Sie zur Kontrolle zuerst auf Global: Öffnet sie sich unter Global, steht sie nicht auf der Liste – schicken Sie die Adresse an den Kundenservice, damit sie aufgenommen wird; öffnet sie sich auch unter Global nicht, liegt das Problem bei der Website selbst.
- **Region**: wird auf der Verwaltungsseite gewählt. Wählen Sie die Region China, um aus dem Ausland chinesische Inhalte zu sehen, und eine ausländische Region, um aus China ausländische Dienste zu erreichen.
- **Blocked sites only** (nur gesperrte Websites): ein Kontrollkästchen unter „VPN settings“ (VPN-Einstellungen) im Abschnitt für intelligentes Split-Routing, standardmäßig angehakt. Es gilt nur für die Richtung „aus China ausländische Dienste erreichen“ (Sie sind in China und haben eine ausländische Region gewählt). Ist es angehakt, laufen nur gesperrte Websites und Dienste über das VPN (anhand einer täglich automatisch aktualisierten Liste gesperrter Websites plus Diensten wie Telegram, die sich mit festen Adressen verbinden); chinesische Websites und ausländische Websites, die sich in China ohnehin problemlos öffnen (Websites ausländischer Firmen, Downloads von Apple und Microsoft, Spieleplattformen und Ähnliches), gehen direkt, ohne Umweg. Entfernen Sie das Häkchen, gilt wieder das frühere Verhalten: chinesische Websites direkt, alles andere über das VPN. Öffnet sich in China eine ausländische Website nicht, entfernen Sie das Häkchen (oder schalten vorübergehend auf Global) und versuchen es erneut; öffnet sie sich dann, ist die Website gesperrt, steht aber noch nicht auf der Liste – schicken Sie die Adresse an den Kundenservice. Firmware, die vor Oktober 2026 geflasht wurde, zeigt dieses Kontrollkästchen noch nicht an (der neue Standard gilt über die automatischen Updates trotzdem schon); wollen Sie es ändern, wenden Sie sich an den Kundenservice, der das aus der Ferne erledigen kann. Die Richtung „aus dem Ausland China erreichen“ ist von diesem Schalter nicht betroffen.
- **Automatically select the fastest line** (schnellste Leitung automatisch wählen): unterhalb der Region, standardmäßig aus, empfehlenswert bei schlechter Netzqualität.

  | | Aus (Standard) | An |
  |---|---|---|
  | Welche Leitung genutzt wird | Immer die gewählte Region | Wählt unter den verfügbaren Leitungen automatisch die mit der geringsten Latenz und wenig Paketverlust, misst regelmäßig neu und wechselt automatisch, wenn sie schlechter wird |
  | Ausgangsland | Die gewählte Region | Bei gewählter Region China: wählt nur unter Leitungen in China, der Ausgang bleibt in China; bei gewählter ausländischer Region: wählt unter allen ausländischen Leitungen, und **das Ausgangsland kann von der gewählten Region abweichen** (zum Beispiel Japan gewählt, tatsächlich aber Ausgang in Singapur) |
  | Geeignet für | Situationen, die ein festes Land brauchen: Streamingdienste eines bestimmten Landes, Banken und Konten, die auf die Region achten | Ein instabiles Heimnetz oder eine Region, die oft ruckelt – wenn Sie nur Tempo wollen und das Ausgangsland egal ist |

  Wenn Sie den Schalter umlegen, zeigt die Verwaltungsseite „Switching automatic selection…“ (automatische Auswahl wird umgeschaltet) und sperrt die Seite, bis der Wechsel abgeschlossen ist. In dieser Zeit bricht das Netz kurz ab, das ist normal. „Current exit“ (aktueller Ausgang) auf der Verwaltungsseite zeigt, welche Leitung tatsächlich genutzt wird.
- **Admin-Passwort und WLAN-Passwort**: Die Werkswerte sind öffentlich bekannte Standardwerte; ändern Sie sie gleich nach der ersten Anmeldung.

## Fernseher, TV-Boxen und die Geräte älterer Familienmitglieder

- Einfach mit dem WLAN dieses Routers oder per Kabel verbinden, dann spielt die Festlandchina-Version einer App sofort ab; die internationalen Versionen (iQIYI, WeTV) haben einen anderen Katalog, installieren Sie also die Festlandchina-Version.
- Ein Gerät ist verbunden, läuft aber nicht über das VPN, oder gesperrte Websites öffnen sich nicht, während alles andere funktioniert: Höchstwahrscheinlich hat es ein eigenes privates DNS eingestellt (Android „Privates DNS“, sicheres DNS im Browser), sodass der Router nicht sieht, welche Website es abfragt; schalten Sie das aus.
- Ein Gerät soll immer direkt verbinden (etwa ein Dienstrechner, der ins Firmen-VPN muss): Lassen Sie es mit dem WLAN des vorgeschalteten Routers oder des Modems verbinden.

## Häufige Fragen

**Kann ich im Tarif Persönlich einen Router nutzen?** Ja. Persönlich, Familie und Unternehmen unterstützen alle einen Router, ein Tarifwechsel ist nicht nötig.

**Wie viele Geräteplätze belegt der Router?** Einen; die Geräte dahinter werden nicht mitgezählt.

**Hat die Firmware eine Hintertür?** Sie wird aus OpenWrt kompiliert; hinzugefügt sind nur die Komponente, die sich mit dem VPN verbindet, und die Split-Routing-Regeln. Das VPN protokolliert für die Abrechnung nur Verbindungsdauer und Gesamtdatenvolumen.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=router-08)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=router-08) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – dauerhaft gültig

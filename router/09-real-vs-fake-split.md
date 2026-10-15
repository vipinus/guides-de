# 09 · Wie das Split-Routing des Routers funktioniert

> Version auf der Website (ausführlicher): https://www.leotun.com/de/guides/router-smart-split?utm_source=github&utm_content=router-09

Alle nennen es „intelligentes Split-Routing“, und doch fühlen sich manche Router einfach umständlich an. Was Split-Routing ist, steht in [03](03-router-split-routing.md); dieser Artikel behandelt nur, was Split-Routing leisten sollte, welche Symptome Sie sehen, wenn ein Teil davon fehlt, und wie unser Router es umsetzt.

## In einem Satz

Was Split-Routing leisten sollte: Jede Website läuft **samt ihren Bildern, Videos und ihrer Anmeldung** je nach Standort über das VPN oder direkt, und **alle Geräte im Haushalt folgen denselben Regeln**. Wird nur ein Teil davon umgesetzt, sehen Sie die Symptome unten.

## Symptome im Vergleich

| Was Sie sehen | Was dahintersteckt |
|---|---|
| Mit eingeschaltetem Split-Routing werden chinesische Websites sogar langsamer | Chinesische Websites werden für ausländische gehalten und machen den ganzen Umweg ins Ausland und zurück |
| Die Webseite öffnet sich, aber das Video dreht sich endlos, Bilder erscheinen nicht, die Anmeldung hängt | Die Liste enthält nur die Hauptseite; Videos, Bilder und Anmeldung derselben Website nehmen einen anderen Weg |
| Sie sind im Ausland, die Leitung nach China ist an, und die Video-App meldet trotzdem „仅限中国大陆“ (nur Festlandchina) | Ein Teil des Datenverkehrs ist nicht ins VPN gelangt, und die Website hat eine ausländische Adresse gesehen |
| Auf dem Smartphone läuft es, auf Fernseher oder TV-Box nicht; ein Computer geht einfach nicht über das VPN | Dieses Gerät hat eigene Netzwerkeinstellungen und umgeht den Router |
| Banking- und Zahlungs-Apps warnen immer wieder vor einer „Anmeldung von einem anderen Ort“ | Der Datenverkehr derselben App geht mal aus China, mal aus dem Ausland hinaus |
| Das Split-Routing verschwindet während der Nutzung (nach einem Neustart oder Neuverbinden läuft entweder alles über das VPN oder nichts) | Die Einstellung wurde nicht gespeichert |

Keines davon **erzeugt eine Fehlermeldung**. Der Router zeigt die ganze Zeit „Connected“ (verbunden), was die Fehlersuche besonders schwer macht, und viele halten am Ende die Leitung für schlecht.

## Was Split-Routing leisten sollte

- Eine Website geht mit Webseiten, Bildern, Videos und Anmeldung einen gemeinsamen Weg, ohne aufgeteilt zu werden
- Bei der Entscheidung „chinesisch oder ausländisch“ steht es auf der richtigen Seite, und chinesische Websites machen keinen Umweg
- Alle Geräte im Haushalt folgen denselben Regeln; Netzwerkeinstellungen, die am Gerät selbst geändert wurden, können sie nicht umgehen
- Die Richtung wechselt automatisch mit der gewählten Region (Zugriff auf China aus dem Ausland und Zugriff auf ausländische Dienste aus China sind zwei entgegengesetzte Regelsätze)
- Die Liste aktualisiert sich selbst, neu flashen ist nicht nötig
- Einstellungen werden gespeichert: nach Neustart oder Neuverbinden unverändert; und einmal ausgeschaltet, wird es nicht heimlich wieder eingeschaltet

## Intelligentes Split-Routing auf unserem Router

| | So ist es umgesetzt |
|---|---|
| Schalter | Standardmäßig an; Region in China gewählt = Richtung „aus dem Ausland China erreichen“, Auslandsregion gewählt = Richtung „aus China ausländische Dienste erreichen“, automatisch angewendet. Für die Richtung „aus China ausländische Dienste erreichen“ gibt es zusätzlich das Kontrollkästchen „Blocked sites only“ (nur gesperrte Websites; „VPN settings“ (VPN-Einstellungen) → intelligentes Split-Routing), standardmäßig angehakt; ohne Häkchen = chinesische Websites direkt, alles andere über das VPN. Firmware, die vor Oktober 2026 geflasht wurde, zeigt dieses Kontrollkästchen noch nicht an; der Kundenservice kann es aus der Ferne ändern |
| Liste | Nach „ganzer Website“ organisiert: Die Webseiten gehen zusammen mit den Video-, Bild- und Anmeldequellen, die sie nutzen |
| Aus China ausländische Dienste erreichen | Standardmäßig laufen nur gesperrte Websites und Dienste über das VPN (anhand einer täglich automatisch aktualisierten Liste gesperrter Websites plus Diensten wie Telegram, die sich mit festen Adressen verbinden); chinesische Websites und ausländische Websites, die sich in China ohnehin öffnen (Websites ausländischer Firmen, Downloads von Apple und Microsoft, Spieleplattformen), verbinden sich direkt ohne Umweg, genauso schnell wie ohne Router |
| Geräte zu Hause | Werden einheitlich übernommen; auch am Gerät selbst geänderte Netzwerkeinstellungen folgen den Regeln; es gibt keine „Hintertür“ am Router vorbei |
| Updates | Liste und Regeln aktualisieren sich beim Start des Routers automatisch; die Liste gesperrter Websites zusätzlich täglich |
| Speicher | Bleibt nach Neuverbinden oder Neustart erhalten; einmal aus, bleibt es aus |
| Lokales Netz | Drucker, NAS und Kameras werden wie gewohnt direkt erreicht |

**Der eine Fall, in dem Sie helfen müssen**: Ist auf einem Smartphone oder im Browser eine verschlüsselnde Einstellung wie „Privates DNS“ oder „Sicheres DNS“ eingeschaltet, verschlüsselt das Gerät seine Namensabfragen selbst, und der Router sieht sie nicht. Verhält sich ein Gerät seltsam oder öffnen sich gesperrte Websites nicht, während alles andere geht, schalten Sie diese Einstellung zuerst aus.

## Selbst überprüfen

1. Sie sind in China (Zugriff auf ausländische Dienste): Baidu und Taobao sowie ausländische Seiten, die sich in China ohnehin öffnen, etwa Downloads von Apple und Microsoft, laufen in normalem Tempo; gesperrte ausländische Websites öffnen sich, und Videos spielen ab.
2. Sie sind im Ausland (Zugriff auf China): Eine beliebige Folge auf Tencent Video oder iQIYI spielt ab, ohne die Meldung „仅限中国大陆“ (nur Festlandchina); lokale Bank- und Shopping-Websites funktionieren wie gewohnt.
3. Probieren Sie jedes Gerät aus, vor allem Fernseher und TV-Box; bei einem, das sich seltsam verhält, prüfen Sie zuerst „Privates DNS / Sicheres DNS“ und dann, ob es mit dem WLAN dieses Routers verbunden ist und nicht mit dem des Modems.
4. Eine Website öffnet sich mit Split-Routing nicht: Schalten Sie vorübergehend auf „Global“. Öffnet sie sich unter Global, aber nicht mit Split-Routing, steht sie noch nicht auf der Liste; schicken Sie die Adresse an den Kundenservice, damit sie aufgenommen wird – sie kommt dann mit dem automatischen Update. In China können Sie auch im Abschnitt für intelligentes Split-Routing das Häkchen bei „Blocked sites only“ entfernen und es erneut versuchen; öffnet sie sich dann, ist sie ebenfalls gesperrt, steht aber noch nicht auf der Liste.

## Häufige Fragen

**Muss ich das intelligente Split-Routing selbst einschalten?** Nein. Es ist an, sobald Sie sich mit Ihrem Konto anmelden und eine Region wählen.

**Müssen „aus dem Ausland China erreichen“ und „aus China ausländische Dienste erreichen“ getrennt eingerichtet werden?** Nein. Die Richtung ergibt sich automatisch aus der gewählten Region.

**Wirkt es sich auf Drucker oder NAS aus?** Nein. Geräte im Heimnetz werden wie gewohnt direkt erreicht.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=router-09)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=router-09) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 24-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide 20 Tage im Tarif Persönlich – ein dauerhaftes Angebot

# 02 · Mit China verbunden, aber trotzdem kein Video: was tun

Prüfen Sie der Reihe nach. Jeder Schritt dauert etwa eine Minute.

1. **Prüfen Sie, ob sich die Ausgangs-IP wirklich geändert hat.** Öffnen Sie im Browser eine Website, die den Standort Ihrer IP anzeigt, und sehen Sie nach, ob dort Festlandchina steht. Falls nicht, greift das VPN nicht; verbinden Sie sich neu.
2. **IPv6- und DNS-Lecks.** Stimmt die Ausgangs-IP, hält die Website Sie aber trotzdem für jemanden im Ausland, umgehen höchstwahrscheinlich IPv6 oder der lokale DNS des Geräts das VPN. Das ist der häufigste Fall, und er hat einen eigenen Artikel: [03 · IPv6 und DNS schlüpfen durch](03-ipv6-and-dns-leak.md).
3. **App-Cache.** Video- und Musik-Apps merken sich das Ergebnis ihrer Regionsprüfung. Beenden Sie die App vollständig und öffnen Sie sie erneut; hilft das nicht, löschen Sie die App-Daten.
4. **App-Version.** Haben Sie die internationale Version installiert (iQIYI, WeTV), ist das Angebot ein anderes. Wechseln Sie zur Version für Festlandchina.
5. **Registrierungsregion des Kontos.** Einige Plattformen beschränken Inhalte nach der Region, in der das Konto registriert wurde – unabhängig von Ihrer aktuellen IP. Dann hilft nur ein anderes Konto.
6. **Systemregion und -sprache.** Manche Apps lesen die Region des Systems aus. Stellen Sie die Systemregion auf China um und versuchen Sie es erneut.
7. **Einstiegsregion.** Manche Inhalte unterscheiden sich auch je nach Provinz der IP. Wechseln Sie zu einem anderen Einstiegspunkt und versuchen Sie es erneut.

## Klappt es immer noch nicht

Nennen Sie dem Support diese vier Dinge: die Ziel-Website oder -App, den genauen Wortlaut der Fehlermeldung, wo Ihre aktuelle Ausgangs-IP liegt und welche Verbindungsart Sie nutzen. Damit lässt sich das Problem in einem Zug eingrenzen.

---
Zusammengestellt vom [LeoTun](https://www.leotun.com/de?utm_source=github&utm_content=troubleshooting-02)-Team · Fragen? Siehe die [Kontaktseite](https://www.leotun.com/de/contact?utm_source=github&utm_content=troubleshooting-02) (Gruppen, E-Mail und Support sind dort aufgeführt) · Registrieren Sie sich für einen 4-stündigen Gratistest; laden Sie einen Freund ein, der bezahlt, erhalten Sie beide je 15 Punkte (etwa 15 Tage im Tarif Persönlich) – ein dauerhaftes Angebot

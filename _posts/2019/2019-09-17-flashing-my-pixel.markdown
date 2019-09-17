---
layout: post
title:  "Flashing my Pixel 3a"
date:   2019-09-17
categories: privacy tech
---
# Generelles
In letzter Zeit habe ich mir sehr viele Gedanken über das Thema Privacy gemacht. Nach der Löschung einiger Social Media Konten (Instagram, Facebook, Last.fm etc.) war der nächste Schritt, dass ich mein Handy flashen wollte um auf das Android Open Source Project (AOSP, [https://source.android.com/](https://source.android.com/) umzusteigen. Zur Erklärung sei gesagt, dass Android generell erst einmal ein Open Source Projekt ist. Google stellt dann ein Image bereit, welches neben AOSP auch verschiedene Google Dienste, die sogenannten Play Dienste beinhaltet. Zu finden sind diese beispielsweise hier: [https://play.google.com/store/apps/details?id=com.google.android.gms](https://play.google.com/store/apps/details?id=com.google.android.gms).

Da ich mir nicht sicher sein konnte, welche Daten Google sonst noch erhebt, wollte ich mich ein bisschen unabhängiger von Google aufstellen. Erschwerend kam hinzu, dass ich privat ein Google Pixel 3A habe, welches noch viel mehr von Google verwaltet wird und sicher einige Daten mehr erhebt.

Nach einiger Recherche bin ich dann auf GrapheneOS gestoßen ([https://grapheneos.org/](https://grapheneos.org/) und [https://www.reddit.com/r/GrapheneOS/](https://www.reddit.com/r/GrapheneOS/) ). Hierbei handelt es sich um ein Open Source Projekt, welches AOSP noch einmal härtet ([https://de.wikipedia.org/wiki/H%C3%A4rten_(Computer)](https://de.wikipedia.org/wiki/H%C3%A4rten_(Computer)) und dann für die Pixel-Geräte bereitstellt. Da das Projekt noch in den Anfängen steckt sind nur wenige Geräte supportet, das Pixel 3A gehört aber zum Glück dazu.

## Flashen
Nachdem ich alle Backups gemacht habe (erstaunlich, was sich über die Zeit so alles auf einem Telefon ansammelt), stand dann das flashen an. Dies bedeutet, dass ich ein neues Image auf das Handy spiele, was jedoch mit jeglichem Verlust der Garantie einhergeht. Nachdem ich also das Android SDK installiert habe, konnte ich der sehr gut dokumentierten Anleitung auf [https://grapheneos.org/install](https://grapheneos.org/install) folgen. 
Im Wesentlichen wird das Handy in das Bootloader Interface gebootet, ehe man dann den Bootloader unlockt mittels `fastboot flashing unlock`. Anschließend flasht man das neue Image und kann den bootloader wieder locken. Sollte ein Garantiefall eintreten, so kann man auch die Factory Images wieder aufspielen, da Google diese für die Pixel Telefone bereitstellt unter [https://developers.google.com/android/images](https://developers.google.com/android/images). 

## Setup
Da man jetzt keinen Zugriff mehr auf den Google App Store hat muss man die Apps anderweitig installieren. Für Open Source und privacy-freundliche Apps empfiehlt sich der F-Droid-Store, den man von [https://f-droid.org/](https://f-droid.org/) laden kann.
Sollte man anschließend doch noch einige Dienste aus dem Google Play Store benötigen, so gibt es auch dort Apps, die einen Zugang zum Playstore bereitstellen.

## Was gut läuft
Vieles. Ich bin positiv überrascht, wie gut vieles läuft und wie wenig ich doch auf die Google Services angewiesen bin. Bin ich im Zweifel, ob die App nicht doch zu viele Tracker mitbringt, dann überprüfe ich die App mit einem Privacy Checker, über den ich bei Gelegenheit sicher auch noch einmal etwas schreiben werde.

## Was nicht so gut läuft
Navigation. Ich habe mich doch immer sehr auf Google Maps verlassen, denn besonders die Live-Daten sind sehr genau und zuverlässig. Für die vor Ort Navigation kann ich OpenStreetMaps wirklich sehr empfehlen, da dort viele Details eingetragen sind, die man in Google Maps vergeblich sucht wie zum Beispiel Fahrradständer. Enttäuschend ist für mich, dass ich zum Beispiel in Signal keinen Standort mehr verschicken kann, da diese eine Abhängigkeit zu Google Maps haben und keine Alternative anbieten. Ein weiterer großer Minuspunkt ist, dass meine Banking-App nicht mehr funktioniert, da sich viele dieser Apps auf die Play Services verlassen. Aber auch hier gab es eine Lösung.
Und zu guter Letzt natürlich die bittere Erkenntnis, dass man ohne Whatsapp doch sehr abgeschnitten von der Außenwelt ist, da immer noch viel zu viele auf dieser Datenkranke von Facebook beharren.

## Meine Apps (teilweise mit Links)

Hier ist eine nicht vollständige Liste meiner Apps, die ich verwende. 
- andOTP wichtig für die Zweifaktor-Authentifizierung, die ich bei vielen Diensten aktiviert habe, zu finden beispielsweise hier: [Link](https://f-droid.org/packages/org.shadowice.flocke.andotp/)
- Antennapod für Podcasts [Link](https://f-droid.org/de/packages/de.danoeh.antennapod/)
- AnySoftKeyboard als Tastatur [Link](https://f-droid.org/de/packages/com.anysoftkeyboard.languagepack.german/)
- AuroraStore als Zugang zum PlayStore [Link](https://f-droid.org/de/packages/com.aurora.store/)
- Bitwarden als Passwort-Manager [Link](https://play.google.com/store/apps/details?id=com.x8bit.bitwarden)
- BookReader als PDF-Reader [Link](https://f-droid.org/de/packages/com.github.axet.bookreader/)
- Bromite als Privacy freundlicher Browser auf Chromium Basis [Link](https://www.bromite.org/)
- c:geo für Geocaching [Link](https://play.google.com/store/apps/details?id=cgeo.geocaching)
- DAVx5 zur Synchronisierung meiner Kontakte und Kalender [Link](https://f-droid.org/de/packages/at.bitfire.davdroid/)
- Exodus Privacy zum Überprüfen von Trackern [Link](https://f-droid.org/de/packages/org.eu.exodus_privacy.exodusprivacy/)
- FairEmail als EmailClient [Link](https://f-droid.org/de/packages/eu.faircode.email/)
- Gallery zum betrachten der Fotos [Link](https://f-droid.org/de/packages/com.simplemobiletools.gallery.pro/)
- Nextcloud als Client für die eigene Cloud [Link](https://f-droid.org/de/packages/com.nextcloud.client/)
- Open Camera als Kamera-Alternative mit vielen Einstellungsmöglichkeiten [Link](https://f-droid.org/de/packages/net.sourceforge.opencamera/)
- OsmAnd+ für Navigation [Link](https://f-droid.org/de/packages/net.osmand.plus/)
- Signal [Link](https://play.google.com/store/apps/details?id=org.thoughtcrime.securesms)
- Slide als Reddit-Client [Link](https://f-droid.org/de/packages/me.ccrama.redditslide/)
- Whatsapp [Link](https://play.google.com/store/apps/details?id=com.whatsapp)

## Fazit
Sicher nicht die perfekte Lösung, die ich hier habe und sicher bin ich auch immer noch zu tracken. Bisher gefällt mir das Setup aber sehr gut und ich denke ich hinterlasse ein paar Datenspuren weniger. Da sich auch gleichzeitig die Akkulaufzeit meines Telefons verlängert hat, bin ich bisher sehr glücklich mit meiner Entscheidung. Ich bin gespannt, wie ich es in ein paar Monaten sehe und ob ich noch einmal den Schritt zurück gehen werde.
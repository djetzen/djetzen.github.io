---
layout: post
title:  "Anonymer Zugriff auf den PlayStore"
date:   2020-05-13
categories: privacy
---
# Anonym auf den Google Play Store zugreifen
Ich habe ja schon in einem vergangenen [Post](https://www.djetzen.de/privacy/tech/2019/09/17/flashing-my-pixel.html) darüber berichtet, dass ich auf mein Phone eine ROM geflasht habe, die keine Google Play Services beinhaltet. 
Heute wollte ich kurz erklären, wie ich trotzdem auf den Google PlayStore zugreifen kann um Apps zu installieren, die nur dort verfügbar sind.
Eine mögliche Alternative wäre gewesen, dass ich mir aus ominösen Quellen direkt die Pakete besorge und installiere, habe mich aber aus verschiedenen Gründen dagegen entschieden.

## F-Droid
Die erstbeste Alternative für mich ist der [F-Droid Store](https://f-droid.org/). Dort bekommt man zwar keine Apps vom PlayStore, kann jedoch viele OpenSource Apps laden, die die meisten Funktionalitäten abdecken. Ich beziehe circa 80% meiner Apps von dort. Die restlichen 20% - die nicht OpenSource sind oder dort nicht verfügbar - beziehe ich aus dem PlayStore. Kandidaten hierfür sind zum Beispiel Signal, Whatsapp oder die Apps für den ÖPNV.

## AuroraStore
Um doch auf den PlayStore zuzugreifen, habe ich über F-Droid den AuroraStore installiert, der hier auf [Gitlab ](https://gitlab.com/AuroraOSS) zu finden ist. Mit diesem alternativen Frontend kann man auf den PlayStore zugreifen ohne die Google Play Services auf dem Gerät zu haben.
Als besonderes Feature wird ein anonymer Login angeboten, so dass man auch gänzlich ohne einen Google Account auf den Store zugreifen kann. Man kann zwar auch seinen eigenen Account nutzen, dies verstößt jedoch gegen die AGB des PlayStore und kann so zur Sperrung des Accounts führen. Mein eigener Account wurde in der Vergangenheit zwar nicht gesperrt, jedoch benutze ich seit einigen Monaten den anonymen Account, so dass ich aktuell mein Phone komplett ohne Google Account betreiben kann.

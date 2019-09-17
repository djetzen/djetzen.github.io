---
layout: post
title:  "Unbekannte Docker Commands"
date:   2019-08-15
categories: programming
---
# Überblick
Benutzt man die Docker-CLI (Command Line Interface), so denkt man doch oft an die gängigen Begriffe. Viele wissen, wie man Container startet, Images baut oder sich eine Liste von beidem anzeigen lässt. Für viele Anwendungsfälle reicht auch genau das aus. Beim Blättern in der Dokumentation der CLI bin ich jedoch über einige weitere Befehle gestolpert, die ich hier vorstellen möchte.

## Docker Events
Möchte man sich einmal genauer ansehen welche Events in der Docker Engine genau passieren, so kann der Befehl `docker events` sehr hilfreich sein. Bei Bedarf - da sehr viele Events auftreten - kann man filtern, das passiert dann zum Beispiel so: `docker events --filter event=health_status`. Mit diesem Befehl werden nur Events angezeigt, bei denen sich der `health_status` ändert.

## Docker stats
Taskmanager kennt jeder und eine vereinfachte Oberfläche dafür hat auch Docker. Wenn man genaueres über den Ressourcenverbrauch von einzelnen Containern wissen möchte, so ist `docker stats` der Befehl der Wahl. Für jeden Container werden hier die benötigten Ressourcen angezeigt.

## Docker diff
Mit dem Befehl `docker diff <container>` kann man sich die Änderungen anzeigen lassen, die innerhalb eines Containers im Filesystem vollzogen werden. Geben wir für einen nginx-Container diesen Befehl ein, so erhalten wir beispielsweise den folgenden Output:
```
C /run
A /run/nginx.pid
C /var
C /var/cache
C /var/cache/nginx
A /var/cache/nginx/uwsgi_temp
A /var/cache/nginx/client_temp
A /var/cache/nginx/fastcgi_temp
A /var/cache/nginx/proxy_temp
A /var/cache/nginx/scgi_temp
```
Jede Zeile, die mit einem C beginnt beschreibt eine geänderte (changed) Datei, jede Zeile mit A eine Datei die hinzugefügt (added) wurde. Beginnt die Zeile mit D, ist die jeweilige Datei gelöscht (deleted).

## Docker top
Wer schon immer mal wissen wollte, wie viele und welche Prozess in einem Container laufen kann sich das mit `docker top <container>` anzeigen lassen. Hier der Output für einen Container dem nginx zugrunde liegt.
```
PID                 USER                TIME                COMMAND
14811               root                0:00                nginx: master process nginx -g daemon off;
14937               101                 0:00                nginx: worker process
```

## Docker rename
Mir bisher komplett unbekannt war die Möglichkeit, dass man einen Container umbenennen kann. Ganz einfach geht es mit diesem Befehl: `docker rename <oldName> <newName>`

## Docker port
Eine spezielle Anzeige für jeden einzelnen Port bekommt man mit `docker port <container>`. Diese Information ist zwar auch in `docker container ls` verfügbar, aber teilweise doch sehr unübersichtlich.

## Docker History
Der letzte Befehl in der Liste zeigt die Historie eines images an. Für den Container nginx sieht es zum jetzigen Zeitpunkt folgendermaßen aus:
```
IMAGE               CREATED             CREATED BY                                      SIZE                COMMENT
4733136e5c3c        32 hours ago        /bin/sh -c #(nop)  CMD ["nginx" "-g" "daemon…   0B                  
<missing>           32 hours ago        /bin/sh -c #(nop)  STOPSIGNAL SIGTERM           0B                  
<missing>           32 hours ago        /bin/sh -c #(nop)  EXPOSE 80                    0B                  
<missing>           32 hours ago        /bin/sh -c ln -sf /dev/stdout /var/log/nginx…   22B                 
<missing>           32 hours ago        /bin/sh -c set -x     && addgroup --system -…   56.6MB              
<missing>           32 hours ago        /bin/sh -c #(nop)  ENV PKG_RELEASE=1~buster     0B                  
<missing>           32 hours ago        /bin/sh -c #(nop)  ENV NJS_VERSION=0.3.3        0B                  
<missing>           32 hours ago        /bin/sh -c #(nop)  ENV NGINX_VERSION=1.17.2     0B                  
<missing>           32 hours ago        /bin/sh -c #(nop)  LABEL maintainer=NGINX Do…   0B                  
<missing>           39 hours ago        /bin/sh -c #(nop)  CMD ["bash"]                 0B                  
<missing>           39 hours ago        /bin/sh -c #(nop) ADD file:330bfb91168adb4a9…   69.2MB   
```
Mit diesem Befehl kann man genau sehen, wann und mit welcher Änderung das image zuletzte aktualisiert wurde.

# Zusammenfassung
Viele Befehle kennt man und benutzt man in der täglichen Arbeit mit Docker. Doch gerade wenn man sich die Dokumentation mit `docker --help` einmal genauer ansieht, dann fällt einem auf wie mächtig die CLI ist und welche Befehle man doch nicht kennt oder noch nie gesehen hat. Ich hoffe ich konnte hier einen kurzen Überblick geben und euch eventuell ein paar Kommandos vorstellen, die ihr so noch nicht kanntet.
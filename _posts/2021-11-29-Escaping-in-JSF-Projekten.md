---
layout: post
title: Escaping in JSF Projekten
---

## Aufgabenstellung und Ziele
**Was ist JSF?** 
JSF ist eine Java-Bibliothek, die einem hilft Webseiten zu erstellen mit Hilfe von Java/Jakarta. Der volle Name ausgschrieben ist JavaServer Faces (Jakarta Server Faces). 
Damit kann man grafische Benutzeroberflächen für Webanwendungen entwickeln. Grundlagen für JSF sind Kenntnisse mit `Java`, `HTML/CSS (HTTP)`. 
Man braucht auch ein JDK und ein Servlet-Container wie zum Beispiel Apache Tomcat.

**Was ist Escaping?**
Escaping ist eine Sicherheitsmethode, die ziemlich wichtig ist. Escaping erlaubt es Nutzern nicht Skripte in Suchfeldern oder generell Textfeldern zu schreiben. Ohne Escaping 
könnte man in einer Datenbank oder in einem Suchfeld ein Skript schreiben, das grosse Auswirkungen auf die Applikation haben kann. Man könnte DDOS werden genau so wie alle Benutzer.
Jeder bekommt beim Starten ein Pop-up, das zum Beispiel sagt: Holen sie sich essen. Mit Skripts kann man natürlich verheerenderes anrichten als nur ein Pop-up. 
Mit Escaping ist das nicht möglich. Für spezielle Zeichen gibt man als Ersetzung neue Zeichen ein, das automatisch passiert (zum Beispiel. < --> &gt)

**Aufgabenstellung**
In JSF Escaping zu aktivieren ist ziemlich simpel und es löst auch direkt das Problem. Aber es ist nur eine Sicherheitsmethode und es müssen noch sehr viel mehr implementiert 
werden. In diesem Portfolio schauen wir an, wie man in JSF Escaping aktiviert. Dafür braucht man kein `Java` sondern nur die `.xhtml`-Seite, in der man Escaping aktivieren muss.
Am besten aktiviert man das überall, wo man etwas per Text eingeben kann.

**Ziele**
1.) Escaping aktiviert in einem JSF Projekt
2.) Alle Art Skripte werden als normaler Text eingegeben


## Produkt
**Programm**
Das Programm muss man nur in der `.xhtml`-Seite umsetzen.
```xhtml
<h:outputText value="#{newsitem.detail}" escape="true"/>
```

**Beschreibung**
Nun wird alles als Text ausgegeben, sogar die möglichen Skripte, die man hätte schreiben können. Das Escaping ist leider nur möglich bei dem Code outputText und sonst nicht.
Um etwas auszugeben, muss man so oder so outputText eingeben, weswegen das Problem theoretisch gelöst ist. Für Datenbanken muss man aber eine andere Sicherheitsmethode verwenden.
Das Escaping wir jedes Mal verwendet, weil das eine der einfachsten und wichtigsten Sicherheitsmethoden ist, die man nutzen sollte.

## Reflexion und Auswertung
**Reflexion**
Ich hatte keine Probleme das Escaping zu aktivieren, aber die entsprechenden Orte zu finden war schwer. Das Escaping in JSF zu aktivieren ist einfach, aber ich weiss nicht, wie
es auf einer normalen Webseite ohne JSF gehen sollte. Das einzige Problem wird sein das Escaping auf anderen Projekten ohne JSF zu aktivieren.

**Auswertung**
1.) Der Text, wenn ein Skript eingegeben wird, sieht so aus.
![Skript](https://github.com/AltayMetehan/AltayMetehan.github.io/blob/70ff7f23133f1c1e6344e63dea9ff1f0c0705723/images/skript.PNG)
2.) Das Escaping in JSF wird so aktiviert.
![Escaping](https://github.com/AltayMetehan/AltayMetehan.github.io/blob/70ff7f23133f1c1e6344e63dea9ff1f0c0705723/images/escaping.PNG)

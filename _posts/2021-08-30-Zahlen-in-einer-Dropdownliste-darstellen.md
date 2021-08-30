---
layout: post
title: Zahlen in einer Dropdownliste darstellen (JSF)
---

## Aufgabenstellung und Ziele
**Was ist JSF?** 
JSF ist eine Java-Bibliothek, die einem hilft Webseiten zu erstellen mit Hilfe von Java/Jakarta. Der volle Name ausgschrieben ist JavaServer Faces (Jakarta Server Faces). 
Damit kann man grafische Benutzeroberflächen für Webanwendungen entwickeln. Grundlagen für JSF sind Kenntnisse mit `Java`, `HTML/CSS (HTTP)`. 
Man braucht auch ein JDK und ein Servlet-Container wie zum Beispiel Apache Tomcat.

**Aufgabenstellung**
Um Zahlen in einer Dropdownliste zu repräsentieren, muss man in einer Javaklasse (einer Bean in JSF) die Zahlen erstellen und in `HTML` in einem Formular oder generell eine Dropdownliste generieren. 
In diesem Auftrag schauen wir dann, wie man es in `HTML` umsetzt und es in `Java` programmiert und beides dann zusammensetzt.

**Ziele**
1.) Eine Dropdownliste in `.xhtml` erstellen
2.) Zahlen darstellen können in der Dropdownliste


## Produkt
**Programm**
Das Programm ist erstellt in `.xhtml` und `Java`.
```java
@ManagedBean(name = "zahlenInDropdown")
@SessionScoped
public class ZahlenInDropdown implements Serializable{
    private List<Integer> zahl;
    
    public ZahlenInDropdown(){
        this.zahl = new ArrayList();
        for (int i = 0; i < 256; i++){
            this.zahl.add(i);
        }
    }
    
    public List<Integer> getZahl(){
        return this.zahl;
    }
}
```

```xhtml
<h:body>
    <h:form>
        <h:selectOneMenu id="zahl" value="irgendetwas">
            <f:selectItems value="#{zahlenInDropdown.zahl}" />
        </h:selectOneMenu>
    </h:form>
</h:body>
```

**Beschreibung**
Das Produkt zeigt in einer Webseite eine Dropdownliste, die Zahlen zeigt. 
Die Zahlen variieren zwischen 0 und 255 und man kann dazwischen auswählen, welche Zahl man will. 
Dies wird oft in einem Formular genutzt, wenn man zwischen vielen Zahlen wählen sollte.


## Reflexion und Verifikation
**Reflexion**
Ich hatte Probleme dabei, wie ich die Zahlen in die Dropdownliste einfüge, obwohl es so simpel war. 
Ich hatte vergessen, in der Bean die Zahlen in die ArrayListe zu packen, weswegen es nicht gezeigt hat. 
Bei xhtml konnte ich alles implementieren. 

**Verifikation**
1.) Wenn man diesen Code austestet, sieht man, dass eine Dropdownliste erstellt worden ist.
2.) Wenn man auf die Dropdownliste klickt, sieht man die Zahlen zwischen 0 und 255 auftauchen.
![Dropdownmenü](https://github.com/AltayMetehan/AltayMetehan.github.io/raw/master/images/Screenshot%20(1).png)
*Ich würde gerne Bilder einfügen für die Verifikation, aber es ging nicht.*

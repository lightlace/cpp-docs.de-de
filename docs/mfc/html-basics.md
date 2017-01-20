---
title: "Grundlagen zu HTML"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HTML, Informationen über HTML"
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
caps.latest.revision: 7
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# Grundlagen zu HTML
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die meisten Browser verfügen die Untersuchung der HTML\-Quelle der Seiten, die Sie durchsuchen.  Wenn Sie die Quelle anzeigen, die Sie mehrere Tags HTML \(Hypertext Markup Language\) anzuzeigen, eingeschlossen von der spitzen Klammern \(\<\>\), kombiniert mit Text.  
  
 Die Schritte mit HTML\-Tags, um eine einfache Webseite erstellen.  In folgenden Schritte geben Sie Nur\-Text in eine Datei im Editor ein, nehmen mehrere Änderungen eingeführt, die Datei speichern und laden die Seite erneut in den Browser, um die Änderungen anzuzeigen.  
  
#### So erstellen Sie eine HTML\-Datei  
  
1.  Öffnen Sie Editor oder einen beliebigen Text\-Editor.  
  
2.  Wählen Sie im Menü **Datei**  die Option `New` aus.  
  
3.  Geben Sie die folgenden Zeilen ein:  
  
    ```  
    <HTML>  
    <HEAD>  
    <TITLE>Top HTML Tags</TITLE>  
    </HEAD>  
    </HTML>  
    ```  
  
4.  Wählen Sie im Menü **Datei**  wählen Sie **Speichern** aus und speichern Sie die Datei als c:\\webpages\\First.htm.  Lassen Sie die Datei im Editor geöffnet.  
  
5.  Zu dem Browser und dem Menü **Datei** , wählen **Öffnen** aus oder geben `file://C:/webpages/first.htm` im URL\-Eingabefeld des Browsers ein.  Sie sollten eine leere Seite mit dem Fenster finden, "oberste HTML\-Tags zu untertiteln."  
  
     Beachten Sie die Tags werden verknüpft und enthalten werden in spitzen Klammern.  Tags die Groß\-\/Kleinschreibung nicht beachtet, aber Großschreibung wird häufig verwendet, Tags out kommunizieren zu können.  
  
     Das Tag \<HTML\> beginnt das Dokument, und Tag \<\/HTML\> beendet sie.  Die Endtags \(nicht immer erforderlich\) sind die gleichen wie das Startfarbe Tag, jedoch besitzen einen Schrägstrich \(\/\) vor den Tag.  Es darf keine Leerzeichen zwischen der spitze Klammer \(\<\) und dem Beginn des Tags geben.  
  
6.  Wechseln Sie wieder zum Editor und nach \/HEAD\-\> die \<Zeile, Typ:  
  
    ```  
    <BODY>  
    HTML is swell.  
    Life is good.  
    </BODY>  
    ```  
  
7.  Wählen Sie im Menü **Datei** wählen Sie **Speichern** aus.  
  
8.  Wechseln Sie zurück zur Ihrem Browser und aktualisieren die Seite.  
  
     Die Wörter werden im Clientbereich der Browser Windows.  Beachten Sie, dass das Wagenrücklauf ignoriert wird.  Wenn Sie einen Zeilenumbruch möchten, müssen Sie ein `<BR>`\-Tag einfügen nach der ersten Zeile.  
  
     Für alle Schritte verwendet, die dem Text überall zwischen \<TEXT\> und \<\/BODY\> folgen, einfügen, um den Text des Dokuments einzufügen.  
  
9. Hinzufügen einer Kopf\- hinzu:  
  
    ```  
    <H3>Here's the big picture</H3>  
    ```  
  
10. Fügen Sie einem Bild, mit einer .gif\- Datei hinzu, die im selben Verzeichnis wie die Seite gespeichert:  
  
    ```  
    <IMG src="yourfile.gif">  
    ```  
  
11. Hinzufügen einer Liste hinzu:  
  
    ```  
    <UL>Make me an unordered list.  
    <LI>One programmer</LI>  
    <LI>Ten SDKs</LI>  
    <LI>Great Internet Apps</LI>  
    </UL>  
    ```  
  
12. Um die Liste stattdessen zu Zahlen, verwenden Sie für \<OL\> und \<\/OL\-\>\-Tags anstelle der \<UL\-\> und \<\/UL\-\>\-Tags.  
  
 Das sollte abgerufen hat.  Wenn Sie eine umfangreiche Funktion auf einer Webseite finden, können Sie ermitteln, wie sie erstellt wurde, indem die HTML\-Quelle eingecheckt hat.  HTML\-Editoren wie Microsoft Front Sie können verwendet werden, um einfachen und erweiterten Seiten erstellen.  
  
 Hier die gesamte HTML\-Quelle für die Datei, die Sie erstellt haben:  
  
```  
<HTML>  
<HEAD>  
<TITLE>Top HTML Tags</TITLE>  
</HEAD>  
<BODY>  
HTML is swell.<BR>  
Life is good.  
<H3>Here's the big picture</H3>  
<IMG src="yourfile.gif">  
<UL>Make me an unordered list.  
<LI>One programmer</LI>  
<LI>Ten SDKs</LI>  
<LI>Great Internet Apps</LI>  
</UL>  
</BODY>  
</HTML>  
```  
  
 Eine vollständige Beschreibung von Tags, finden Attribute und Erweiterungen, die Spezifikationen Hypertext Markup Language \(HTML\):  
  
 [http:\/\/www.w3.org\/pub\/WWW\/MarkUp\/](http://www.w3.org/pub/WWW/MarkUp/)  
  
## Siehe auch  
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)
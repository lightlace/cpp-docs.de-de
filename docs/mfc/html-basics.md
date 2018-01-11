---
title: Grundlagen zu HTML | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 852a4894478d139013d70813316976a20e99dd41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="html-basics"></a>Grundlagen zu HTML
Die meisten Browser haben die Möglichkeit die HTML-Quelle der Seiten, die Sie durchsuchen zu untersuchen. Bei der Anzeige der Quelle, sehen Sie eine Anzahl von Tags für HTML (Hypertext Markup Language), umgeben von spitzen Klammern (<>), kombiniert mit Text.  
  
 Die folgenden Schritte verwenden HTML-Tags, um eine einfache Webseite zu erstellen. In den folgenden Schritten müssen Sie geben nur-Text in eine Datei in Editor, ein paar Änderungen vornehmen, speichern Sie die Datei und laden die Seite im Browser, um Ihre Änderungen anzuzeigen.  
  
#### <a name="to-create-an-html-file"></a>So erstellen eine HTML-Datei  
  
1.  Öffnen Sie Editor oder einem nur-Text-Editor.  
  
2.  Aus der **Datei** Menü Wählen Sie `New`.  
  
3.  Geben Sie die folgenden Zeilen ein:  
  
 ```  
 <HTML>  
 <HEAD>  
 <TITLE>Top HTML Tags</TITLE>  
 </HEAD>  
 </HTML>  
 ```  
  
4.  Aus der **Datei** Menü wählen **speichern**, und speichern Sie die Datei als c:\webpages\First.htm. Lassen Sie die Datei im Editor geöffnet.  
  
5.  Wechseln Sie in den Browser, und aus der **Datei** Menü Wählen Sie **öffnen**, oder Typ `file://C:/webpages/first.htm` im Eingabefeld für den Browser-URL. Eine leere Seite mit der Beschriftung "Top HTML-Tags" sollte angezeigt werden.  
  
     Beachten Sie die Tags gekoppelt sind und in spitzen Klammern eingeschlossen werden. Tags sind nicht in der Groß-/Kleinschreibung beachtet, aber die Großschreibung wird häufig verwendet, um die Tags optisch hervorzuheben.  
  
     Das Tag \<HTML > beginnt mit der das Dokument und das Tag \<paarweise > beendet. Ende Tags (nicht immer erforderlich) sind identisch mit der Startkennzeichen, jedoch haben einen Schrägstrich (/) vor das Tag. Es darf kein Leerzeichen zwischen der Spitze Klammer (<) und dem Start der Ihr Tag.  
  
6.  Wechseln Sie zurück in den Editor, und klicken Sie nach der  \< /HEAD > Zeile, geben Sie:  
  
 ```  
 <BODY>  
    HTML is swell.  
    Life is good.  
 </BODY>  
 ```  
  
7.  Aus der **Datei** Menü wählen **speichern**.  
  
8.  Wechseln Sie zurück in den Browser, und aktualisieren Sie die Seite.  
  
     Die Wörter erscheint im Clientbereich des Fensters des Browsers ab. Beachten Sie, dass Ihre Wagenrücklauf ignoriert wird. Wenn ein Zeilenumbruch eingefügt werden sollen, müssen Sie enthalten eine `<BR>` Tag nach der ersten Zeile.  
  
     Die Schritte, die darauf folgen, fügen Sie den Text an einer beliebigen Stelle zwischen \<Text > und  \< /BODY > in den Text des Dokuments hinzufügen.  
  
9. Fügen Sie einen Header hinzu:  
  
 ```  
 <H3>Here's the big picture</H3>  
 ```  
  
10. Fügen Sie ein Bild, das mithilfe einer GIF-Datei im gleichen Verzeichnis wie die Seite gespeichert:  
  
 ```  
 <IMG src="yourfile.gif">  
 ```  
  
11. Fügen Sie eine Liste hinzu:  
  
 ```  
 <UL>Make me an unordered list.  
 <LI>One programmer</LI>  
 <LI>Ten SDKs</LI>  
 <LI>Great Internet Apps</LI>  
 </UL>  
 ```  
  
12. Verwenden, um die Liste stattdessen Zahl gekoppelt \<OL > und \</OL > anstelle von tags die \<UL > und  \< /UL > RFID-Transponder.  
  
 Die sollen Ihnen den Einstieg erleichtern. Wenn Sie eine großartige Funktion auf einer Webseite angezeigt wird, können Sie feststellen, wie sie mithilfe der HTML-Quelle erstellt wurde. HTML-Editoren, z. B. Microsoft Front Page können verwendet werden, um einfache und erweiterte Seiten zu erstellen.  
  
 Hier wird die gesamte HTML-Quelle für die Datei, die Sie soeben erstellt haben:  
  
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
  
 Eine vollständige Beschreibung des Tags, Attributen und Erweiterungen finden Sie in der Spezifikation Hypertext Markup Language (HTML):  
  
 [http://www.w3.org/pub/www/MarkUp/](http://www.w3.org/pub/www/markup/)  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)


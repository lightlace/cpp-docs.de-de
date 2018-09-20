---
title: Grundlagen zu HTML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b25f957615d738d0608f911736bb42f8e3731dd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391618"
---
# <a name="html-basics"></a>Grundlagen zu HTML

Die meisten Browser verfügen über eine Funktion untersuchen die HTML-Quelle der Seiten, die Sie durchsuchen. Beim Anzeigen der Quelle, die eine Anzahl von HTML (Hypertext Markup Language)-Tags angezeigt werden, die von spitzen Klammern (<>), zusammen mit Text umgeben werden.

Die folgenden Schritte verwenden HTML-Tags, um eine einfache Webseite zu erstellen. In den folgenden Schritten werden Sie geben nur-Text in eine Datei im Editor, nehmen einige Änderungen vor, speichern Sie die Datei und Laden Ihre Seite im Browser, um Ihre Änderungen anzuzeigen.

#### <a name="to-create-an-html-file"></a>Um eine HTML-Datei zu erstellen.

1. Öffnen Sie Editor oder einem nur-Text-Editor.

1. Von der **Datei** Menü wählen **neu**.

1. Geben Sie die folgenden Zeilen ein:

```
<HTML>
<HEAD>
<TITLE>Top HTML Tags</TITLE>
</HEAD>
</HTML>
```

1. Von der **Datei** Menü wählen **speichern**, und speichern Sie die Datei als c:\webpages\First.htm. Lassen Sie die Datei im Editor geöffnet.

1. Wechseln Sie in Ihren Browser, und klicken Sie in der **Datei** Menü wählen **öffnen**, oder Typ *file://C:/webpages/first.htm* im Bearbeitungsfeld "URL" des Browsers. Sehen Sie eine leere Seite mit der Beschriftung des Fensters "Top HTML-Tags".

     Beachten Sie, dass die Tags werden zusammengefasst und in spitze Klammern eingeschlossen werden. Tags sind nicht in der Groß-/Kleinschreibung beachtet, aber die Großschreibung wird häufig verwendet, um die Tags optisch hervorzuheben.

     Das Tag \<HTML > beginnt, das Dokument, und das Tag  \< /HTML > beendet sie. Beenden-Tags (nicht immer erforderlich) sind identisch mit dem Tag ab, aber Sie haben einen Schrägstrich (/) vor das Tag. Es sollte kein Leerzeichen zwischen der Spitze Klammer (<) und dem Beginn der Ihr Tag vorhanden sein.

1. Wechseln Sie zurück in den Editor, und klicken Sie nach der  \< /HEAD > Geben Sie diese Zeile:

```
<BODY>
    HTML is swell.
    Life is good.
</BODY>
```

1. Von der **Datei** Menü wählen **speichern**.

1. Wechseln Sie zurück zu Ihrem Browser, und aktualisieren Sie die Seite.

     Die Wörter werden in den Clientbereich des Browserfensters angezeigt. Beachten Sie, dass Ihre Carriage return, Wagenrücklauf ignoriert wird. Wenn Sie ein Zeilenumbruch eingefügt haben möchten, müssen Sie enthalten eine `<BR>` Tag nach der ersten Zeile.

     Für alle Schritte, die folgen, fügen Sie den Text an einer beliebigen Stelle zwischen \<Text > und  \< /BODY > den Text des Dokuments hinzu.

9. Hinzufügen eines Headers:

```
<H3>Here's the big picture</H3>
```

10. Fügen Sie ein Bild, das mithilfe von GIF-Datei im gleichen Verzeichnis wie die Seite gespeichert:

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

12. Verwenden, um die Liste stattdessen Zahl gekoppelt \<OL > und \</OL > anstelle von tags die \<UL > und  \< /UL > Tags.

Sollte Ihnen den Einstieg abgerufen. Wenn Sie eine großartige Funktion auf einer Webseite angezeigt wird, finden Sie heraus, wie sie mithilfe der HTML-Quelle erstellt wurde. HTML-Editoren, z. B. Microsoft Front Page können dazu verwendet werden, sowohl einfache als auch erweiterte Seiten zu erstellen.

Hier ist die gesamte HTML-Quelle für die Datei, die Sie soeben erstellt haben:

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

[http://www.w3.org/pub/WWW/MarkUp/](http://www.w3.org/pub/www/markup/)

## <a name="see-also"></a>Siehe auch

[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)


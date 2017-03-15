---
title: "Gewusst wie: Aktualisieren von Benutzeroberfl&#228;chenobjekten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehle, Aktualisieren der UI"
  - "Deaktivieren von Menüs"
  - "Deaktivieren von UI-Elementen"
  - "Aktivieren von Menüs"
  - "Aktivieren von UI-Elementen"
  - "Menüs, Aktualisieren bei Kontextänderungen"
  - "Updatehandler"
  - "Aktualisieren von Benutzeroberflächenobjekten"
  - "Benutzerschnittstellenobjekte"
  - "Benutzerschnittstellenobjekte, Aktualisieren"
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Gewusst wie: Aktualisieren von Benutzeroberfl&#228;chenobjekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der Regel haben Menüelemente und Symbolleisten\-Schaltflächen mehrere Zustände.  Beispielsweise wird ein Menüelement abgeblendet \(abgeblendet\) wenn es im vorhandenen Kontext nicht verfügbar ist.  Menüelemente können auch überprüft oder deaktiviert werden.  Eine Schaltfläche kann ebenfalls deaktiviert werden, wenn nicht verfügbar, oder sie kann überprüft werden.  
  
 Wer aktualisiert den Zustand dieser Elemente, während Programmzustände ändern?  Logisch wenn ein Menüelement einen Befehl generiert, der durch sagen wir ein Dokument behandelt wird, ist es sinnvoll, das Dokument das Menüelement aktualisieren zu lassen.  Das Dokument enthält wahrscheinlich die Informationen, die die Aktualisierung basiert.  
  
 Wenn ein Befehl mehrere Benutzeroberflächen\-Objekte \(kann ein Menüelement und eine Symbolleistenschaltfläche\) verfügt, werden beide gleichzeitig Handlerfunktion weitergeleitet.  Dies kapselt den Benutzeroberflächeupdatecode für alle Entsprechungsbenutzeroberflächeobjekte in einer einzigen Stelle.  
  
 Das Framework stellt eine bequeme Oberfläche für Benutzeroberflächen\-Objekte automatisch aktualisieren bereit.  Sie können wählen, ob das Aktualisieren auf andere Weise zu tun, die Schnittstelle, die bereitgestellt wird, ist effizient und einfach.  
  
 Die folgenden Themen wird die Verwendung von Aktualisierungshandlern:  
  
-   [Wenn Aktualisierungshandler aufgerufen werden](../mfc/when-update-handlers-are-called.md)  
  
-   [Das ON\_UPDATE\_COMMAND\_UI\-Makro](../mfc/on-update-command-ui-macro.md)  
  
-   [Die CCmdUI\-Klasse](../mfc/the-ccmdui-class.md)  
  
## Siehe auch  
 [Menüs](../mfc/menus-mfc.md)
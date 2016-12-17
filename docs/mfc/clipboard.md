---
title: "Zwischenablage"
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
  - "Zwischenablage"
  - "Zwischenablage, Programmieren"
  - "Kopieren von Daten"
  - "Ausschneiden und Kopieren von Daten"
  - "Übertragen von Daten"
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
caps.latest.revision: 10
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Zwischenablage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Gruppe von Artikeln erläutert, wie Sie Support für die Windows\-Zwischenablage in MFC\-Anwendungen implementiert.  Die Zwischenablage wird auf zwei Arten verwendet:  
  
-   Standardbearbeitungsmenübefehle, Implementing wie Ausschneiden, Kopieren und Einfügen.  
  
-   Implementieren der einheitliche Datenübertragung mit Drag & Drop \(OLE\).  
  
 Die Zwischenablage ist die Standard\-Windows\-Methode des Übertragens von Daten zwischen einer Quelle und einem Ziel.  Es kann in OLE\-Vorgängen sehr hilfreich sein.  Mit dem Aufkommen OLE gibt es zwei Zwischenablagemechanismen in Windows.  Die Standard\-Windows\-Zwischenablage API ist weiterhin verfügbar, aber sie ist mit dem OLE\-Datenübertragungsmechanismus ergänzt wurde.  Einheitliche Datenübertragung \(UDT\) OLE unterstützt Ausschneiden, Kopieren und Einfügen mit der Zwischenablage und den Drag & Drop.  
  
 Die Zwischenablage ist ein Systemdienst, der von der gesamten Windows\-Sitzung freigegeben wird, enthält kein Handle oder eine Klasse von einem eigenen.  Sie verwalten die Zwischenablage von Memberfunktionen der Klasse [CWnd](../mfc/reference/cwnd-class.md).  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Wann jeden Zwischenablagemechanismus verwendet](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)  
  
-   [Verwenden der herkömmlichen Windows\-Zwischenablage API](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [Verwenden des OLE\-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)  
  
-   [\<caps:sentence id\="tgt18" sentenceid\="1bc8aafd7da110d0b343b54cffa169d9" class\="tgtSentence"\>Die Zwischenablage\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms648709)  
  
-   [Drag & Drop \(OLE\) implementieren](../mfc/drag-and-drop-ole.md)  
  
## Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)
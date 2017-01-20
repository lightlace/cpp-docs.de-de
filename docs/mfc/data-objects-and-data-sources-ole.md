---
title: "Datenobjekte und Datenquellen (OLE)"
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
  - "Datenobjekte [C++], Definition"
  - "Datenquellen [C++], Definition"
  - "Datenübertragung [C++]"
  - "Datenübertragung [C++], Definition"
  - "OLE [C++], Datenobjekte"
  - "OLE [C++], Datenquellen"
  - "OLE [C++], Datenübertragung"
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Datenobjekte und Datenquellen (OLE)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine Datenübertragung, entweder mithilfe der Zwischenablage oder Drag & Drop ausführen, haben die Daten eine Quelle und ein Ziel.  Eine Anwendung stellt die Daten für das Kopieren bereit und eine andere Anwendung akzeptiert sie für das Einfügen.  Jede Seite der Übergangsanforderungen, unterschiedliche Vorgänge mit denselben Daten auszuführen, sodass die Übertragung folgt.  Die MFC\-Bibliothek \(Microsoft Foundation \(MFC\) stellt zwei Klassen, die eine Seite dieser Übertragung darstellen:  
  
-   Datenquellen \(wie durch `COleDataSource`\-Objekte implementiert\) stellen die Quellseite der Datenübertragung dar.  Sie werden durch die aussieht erstellt, wenn Daten in die Zwischenablage kopiert werden sollen oder wenn Sie Daten für einen Drag & Drop\-Vorgangs bereitgestellt werden.  
  
-   Datenobjekte \(wie durch `COleDataObject`\-Objekte implementiert\) stellen die Zielseite der Datenübertragung dar.  Sie werden erstellt, wenn die Ziel\-Anwendung die Daten enthält, die in dem Ablegen wird oder wenn sie aufgefordert wird, einen Einfügevorgang von der Zwischenablage auszuführen.  
  
 Die folgenden Elemente beschreiben, wie Sie Datenobjekte und Datenquellen in Anwendungen.  Diese Informationen gelten für Container und Serveranwendungen zu, da beide möglicherweise zu kopieren und einfügen\-Daten aufgefordert werden.  
  
-   [Datenobjekte und Datenquellen: Erstellung und Zerstörung](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Datenobjekte und Datenquellen: Manipulation](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## In diesem Abschnitt  
 [Drag & Drop](../mfc/drag-and-drop-ole.md)  
  
 [Zwischenablage](../mfc/clipboard.md)  
  
## Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleDataObject Class](../mfc/reference/coledataobject-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)
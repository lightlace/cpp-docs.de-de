---
title: "Debuggen des Anbieters | Microsoft Docs"
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
  - "Debuggen [C++], Anbieter"
  - "OLE DB-Anbieter, Debuggen"
  - "Visual C++-Debugger"
  - "Visual C++-Debugger, Debuggen von Anbietern"
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Debuggen des Anbieters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie haben zwei Möglichkeiten, den Anbieter zu debuggen:  
  
-   Da Anbieter prozessintern erstellt werden, können Sie mithilfe der OLE DB\-Consumervorlagen Consumercode erstellen und den Anbieter wie gewohnt ausführen.  
  
-   Sie können das in Visual C\+\+ enthaltene Dienstprogramm ITEST verwenden.  
  
### So verwenden Sie das ITEST\-Dienstprogramm  
  
1.  Öffnen Sie das Anbieterprojekt.  
  
2.  Klicken Sie im Menü **Projekte** auf **Einstellungen**.  
  
3.  Klicken Sie im Dialogfeld **Eigenschaftenseiten** auf die Registerkarte **Debuggen**.  
  
4.  Wählen Sie im Feld **Ausführbares Programm für Debugsitzung** das ITEST\-Dienstprogramm aus.  
  
5.  Setzen Sie Haltepunkte, und führen Sie die Debugsitzung wie gewohnt aus.  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)
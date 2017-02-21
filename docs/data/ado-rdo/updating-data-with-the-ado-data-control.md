---
title: "Aktualisieren von Daten mit dem ADO-Datensteuerelement | Microsoft Docs"
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
  - "ADO [C++], Datenbindung"
  - "ADO [C++], Datensteuerelemente"
ms.assetid: 8bec34b9-93dd-4872-b023-55ac011ccff5
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Aktualisieren von Daten mit dem ADO-Datensteuerelement
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Daten des ADO\-Datensteuerelements können entweder schreibgeschützt oder veränderbar sein.  
  
### So erstellen Sie eine Anwendung, in der Daten mithilfe eines ADO\-Datensteuerelements geändert werden  
  
1.  Legen Sie die **CursorLocation**\-Eigenschaft des ADO\-Datensteuerelements fest.  Auswahlmöglichkeiten:  
  
    -   Serverseitig  
  
    -   Clientseitig  
  
2.  Legen Sie die **LockType**\-Eigenschaft des ADO\-Datensteuerelements fest.  Hier wird die vollständige Parallelität empfohlen.  
  
3.  Legen Sie die **CursorType**\-Eigenschaft des ADO\-Datensteuerelements fest.  Auswahlmöglichkeiten:  
  
    -   Keysetcursor  
  
    -   Dynamischer Cursor  
  
    -   Statischer Cursor  
  
     Stellen Sie sicher, dass der OLE DB\-Anbieter die ausgewählte Option unterstützt.  
  
4.  Legen Sie ggf. Eigenschaften des datengebundenen Steuerelements fest, um Aktualisierbarkeit zu gewährleisten.  Beachten Sie, dass einige Steuerelemente keine Aktualisierung zulassen.  
  
 Weitere Informationen über diese Eigenschaften finden Sie in der ADO\-Dokumentation.  
  
## Siehe auch  
 [ADO\-Datenbindung](../../data/ado-rdo/ado-databinding.md)   
 [Verwenden der ADO\-Datenbindung in Visual C\+\+](../../data/ado-rdo/using-ado-databinding-in-visual-cpp.md)
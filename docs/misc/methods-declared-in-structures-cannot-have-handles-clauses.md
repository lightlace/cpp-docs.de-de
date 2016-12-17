---
title: "In Strukturen deklarierte Methoden k&#246;nnen keine Handles-Klauseln haben."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30728"
  - "bc30728"
helpviewer_keywords: 
  - "BC30728"
ms.assetid: 64c70bb5-3696-4865-8194-328394c2b4b1
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# In Strukturen deklarierte Methoden k&#246;nnen keine Handles-Klauseln haben.
Strukturmethoden können das `Handles`\-Schlüsselwort nicht zum Behandeln von Ereignissen verwenden.  
  
 **Fehler\-ID:** BC30728  
  
### So beheben Sie diesen Fehler  
  
-   Sie sollten einen Neuentwurf Ihrer Struktur als Klasse in Erwägung ziehen.  
  
     Sie können `AddHandler` verwenden, um ein Ereignis mit einem Ereignishandler in einer Struktur zu verknüpfen, vorausgesetzt, die Struktur implementiert einen in einer Schnittstelle definierten Ereignishandler.  
  
## Siehe auch  
 [Structures and Classes](../Topic/Structures%20and%20Classes%20\(Visual%20Basic\).md)   
 [NICHT IM BUILD: Klassen: Blaupausen für Objekte](assetId:///2c86373d-0333-4616-a7d8-4790c4e89f7b)   
 [Events](../Topic/Events%20\(Visual%20Basic\).md)   
 [NICHT IM BUILD: AddHandler und RemoveHandler](assetId:///a7a24bd2-519a-46fe-8a2c-2b9df2ca28ef)
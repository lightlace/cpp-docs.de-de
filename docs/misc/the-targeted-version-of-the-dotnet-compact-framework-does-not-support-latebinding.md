---
title: "Die Zielversion von .NET Compact Framework unterst&#252;tzt kein sp&#228;tes Binden."
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30762"
  - "bc30762"
helpviewer_keywords: 
  - "BC30762"
ms.assetid: b433014d-8422-46e8-ad55-321146a48186
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Die Zielversion von .NET Compact Framework unterst&#252;tzt kein sp&#228;tes Binden.
Die Version von .NET Compact Framework, mit der Sie arbeiten, unterstützt kein spätes Binden.  
  
 **Fehler\-ID:** BC30762  
  
### So beheben Sie diesen Fehler  
  
1.  Vermeiden Sie Aufrufe von Funktionen, Subs oder Eigenschaften für eine als Objekt deklarierte Variable.  
  
2.  Vermeiden Sie die Verwendung der Objektvariablen als Array.  
  
3.  Vermeiden Sie die Verwendung von Memberzugriffsausdrücken aus Wörterbüchern mit Objektvariablen.  
  
## Siehe auch  
 [NICHT IM BUILD: Objekte in Visual Basic](assetId:///85bd757a-a19e-45e1-af89-d68765f5ee3c)   
 [Special Characters in Code](../Topic/Special%20Characters%20in%20Code%20\(Visual%20Basic\).md)
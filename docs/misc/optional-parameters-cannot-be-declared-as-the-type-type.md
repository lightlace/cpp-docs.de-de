---
title: "Optionale Parameter k&#246;nnen nicht als Typ &quot;&lt;Typ&gt;&quot; deklariert werden."
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
  - "bc30423"
  - "vbc30423"
helpviewer_keywords: 
  - "BC30423"
ms.assetid: 972dab8b-d91e-4a89-b822-2b8e4aadd25f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Optionale Parameter k&#246;nnen nicht als Typ &quot;&lt;Typ&gt;&quot; deklariert werden.
Optionale Parameter können nicht den Datentyp einer Struktur annehmen.  
  
 **Fehler\-ID:** BC30423  
  
### So beheben Sie diesen Fehler  
  
1.  Um eine Struktur an einen optionalen Parameter zu übergeben, deklarieren Sie den Parameter als `Object`.  
  
2.  Verwenden Sie `CType`, um den Parameter in diesen Strukturtyp innerhalb der Prozedur umzuwandeln.  
  
## Siehe auch  
 [Structures and Classes](../Topic/Structures%20and%20Classes%20\(Visual%20Basic\).md)   
 [CType\-Funktion](../Topic/CType%20Function%20\(Visual%20Basic\).md)
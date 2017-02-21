---
title: "Ausdrucksauswertungsfehler CXX0019 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0019"
  - "CXX0019"
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksauswertungsfehler CXX0019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehlerhafte Typumwandlung  
  
 Die C\-Ausdrucksauswertung kann die angegebene Typumwandlung nicht ausführen.  
  
 Dieser Fehler ist mit CAN0019 identisch.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Der angegebene Typ ist unbekannt.  
  
2.  Es waren zu viele Ebenen von Zeigertypen vorhanden.  Die Typumwandlung  
  
    ```  
    (char **)h_message  
    ```  
  
     z. B. kann von der C\-Ausdrucksauswertung nicht ausgewertet werden.
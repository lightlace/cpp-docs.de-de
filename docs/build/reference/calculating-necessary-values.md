---
title: "Berechnen der erforderlichen Werte | Microsoft Docs"
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
  - "Hilfsfunktionen, Berechnen der erforderlichen Werte"
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Berechnen der erforderlichen Werte
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zwei entscheidende Informationen müssen von der Hilfsfunktion für verzögertes Laden berechnet werden.  Zur Berechnung dieser Informationen befinden sich in der Headerdatei **delayimp.h** zwei Inlinefunktionen.  
  
-   Die erste berechnet den Index des aktuellen Imports in die drei verschiedenen Tabellen \(Importadressentabelle \(IAT\), gebundene Importadressentabelle \(BIAT\) und ungebundene Importadressentabelle \(UIAT\)\).  
  
-   Die zweite zählt die Anzahl der Importe in einer gültigen Importadressentabelle \(IAT\).  
  
```  
// utility function for calculating the index of the current import  
// for all the tables (INT, BIAT, UIAT, and IAT).  
__inline unsigned  
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {  
    return pitdCur - pitdBase;  
    }  
  
// utility function for calculating the count of imports given the base  
// of the IAT. NB: this only works on a valid IAT!  
__inline unsigned  
CountOfImports(PCImgThunkData pitdBase) {  
    unsigned        cRet = 0;  
    PCImgThunkData  pitd = pitdBase;  
    while (pitd->u1.Function) {  
        pitd++;  
        cRet++;  
        }  
    return cRet;  
    }  
```  
  
## Siehe auch  
 [Understanding the Helper Function](assetId:///6279c12c-d908-4967-b0b3-cabfc3e91d3d)
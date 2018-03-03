---
title: Berechnen der erforderlichen Werte | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- helper functions, calculating necessary values
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d1e51f1a23a81811bdd4aa6c6feec45748ee572
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="calculating-necessary-values"></a>Berechnen der erforderlichen Werte
Zwei wichtige Angaben müssen durch die Verzögerung Hilfsroutine berechnet werden soll. Zu diesem Zweck stehen zwei Inlinefunktionen in delayhlp.cpp zum Berechnen dieser Informationen.  
  
-   Die erste berechnet den Index des aktuellen Imports in die drei verschiedenen Tabellen (Local Address Table (IAT), gebundene Importadresstabelle (BIAT) und ungebundene Importadresstabelle (UIAT) importiert).  
  
-   Die zweite zählt die Anzahl von "Imports" in eine gültige IAT.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Die Hilfsfunktion](understanding-the-helper-function.md)
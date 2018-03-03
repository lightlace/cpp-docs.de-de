---
title: Ausdrucksauswertungsfehler CXX0019 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0019
dev_langs:
- C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c62391bb770a49810a87c52b2f75d5a0d4426fbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0019"></a>Ausdrucksauswertungsfehler CXX0019
Fehlerhafte Typumwandlung  
  
 Die C-ausdrucksauswertung kann die Typumwandlung wie geschrieben nicht ausführen.  
  
 Dieser Fehler ist mit CAN0019 identisch.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Der angegebene Typ ist unbekannt.  
  
2.  Es wurden zu viele Ebenen von Zeigertypen. Z. B. die Typumwandlung  
  
    ```  
    (char **)h_message  
    ```  
  
     kann von der C-ausdrucksauswertung ausgewertet werden.
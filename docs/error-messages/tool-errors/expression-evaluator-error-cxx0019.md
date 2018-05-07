---
title: Ausdrucksauswertungsfehler CXX0019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0019
dev_langs:
- C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52e1679374e105ab06ce245ba68cfe92706689e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
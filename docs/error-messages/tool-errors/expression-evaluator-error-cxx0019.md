---
title: Ausdrucksauswertungsfehler CXX0019 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0019
dev_langs: C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67fbd43280ad6ffcecdf0532819cd80a0d44b479
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
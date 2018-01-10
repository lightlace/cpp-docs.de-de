---
title: "Kumulative Abhängigkeiten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 40811087cedd83bcd34745be7f1d5a404f4bb628
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cumulative-dependencies"></a>Kumulative Abhängigkeiten
Abhängigkeiten sind in einem Beschreibungsblock kumulativ, wenn ein Ziel wiederholt wird.  
  
 Legen Sie diese z. B. Regeln,  
  
```Output  
bounce.exe : jump.obj  
bounce.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 wird folgendermaßen ausgewertet:  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Mehrere Ziele in mehreren Abhängigkeitszeilen in einem einzelnen Beschreibungsblock werden ausgewertet, als ob alle in einem separaten Beschreibungsblock angegeben wurden, aber Ziele, die nicht in der letzten Abhängigkeitszeile Sie den Befehlsblock nicht verwenden. NMAKE versucht, eine Rückschlussregel mithilfe eines für diese Ziele zu verwenden.  
  
 Legen Sie diese z. B. Regeln,  
  
```Output  
leap.exe bounce.exe : jump.obj  
bounce.exe climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 wird folgendermaßen ausgewertet:  
  
```Output  
  
leap.exe : jump.obj  
# invokes an inference rule  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ziele](../build/targets.md)
---
title: Kumulative Abhängigkeiten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d502912a8aeee2e6b3782e7795f44238386e1dba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366974"
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
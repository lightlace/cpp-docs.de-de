---
title: Compilerfehler Fehler C2006 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8d182e7a98d01dee4047defa5adb5ccc2dc7cde5
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2006"></a>Compilerfehler Fehler C2006
'Direktive' erwartet Dateinamen, aber 'token' gefunden  
  
 Anweisungen wie z. B. [#include](../../preprocessor/hash-include-directive-c-cpp.md) oder [#import](../../preprocessor/hash-import-directive-cpp.md) ist ein Dateiname erforderlich. Um den Fehler zu beheben, stellen Sie sicher, dass *token* ist ein gültiger Dateiname. Darüber hinaus sollten Sie den Dateinamen in doppelte Anführungszeichen und spitzen Klammern.  
  
 Im folgende Beispiel wird C2006 generiert:  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 Mögliche Lösung:  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```

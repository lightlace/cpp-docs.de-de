---
title: Compilerfehler Fehler C2006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93880e7d767de3101cd7a292af5fa2874cae86bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
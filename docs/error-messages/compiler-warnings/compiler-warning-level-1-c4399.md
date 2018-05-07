---
title: Compilerwarnung (Stufe 1) C4399 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b39f4919dd736e4bf2e6230fe68ea69c2b14766e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4399"></a>Compilerwarnung (Stufe 1) C4399
'Symbol': prozessspezifisch Symbol sollten nicht gekennzeichnet werden, mit von "__declspec(dllimport)" "beim Kompilieren mit/clr: pure  
  
 Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert ist.  
  
 Daten über ein systemeigenes Image oder ein Bild mit einheitlichen und den CLR-Konstrukte können in einem reinen Image nicht importiert werden. Um diese Warnung zu beheben, kompilieren Sie mit **"/ CLR"** (nicht **/CLR: pure**) oder Löschen von `__declspec(dllimport)`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4399 generiert.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```
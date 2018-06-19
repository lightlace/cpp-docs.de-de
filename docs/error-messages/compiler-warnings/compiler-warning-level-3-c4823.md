---
title: Compilerwarnung (Stufe 3) C4823 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c29499a82601dcf653ff2f003441935f1d6841a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293230"
---
# <a name="compiler-warning-level-3-c4823"></a>Compilerwarnung (Stufe 3) C4823
'Funktion': verwendet, die feste Zeiger, aber entladen nicht aktiviert. Erwägen Sie/EHa  
  
Um ein Objekt auf dem verwalteten Heap verweist ein fester Zeiger deklariert, die in einem Blockbereich lösen zu können, wird der Compiler das Verhalten von Destruktoren für lokale Klassen, die "servermeldungen", dass der feste Zeiger einen Destruktor enthält, der den Zeiger hebt simuliert. Um einen Aufruf von einem Destruktor nach dem Auslösen einer Ausnahme zu aktivieren, müssen Sie aktivieren Objekt zu entladen, können Sie mithilfe von [/EHsc /](../../build/reference/eh-exception-handling-model.md).  
  
Sie können auch manuell lösen Sie das Objekt und die Warnung ignorieren.  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird C4823 generiert.  
  
```  
// C4823.cpp  
// compile with: /clr /W3 /EHa-  
using namespace System;  
  
ref struct G {  
   int m;  
};  
  
void f(G ^ pG) {  
   try {  
      pin_ptr<int> p = &pG->m;  
      // manually unpin, ignore warning  
      // p = nullptr;  
      throw gcnew Exception;  
   }  
   catch(Exception ^) {}  
}   // C4823 warning  
  
int main() {  
   f( gcnew G );  
}  
```  

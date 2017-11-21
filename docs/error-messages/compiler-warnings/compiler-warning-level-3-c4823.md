---
title: Compilerwarnung (Stufe 3) C4823 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4823
dev_langs: C++
helpviewer_keywords: C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af4b7e220957722793458a283244092574d05fa9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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

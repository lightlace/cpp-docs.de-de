---
title: Compiler (Stufe 3) C4823 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ea03723f9ccae2348a47ae4894097f5cd9f8b5a1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4823"></a>Compilerwarnung (Stufe 3) C4823
'Funktion': verwendet feste Zeiger zu, aber entladen nicht aktiviert. Erwägen Sie/EHa  
  
Um ein Objekt im verwalteten Heap verweist ein fester Zeiger in einem Blockbereich deklarierten zu lösen, simuliert der Compiler das Verhalten von Destruktoren für lokale Klassen und "als", ob der feste Zeiger über einen Destruktor aufweist, der den Zeiger hebt. Um einen Aufruf von einem Destruktor nach dem Auslösen einer Ausnahme zu aktivieren, müssen Sie aktivieren Objekt zu entladen, können Sie mithilfe von [/EHsc](../../build/reference/eh-exception-handling-model.md).  
  
Sie können auch manuell lösen das Objekt und die Warnung ignorieren.  
  
## <a name="example"></a>Beispiel  
Im folgende Beispiel wird C4823 generiert.  
  
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


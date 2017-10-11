---
title: Compilerfehler C3498 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3498
dev_langs:
- C++
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0429b9d21829f772596b6d0fd2c51d72b0924e26
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3498"></a>Compilerfehler C3498
"Var": Sie können keine Variable mit einer verwalteten oder WinRTtype erfassen  
  
 Sie können keine Variable erfassen, die einen verwalteten Typ oder einen Windows-Runtime-Typ in einem „lambda“ aufweist.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Übergeben Sie die verwaltete oder Windows-Runtime-Variable an die Parameterliste des Lambdaausdrucks.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3498 generiert, da eine Variable mit einem verwalteten Typ in der Erfassungsliste eines Lambdaausdrucks angezeigt wird:  
  
```  
// C3498a.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [&s](String ^ r)   
      { return String::Concat(s, r); } (", World!"); // C3498  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3498 durch Übergeben der verwaltete Variablen `s` an die Parameterliste des Lambda-Ausdrucks aufgelöst:  
  
```  
// C3498b.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [](String ^ s, String ^ r)   
      { return String::Concat(s, r); } (s, ", World!");  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)

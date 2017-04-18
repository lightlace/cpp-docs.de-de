---
title: Compilerfehler C3491 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3491
dev_langs:
- C++
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: c6087d7be6ac5fce959d7f54c529401d9b57631e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3491"></a>Compilerfehler C3491
"Var": Eine Erfassung nach Wert kann in einem nicht änderbaren Lambda nicht geändert werden.  
  
 Ein nicht änderbarer Lambda-Ausdruck kann den Wert einer Variablen nicht ändern, die nach Wert erfasst wird.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Deklarieren Sie den Lambda-Ausdruck mit dem `mutable` -Schlüsselwort, oder  
  
-   übergeben Sie die Variable per Verweis an die Erfassungsliste des Lambda-Ausdrucks.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3491 generiert, da der Text eines nicht änderbaren Lambda-Ausdrucks die Erfassungsvariable `m`ändert:  
  
```  
// C3491a.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) { m = n; }(99); // C3491  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Fehler C3491 durch Deklarieren des Lambda-Ausdrucks mit dem `mutable` -Schlüsselwort behoben:  
  
```  
// C3491b.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) mutable { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)

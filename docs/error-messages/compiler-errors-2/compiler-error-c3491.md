---
title: Compilerfehler C3491 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3491
dev_langs:
- C++
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bd856f50f3528b3895e4495215b2e479d8a424b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
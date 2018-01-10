---
title: Compilerfehler C3491 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3491
dev_langs: C++
helpviewer_keywords: C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8c126ae0533424c19fd29ea48dbea8c3d7e8971
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
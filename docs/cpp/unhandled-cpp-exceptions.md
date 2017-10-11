---
title: Nicht behandelte C++-Ausnahmen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], unhandled exceptions
- catch keyword [C++], handler not found
- exceptions [C++], unhandled
- C++ exception handling, unhandled exceptions
- unhandled exceptions [C++]
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 590dc46e5cf761f02ba85dba950c04a2da4df022
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="unhandled-c-exceptions"></a>Nicht behandelte C++-Ausnahmen
Wenn kein entsprechender Handler (oder Auslassungszeichen- **catch** Handler) kann nicht gefunden werden, für die aktuelle Ausnahme, die die vordefinierten `terminate` -Laufzeit-Funktion wird aufgerufen. (Sie können auch `terminate` in jedem Ihrer Handler explizit aufrufen.) Der Standardvorgang von `terminate` besteht darin, `abort` aufzurufen. Wenn `terminate` eine andere Funktion in Ihrem Programm aufrufen soll, bevor Sie die Anwendung beenden, rufen Sie die `set_terminate`-Funktion mit dem Funktionsnamen auf, der als sein einzelnes Argument aufgerufen werden soll. Sie können `set_terminate` an jedem Punkt im Programm aufrufen. Die `terminate` -Routine ruft immer die letzte Funktion als Argument an `set_terminate`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel löst eine `char *`-Ausnahme aus, aber es enthält keinen Handler, der dazu vorgesehen ist, Ausnahmen des Typs `char *` zu erfassen. Der Aufruf von `set_terminate` weist `terminate` an, `term_func` aufzurufen.  
  
```  
// exceptions_Unhandled_Exceptions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void term_func() {  
   cout << "term_func was called by terminate." << endl;  
   exit( -1 );  
}  
int main() {  
   try  
   {  
      set_terminate( term_func );  
      throw "Out of memory!"; // No catch handler for this exception  
   }  
   catch( int )  
   {  
      cout << "Integer exception raised." << endl;  
   }  
   return 0;  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
term_func was called by terminate.  
```  
  
 Die `term_func`-Funktion muss das Programm oder den aktuellen Thread beenden, idealerweise mit dem Aufruf von `exit`. Wenn stattdessen eine Rückkehr zum Aufruf erfolgt, wird `abort` aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)

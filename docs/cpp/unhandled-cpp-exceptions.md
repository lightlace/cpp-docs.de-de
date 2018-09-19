---
title: Nicht behandelte C++-Ausnahmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 57d014762ebc5427ccc4b9d26fff75addc883759
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097769"
---
# <a name="unhandled-c-exceptions"></a>Nicht behandelte C++-Ausnahmen

Wenn kein entsprechender Handler (oder Auslassungszeichen- **catch** Handler) kann nicht gefunden werden, für die aktuelle Ausnahme, die die vordefinierten `terminate` Run-Time-Funktion wird aufgerufen. (Sie können auch `terminate` in jedem Ihrer Handler explizit aufrufen.) Der Standardvorgang von `terminate` besteht darin, `abort` aufzurufen. Wenn `terminate` eine andere Funktion in Ihrem Programm aufrufen soll, bevor Sie die Anwendung beenden, rufen Sie die `set_terminate`-Funktion mit dem Funktionsnamen auf, der als sein einzelnes Argument aufgerufen werden soll. Sie können `set_terminate` an jedem Punkt im Programm aufrufen. Die `terminate` -Routine ruft immer die letzte Funktion, die als Argument an `set_terminate`.

## <a name="example"></a>Beispiel

Das folgende Beispiel löst eine `char *`-Ausnahme aus, aber es enthält keinen Handler, der dazu vorgesehen ist, Ausnahmen des Typs `char *` zu erfassen. Der Aufruf von `set_terminate` weist `terminate` an, `term_func` aufzurufen.

```cpp
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

```Output
term_func was called by terminate.
```

Die `term_func`-Funktion muss das Programm oder den aktuellen Thread beenden, idealerweise mit dem Aufruf von `exit`. Wenn stattdessen eine Rückkehr zum Aufruf erfolgt, wird `abort` aufgerufen.

## <a name="see-also"></a>Siehe auch

[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)
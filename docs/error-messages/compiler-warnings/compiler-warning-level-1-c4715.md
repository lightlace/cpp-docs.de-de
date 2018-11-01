---
title: Compilerwarnung (Stufe 1) C4715
ms.date: 11/04/2016
f1_keywords:
- C4715
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
ms.openlocfilehash: f165ea3b54b78e2f8fae995815e309d55101244e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501230"
---
# <a name="compiler-warning-level-1-c4715"></a>Compilerwarnung (Stufe 1) C4715

'Funktion': nicht alle Codepfade geben einen Wert zurück.

Die angegebene Funktion kann nicht auf einen Wert zurückgeben.

## <a name="example"></a>Beispiel

```
// C4715a.cpp
// compile with: /W1 /LD
int func1( int i )
{
   if( i )
   return 3;  // C4715 warning, nothing returned if i == 0
}
```

Um diese Warnung zu vermeiden, ändern Sie den Code, damit alle Pfade über einen Rückgabewert der Funktion zuweisen:

```
// C4715b.cpp
// compile with: /LD
int func1( int i )
{
   if( i ) return 3;
   else return 0;     // OK, always returns a value
}
```

Es ist möglich, dass Ihr Code einen Aufruf einer Funktion, die nie zurückgegeben enthalten kann, wie im folgenden Beispiel:

```
// C4715c.cpp
// compile with: /W1 /LD
void fatal()
{
}
int glue()
{
   if(0)
      return 1;
   else if(0)
      return 0;
   else
      fatal();   // C4715
}
```

Dieser Code generiert außerdem eine Warnung aus, da der Compiler nicht, dass weiß `fatal` gibt nie Werte zurück. Um zu verhindern, dass dieser Code generiert eine Fehlermeldung angezeigt, deklarieren `fatal` mit [__declspec(noreturn)](../../cpp/noreturn.md).
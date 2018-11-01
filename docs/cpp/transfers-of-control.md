---
title: Übertragung der Steuerung
ms.date: 11/04/2016
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
ms.openlocfilehash: 1fc487628f26dcac097109bc71fa960e501d0797
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469640"
---
# <a name="transfers-of-control"></a>Übertragung der Steuerung

Können Sie die **Goto** Anweisung oder ein **Fall** -Bezeichnung in einer **wechseln** Anweisung, um ein Programm angeben, die hinter einem Initialisierer brancht. Solcher Code ist nicht zulässig, es sei denn, die Deklaration, die den Initialisierer enthält, befindet sich in einem Block, der von dem Block eingeschlossen wird, in dem die Sprunganweisung auftritt.

Das folgende Beispiel zeigt eine Schleife, welche die Objekte `total`, `ch` und `i` deklariert und initialisiert. Es gibt auch eine fehlerhafte **Goto** Anweisung, die Steuerung jenseits eines Initialisierers überträgt.

```cpp
// transfers_of_control.cpp
// compile with: /W1
// Read input until a nonnumeric character is entered.
int main()
{
   char MyArray[5] = {'2','2','a','c'};
   int i = 0;
   while( 1 )
   {
      int total = 0;

      char ch = MyArray[i++];

      if ( ch >= '0' && ch <= '9' )
      {
         goto Label1;

         int i = ch - '0';
      Label1:
         total += i;   // C4700: transfers past initialization of i.
      } // i would be destroyed here if  goto error were not present
   else
      // Break statement transfers control out of loop,
      //  destroying total and ch.
      break;
   }
}
```

Im vorherigen Beispiel das **Goto** -Anweisung versucht, die Kontrolle über die Initialisierung der zu übertragenden `i`. Wenn jedoch `i` zwar deklariert, aber nicht initialisiert ist, wäre die Übertragung gültig.

Die Objekte `total` und `ch`, deklariert im-Block, der als dient der *Anweisung* von der **während** -Anweisung werden zerstört, wenn es sich bei diesen Block beendet wird, mit der  **Break** Anweisung.
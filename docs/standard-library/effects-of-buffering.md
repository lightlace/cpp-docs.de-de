---
title: Pufferungseffekte
ms.date: 11/04/2016
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
ms.openlocfilehash: 1f28748f1e7a837ad87ef1cfcebc56d3410d0fd2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458907"
---
# <a name="effects-of-buffering"></a>Pufferungseffekte

Im folgenden Beispiel werden die Effekte von Pufferung veranschaulicht. Sie erwarten wahrscheinlich, dass das Programm `please wait`ausgibt, 5 Sekunden wartet, und dann den nächsten Vorgang ausführt. Das Programm wird aber nicht unbedingt so funktionieren, weil die Ausgabe gepuffert wird.

```cpp
// effects_buffering.cpp
// compile with: /EHsc
#include <iostream>
#include <time.h>
using namespace std;

int main( )
{
   time_t tm = time( NULL ) + 5;
   cout << "Please wait...";
   while ( time( NULL ) < tm )
      ;
   cout << "\nAll done" << endl;
}
```

Damit das Programm logisch funktioniert, muss sich das `cout` -Objekt selbst leeren, wenn die Meldung angezeigt werden soll. Um ein `ostream` -Objekt zu leeren, senden Sie ihm den `flush` -Manipulator:

```cpp
cout <<"Please wait..." <<flush;
```

In diesem Schritt wird der Puffer geleert, wodurch sichergestellt wird, dass die Meldung vor dem Wartevorgang ausgegeben wird. Sie können auch den `endl` Manipulator verwenden, der den Puffer leert und einen Wagen Rücklauf-Zeilenvorschub ausgibt, oder Sie können das `cin` -Objekt verwenden. Dieses Objekt (mit dem `cerr` - oder dem `clog` -Objekt) ist in der Regel mit dem `cout` -Objekt verknüpft. Daher wird bei jeder Verwendung von `cin` (oder einem der Objekte `cerr` oder `clog` ) das `cout` -Objekt geleert.

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)

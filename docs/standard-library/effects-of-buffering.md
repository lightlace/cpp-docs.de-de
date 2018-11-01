---
title: Pufferungseffekte
ms.date: 11/04/2016
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
ms.openlocfilehash: e10b28edffdfe3411f86c031bfd12ea886410e20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631438"
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

In diesem Schritt wird der Puffer geleert, wodurch sichergestellt wird, dass die Meldung vor dem Wartevorgang ausgegeben wird. Sie können auch die `endl` Manipulator, der den Puffer leert und gibt einen Zeilenumbruch, oder Sie können die `cin` Objekt. Dieses Objekt (mit dem `cerr` - oder dem `clog` -Objekt) ist in der Regel mit dem `cout` -Objekt verknüpft. Daher wird bei jeder Verwendung von `cin` (oder einem der Objekte `cerr` oder `clog` ) das `cout` -Objekt geleert.

## <a name="see-also"></a>Siehe auch

[Ausgabestreams](../standard-library/output-streams.md)<br/>

---
title: Ausgabestreammanipulatoren mit einem Argument (int oder long)
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
ms.openlocfilehash: e093512af2741329c58db0b613453f3388bacdf2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530988"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Ausgabestreammanipulatoren mit einem Argument (int oder long)

Die iostream-Klassenbibliothek enthält eine Reihe von Makros zum Erstellen von parametrisierter Manipulatoren. Manipulatoren mit einem einzigen **Int** oder **lange** Argument sind ein Sonderfall. Um einen ausgabestreammanipulator zu erstellen, eine einzelne akzeptiert **Int** oder **lange** Argument (z. B. `setw`), müssen Sie das Makro _Smanip, definiert in den verwenden \<Iomanip >. Dieses Beispiel definiert einen `fillblank`-Manipulator, der eine angegebene Anzahl von Leerzeichen in den Datenstrom eingefügt:

## <a name="example"></a>Beispiel

```cpp
// output_stream_manip.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

void fb( ios_base& os, int l )
{
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
}

_Smanip<int>
   __cdecl fillblank(int no)
   {
   return (_Smanip<int>(&fb, no));
   }

int main( )
{
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";
}
```

## <a name="see-also"></a>Siehe auch

[Benutzerdefinierte Manipulatoren mit Argumenten](../standard-library/custom-manipulators-with-arguments.md)<br/>

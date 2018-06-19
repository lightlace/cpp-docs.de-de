---
title: Ausgabestreammanipulatoren mit einem Argument (int oder long) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3238ffcbd03f40c6eac0423d0212a65719fb33d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853072"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Ausgabestreammanipulatoren mit einem Argument (int oder long)

Die iostream-Klassenbibliothek enthält eine Reihe von Makros zum Erstellen von parametrisierter Manipulatoren. Manipulatoren mit einem einzigen `int`- oder `long`-Argument sind ein Sonderfall. Um einen Ausgabestreammanipulator zu erstellen, der ein einzelnes `int`- oder `long`-Argument akzeptiert (z.B. `setw`), müssen Sie das Makro _Smanip verwenden, das in \<iomanip> definiert ist. Dieses Beispiel definiert einen `fillblank`-Manipulator, der eine angegebene Anzahl von Leerzeichen in den Datenstrom eingefügt:

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

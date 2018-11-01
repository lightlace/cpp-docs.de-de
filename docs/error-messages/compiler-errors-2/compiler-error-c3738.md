---
title: Compilerfehler C3738
ms.date: 11/04/2016
f1_keywords:
- C3738
helpviewer_keywords:
- C3738
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
ms.openlocfilehash: e313c7d66bc030183e330dd961fad2fb35f02ac2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539320"
---
# <a name="compiler-error-c3738"></a>Compilerfehler C3738

'Aufrufkonvention': die Aufrufkonvention der expliziten Instanziierung muss mit der der instanziierten Vorlage übereinstimmen

Es wird empfohlen, dass Sie bei einer expliziten Instanziierung nicht durch eine Aufrufkonvention angeben. Falls erforderlich, jedoch müssen die Aufrufkonventionen übereinstimmen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3738 generiert.

```
// C3738.cpp
// compile with: /clr
// processor: x86
#include <stdio.h>
template< class T >
void f ( T arg ) {   // by default calling convention is __cdecl
   printf ( "f: %s\n", __FUNCSIG__ );
}

template
void __stdcall f< int > ( int arg );   // C3738
// try the following line instead
// void f< int > ( int arg );

int main () {
   f(1);
   f< int > ( 1 );
}
```
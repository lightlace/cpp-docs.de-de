---
title: Compilerwarnung (Stufe 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: 439c4976f25688fd9220c3f58ceb933266b5f15c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447334"
---
# <a name="compiler-warning-level-1-c4342"></a>Compilerwarnung (Stufe 1) C4342

verhaltensänderung: '*Funktion*"aufgerufen wird, jedoch ein Memberoperator aufgerufen wurde, in früheren Versionen

In Versionen von Visual C++ vor Visual Studio 2002 ein Element aufgerufen wurde, aber dieses Verhalten wurde geändert, und der Compiler findet jetzt die beste Übereinstimmung im Namespacebereich.

Wenn ein Member-Operator gefunden wurde, würde der Compiler zuvor betrachtet keinem Namespace Bereich Operatoren. Ist eine bessere Übereinstimmung im Gültigkeitsbereich des Namespace, ruft der aktuelle Compiler ordnungsgemäß, während der vorherige Compilern wäre nicht beachtet.

Diese Warnung sollte deaktiviert werden, nachdem Sie erfolgreich Portieren von Code auf die aktuelle Version.  Der Compiler möglicherweise falsch positive Ergebnisse, generiert diese Warnung für Code bieten, wenn keine verhaltensänderung vorhanden ist.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Im folgende Beispiel wird die C4342 generiert:

```cpp
// C4342.cpp
// compile with: /EHsc /W1
#include <fstream>
#pragma warning(default: 4342)
using namespace std;
struct X : public ofstream {
   X();
};

X::X() {
   open( "ofs_bug_ev.txt." );
   if ( is_open() ) {
      *this << "Text" << "<-should be text" << endl;   // C4342
      *this << ' ' << "<-should be space symbol" << endl;   // C4342
   }
}

int main() {
   X b;
   b << "Text" << "<-should be text" << endl;
   b << ' ' << "<-should be space symbol" << endl;
}
```
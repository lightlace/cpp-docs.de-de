---
title: Compilerwarnung (Stufe 4) C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: e087e3cd36ab85d6f3f6b5cfed1b55cac66ea142
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541698"
---
# <a name="compiler-warning-level-4-c4256"></a>Compilerwarnung (Stufe 4) C4256

"Function": der Konstruktor für die Klasse mit virtuellen Basen weist "..." auf. Aufrufe sind möglicherweise nicht mit älteren Versionen von Visual kompatibelC++

Mögliche Inkompatibilität.

Betrachten Sie folgendes Codebeispiel: Wenn die Definition des Konstruktors S2:: S2 (int i,...) mit einer Version des Microsoft C++ -Compilers vor Version 7 kompiliert wurde, das folgende Beispiel jedoch mit der aktuellen Version kompiliert wurde, funktioniert der Aufruf des Konstruktors für S3 aufgrund einer speziellen Änderung der Aufruf Konvention nicht ordnungsgemäß. Wenn beide mit Visual C++ 6,0 kompiliert wurden, funktioniert der-Befehl nicht ganz richtig, es sei denn, es wurden keine Parameter für die Auslassungs Zeichen übermittelt.

So beheben Sie diese Warnung

1. Verwenden Sie keine Ellipsen in einem Konstruktor.

1. Stellen Sie sicher, dass alle Komponenten in Ihrem Projekt mit der aktuellen Version (einschließlich aller Bibliotheken, die diese Klasse definieren oder referenzieren) erstellt werden, und deaktivieren Sie dann die Warnung mithilfe des [Warning](../../preprocessor/warning.md) -Pragmas.

Im folgenden Beispiel wird C4256 generiert:

```cpp
// C4256.cpp
// compile with: /W4
// #pragma warning(disable : 4256)
struct S1
{
};

struct S2: virtual public S1
{
   S2( int i, ... )    // C4256
   {
      i = 0;
   }
   /*
   // try the following line instead
   S2( int i)
   {
      i = 0;
   }
   */
};

void func1()
{
   S2 S3( 2, 1, 2 );   // C4256
   // try the following line instead
   // S2 S3( 2 );
}

int main()
{
}
```
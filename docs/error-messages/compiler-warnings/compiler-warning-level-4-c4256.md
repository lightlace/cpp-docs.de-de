---
title: Compilerwarnung (Stufe 4) C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: 3e8a3ab1b11c719730016e6a0cd248770cd89af8
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447773"
---
# <a name="compiler-warning-level-4-c4256"></a>Compilerwarnung (Stufe 4) C4256

"Function": Konstruktor für die Klasse mit virtuellen Basen besitzt "...". Aufrufe sind möglicherweise nicht mit älteren Versionen von Visual C++ kompatibel

Mögliche Inkompatibilitäten.

Betrachten Sie folgendes Codebeispiel. Wenn die Definition des Konstruktors S2::S2 (Int i,...) wurde mit einer Version von Microsoft kompiliert C++ Compiler vor Version 7, jedoch im folgenden Beispiel wird mithilfe der aktuellen Version kompiliert, den Aufruf des Konstruktors für S3 funktioniert nicht ordnungsgemäß aufgrund einer Änderung des besondere Schreibweisen-Aufrufkonvention. Wenn beide mit Visual C++ 6.0 kompiliert wurden, würde der Aufruf nicht ganz rechts, funktionieren nur, wenn keine Parameter für die Auslassungszeichen übergeben wurden.

Um diese Warnung zu beheben,

1. Verwenden Sie nicht mit den Auslassungspunkten in einem Konstruktor.

1. Stellen Sie sicher, dass alle Komponenten in ihrem Projekt, mit der aktuellen Version erstellt werden (einschließlich der Bibliotheken, die definieren, oder verweisen auf diese Klasse können), und deaktivieren Sie die Warnung mit dem [Warnung](../../preprocessor/warning.md) Pragma.

Im folgende Beispiel wird die C4256 generiert:

```
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
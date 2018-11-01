---
title: Compilerwarnung (Stufe 2) C4412
ms.date: 11/04/2016
f1_keywords:
- C4412
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
ms.openlocfilehash: 2c9d50fc3433321c0ca92366a512892212545754
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665516"
---
# <a name="compiler-warning-level-2-c4412"></a>Compilerwarnung (Stufe 2) C4412

> "*Funktion*': Funktionssignatur enthält Typ '*Typ*'; C++-Objekte sind nicht sicher zwischen reinem Code übergeben und gemischtem bzw. systemeigenem.

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt. Wenn Sie über Code, die verfügen als reine benötigt, es wird empfohlen, dass Sie damit Portieren C#.

Der Compiler hat eine potenziell unsichere Situation, die einen Laufzeitfehler verursachen könnte: erfolgt ein Aufruf von eine **/CLR: pure** Kompiliereinheit an eine Funktion, die über Dllimport und die Funktionssignatur importiert wurde, enthält einen unsicheren Typ . Ein Typ ist unsicher, wenn sie eine Memberfunktion enthält oder einen Datenmember, der einem unsicheren Typ oder eine Dereferenzierung zu einem unsicheren Typ ist.

Dies ist unsicher aufgrund der Unterschied in der Standard-Aufrufkonventionen zwischen reinen und systemeigenem Code (oder gemischten systemeigenen und verwalteten). Beim Importieren (über `dllimport`) eine Funktion in eine **/CLR: pure** Kompiliereinheit, stellen Sie sicher, dass die Deklarationen der einzelnen Typen in der Signatur in der Kompiliereinheit identisch, die die Funktion sind (Achten Sie besonders auf exportiert Unterschiede bei der impliziten Aufrufkonventionen).

Eine virtuelle Memberfunktion ist besonders anfällig für unerwartete Ergebnisse zurückgibt.  Allerdings sollten auch eine nicht virtuelle Funktion getestet werden, um sicherzustellen, dass Sie die richtigen Ergebnisse zu erhalten. Wenn Sie sicher sind, dass Sie die richtigen Ergebnisse erhalten, können Sie diese Warnung ignorieren.

C4412 ist standardmäßig deaktiviert. Finden Sie unter [Compiler Warnings, die Are Off standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md) und [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md) für Weitere Informationen.

Um diese Warnung zu beheben, entfernen Sie alle Funktionen, von dem Typ.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4412 generiert.

```cpp
// C4412.cpp
// compile with: /c /W2 /clr:pure
#pragma warning (default : 4412)

struct Unsafe {
   virtual void __cdecl Test();
};

struct Safe {
   int i;
};

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   Unsafe *pUnsafe = func();   // C4412
   // pUnsafe->Test();

   Safe *pSafe = func2();   // OK
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird eine Headerdatei, die zwei Typen deklariert. Die `Unsafe` Typ ist unsicher, da sie über eine Memberfunktion verfügt.

```cpp
// C4412.h
struct Unsafe {
   // will be __clrcall if #included in pure compilation
   // defaults to __cdecl in native or mixed mode compilation
   virtual void Test(int * pi);

   // try the following line instead
   // virtual void __cdecl Test(int * pi);
};

struct Safe {
   int i;
};
```

## <a name="example"></a>Beispiel

In diesem Beispiel werden Funktionen mit den in der Headerdatei definierten Typen exportiert.

```cpp
// C4412_2.cpp
// compile with: /LD
#include "C4412.h"

void Unsafe::Test(int * pi) {
   *pi++;
}

__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }
```

## <a name="example"></a>Beispiel

Die Standardaufrufkonvention einem **/CLR: pure** Kompilierung unterscheidet sich von der systeminterne Kompilierung.  Wenn C4412.h eingeschlossen ist, wird `Test` standardmäßig `__clrcall`. Wenn Sie kompilieren und führen Sie dieses Programm (verwenden Sie keine **/c**), die Anwendung wird eine Ausnahme ausgelöst.

Im folgende Beispiel wird die C4412 generiert.

```cpp
// C4412_3.cpp
// compile with: /W2 /clr:pure /c /link C4412_2.lib
#pragma warning (default : 4412)
#include "C4412.h"

__declspec(dllimport) Unsafe * __cdecl func();
__declspec(dllimport) Safe * __cdecl func2();

int main() {
   int n = 7;
   Unsafe *pUnsafe = func();   // C4412
   pUnsafe->Test(&n);

   Safe *pSafe = func2();   // OK
}
```
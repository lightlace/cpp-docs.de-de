---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: 3a8dce21aa707a1a52c647c9efee5ab806511ca8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454560"
---
# <a name="noinline"></a>noinline

## <a name="microsoft-specific"></a>Microsoft-spezifisch

**__declspec(noinline)** weist den Compiler niemals eine inlineersetzung eine bestimmten Member-Funktion (Funktion in einer Klasse).

Es lohnt sich möglicherweise, eine Funktion nicht inline auszuführen, wenn die Funktion klein und für die Leistung des Codes nicht wichtig ist. Das ist der Fall, wenn die Funktion klein ist und wahrscheinlich nicht häufig aufgerufen wird, z. B. eine Funktion, die eine Fehlerbedingung behandelt.

Beachten Sie, dass wenn eine Funktion markiert ist **Noinline**, die aufrufende Funktion werden kleiner und somit selbst ein Kandidat für Compiler-inlining.

```cpp
class X {
   __declspec(noinline) int mbrfunc() {
      return 0;
   }   // will not inline
};
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \__forceinline](inline-functions-cpp.md)


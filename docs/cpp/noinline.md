---
title: Noinline | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noinline_cpp
dev_langs:
- C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7a2831251d00f0dc24b1cfab7beeecaff100962
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092285"
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


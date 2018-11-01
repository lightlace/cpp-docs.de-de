---
title: Compilerfehler C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: 32aed1dfd957035cdd60fa97bd9ec534de03cb06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547940"
---
# <a name="compiler-error-c3896"></a>Compilerfehler C3896

'Member': Fehlerhafte Initialisierung: Dieser literal-Datenmember kann nur mit "Nullptr" initialisiert werden

Ein [literal](../../windows/literal-cpp-component-extensions.md) Datenmember wurde nicht ordnungsgemäß initialisiert.  Finden Sie unter ["nullptr"](../../windows/nullptr-cpp-component-extensions.md) für Weitere Informationen.

Im folgende Beispiel wird die C3896 generiert:

```
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```
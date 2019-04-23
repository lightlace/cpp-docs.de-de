---
title: Compilerfehler C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: 00e103720dc666b17566b67da19d4e908bb3addd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776079"
---
# <a name="compiler-error-c3896"></a>Compilerfehler C3896

'Member': Fehlerhafte Initialisierung: Dieser literal-Datenmember kann nur mit "Nullptr" initialisiert werden

Ein [literal](../../extensions/literal-cpp-component-extensions.md) Datenmember wurde nicht ordnungsgemäß initialisiert.  Finden Sie unter ["nullptr"](../../extensions/nullptr-cpp-component-extensions.md) für Weitere Informationen.

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
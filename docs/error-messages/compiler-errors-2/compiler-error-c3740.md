---
title: Compilerfehler C3740
ms.date: 11/04/2016
f1_keywords:
- C3740
helpviewer_keywords:
- C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
ms.openlocfilehash: dd493e4759b2fb70918bf94f14f4ada022e326b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547224"
---
# <a name="compiler-error-c3740"></a>Compilerfehler C3740

Vorlagen können keine Datenquelle, oder Empfangen von Ereignissen

Eine auf Vorlagen basierenden Klasse oder Struktur kann nicht enthalten [Ereignisse](../../cpp/event-handling.md).

Im folgende Beispiel wird die C3740 generiert:

```
// C3740.cpp
template <typename T>   // Delete the template specification
struct E {
   __event void f();   // C3740
};

int main() {
}
```
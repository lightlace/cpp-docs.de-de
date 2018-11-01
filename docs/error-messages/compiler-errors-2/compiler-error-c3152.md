---
title: Compilerfehler C3152
ms.date: 11/04/2016
f1_keywords:
- C3152
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
ms.openlocfilehash: 270d2fb02365f9c2460257d96bb5f6028707553e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624769"
---
# <a name="compiler-error-c3152"></a>Compilerfehler C3152

'construct' : 'keyword' kann nur auf eine Klasse, Struktur oder virtuelle Memberfunktion angewendet werden.

Bestimmte Schlüsselwörter können nur auf eine C++-Klasse angewendet werden.

Im folgenden Beispiel wird C3152 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3152.cpp
// compile with: /clr /c
ref class C {
   int (*pfn)() sealed;   // C3152
   virtual int g() sealed;   // OK
};
```

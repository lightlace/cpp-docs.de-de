---
title: Compilerfehler C2459
ms.date: 11/04/2016
f1_keywords:
- C2459
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
ms.openlocfilehash: c49c348968f750c7e5c64ab9ef4f298d3fc74f67
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743990"
---
# <a name="compiler-error-c2459"></a>Compilerfehler C2459

' Identifier ': wird definiert. als anonymer Member kann nicht hinzugefügt werden.

Eine Klasse, Struktur oder Union wird in Ihrem eigenen Bereich durch ein Member einer anonymen Union neu definiert.

Im folgenden Beispiel wird C2459 generiert:

```cpp
// C2459.cpp
// compile with: /c
class C {
   union { int C; };   // C2459
   union { int D; };
};
```

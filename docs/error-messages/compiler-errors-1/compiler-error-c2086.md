---
title: Compilerfehler C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: 417763e8c26918d3cd83702b283244d1c13d9d1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735748"
---
# <a name="compiler-error-c2086"></a>Compilerfehler C2086

' Bezeichner ': Neudefinition

Der Bezeichner ist mehrmals definiert, oder eine nachfolgende Deklaration unterscheidet sich von einer vorherigen Deklaration.

C2086 kann auch das Ergebnis eines inkrementellen Aufbaus für C# eine referenzierte Assembly sein. Erstellen Sie C# die Assembly neu, um diesen Fehler zu beheben.

Im folgenden Beispiel wird C2086 generiert:

```cpp
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```

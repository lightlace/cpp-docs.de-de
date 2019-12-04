---
title: Compilerfehler C2394
ms.date: 11/04/2016
f1_keywords:
- C2394
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
ms.openlocfilehash: 2c8c23939298f5603b59636ede08b65acaa0f22b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744991"
---
# <a name="compiler-error-c2394"></a>Compilerfehler C2394

' your_type:: operator' op ' ': CLR oder winrtoperator ist ungültig. Mindestens ein Parameter muss die folgenden Typen aufweisen: 't ^ ', 't ^% ', 't ^ & ', wobei T = ' your_type ' ist.

Ein Operator in einer Windows-Runtime oder einem verwalteten Typen hatte nicht mindestens einen Parameter, dessen Typ mit dem Typen des Operatorrückgabewerts identisch ist.

Im folgenden Beispiel wird C2394 generiert:

```cpp
// C2394.cpp
// compile with: /clr /c
ref struct Y {
   static Y^ operator -(int i, char c);   // C2394

   // OK
   static Y^ operator -(Y^ hY, char c);
   // or
   static Y^ operator -(int i, Y^& rhY);
};
```

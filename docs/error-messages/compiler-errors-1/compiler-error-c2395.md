---
title: Compilerfehler C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: 2ac59856770b04dd3c4ea14360e0a83dd99f2150
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744939"
---
# <a name="compiler-error-c2395"></a>Compilerfehler C2395

'your_type::operator'op'': CLR oder WinRT-Operator ist ungültig. Mindestens ein Parameter muss die folgenden Typen aufweisen: 't ', 't% ', 't & ', 't ^ ', 't ^% ', 't ^ & ', wobei T = ' your_type ' ist.

Ein Operator in einer Windows-Runtime oder einem verwalteten Typen hatte nicht mindestens einen Parameter, dessen Typ mit dem Typen des Operatorrückgabewerts identisch ist.

Im folgenden Beispiel wird C2395 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```

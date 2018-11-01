---
title: Compilerfehler C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: dd3bd922e2bfa61da2da87d368bb4b28237161f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599836"
---
# <a name="compiler-error-c2395"></a>Compilerfehler C2395

'your_type::operator'op'': CLR oder WinRT-Operator ist ungültig. Mindestens ein Parameter muss einer der folgenden Typen sein: 'T', 'T%', 'T&', 'T^', 'T^%', 'T^&', wobei T = 'your_type' ist

Ein Operator in einer Windows-Runtime oder einem verwalteten Typen hatte nicht mindestens einen Parameter, dessen Typ mit dem Typen des Operatorrückgabewerts identisch ist.

Im folgenden Beispiel wird C2395 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
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
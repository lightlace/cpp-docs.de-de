---
title: Compilerfehler C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: dd3bd922e2bfa61da2da87d368bb4b28237161f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303655"
---
# <a name="compiler-error-c2395"></a>Compilerfehler C2395

' your_type ': CLR- oder WinRT-Operator ist ungültig. Mindestens ein Parameter muss die folgenden Typen aufweisen: ' T ', ' t %', ' t & ", ' t ^', ' t ^ %', ' t ^ &", wobei T = 'Your_type'

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
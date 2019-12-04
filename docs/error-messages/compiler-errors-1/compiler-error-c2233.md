---
title: Compilerfehler C2233
ms.date: 11/04/2016
f1_keywords:
- C2233
helpviewer_keywords:
- C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
ms.openlocfilehash: 066f28bfaacd1ad2e7645822aef082e43e863327
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759255"
---
# <a name="compiler-error-c2233"></a>Compilerfehler C2233

' Identifier ': Arrays von Objekten mit Arrays der Größe 0 (null) sind unzulässig.

Jedes-Objekt in einem Array muss mindestens ein-Element enthalten.

Im folgenden Beispiel wird C2233 generiert:

```cpp
// C2233.cpp
// compile with: /c
class A {
   char somearray[1];
};

class B {
   char zeroarray[];
};

A array[100];   // OK
B array2[100];   // C2233
```

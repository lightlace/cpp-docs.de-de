---
title: Compilerfehler C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: 7f6b514231bcda18404e891e0acbe457c8f95146
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738777"
---
# <a name="compiler-error-c3200"></a>Compilerfehler C3200

"Template": Ungültiges Vorlagen Argument für den Vorlagen Parameter "Parameter", eine Klassen Vorlage wurde erwartet.

Sie haben ein ungültiges Argument an eine Klassen Vorlage übermittelt. Die Klassen Vorlage erwartet die Vorlage als Parameter. Im folgenden Beispiel wird durch Aufrufen von `Y<int, int> aY` C3200 generiert. Der erste Parameter muss eine Vorlage sein, z. b. `Y<X, int> aY`.

```cpp
// C3200.cpp
template<typename T>
class X
{
};

template<template<typename U> class T1, typename T2>
class Y
{
};

int main()
{
   Y<int, int> y;   // C3200
}
```

---
title: Compilerfehler C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: 574a04923c20c3104083a6aa05a71838e7ec13d2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760503"
---
# <a name="compiler-error-c2719"></a>Compilerfehler C2719

'parameter': formeller Parameter mit __declspec(align('#')) wird nicht ausgerichtet

Der Modifizierer [align](../../cpp/align-cpp.md) `__declspec` ist für Funktionsparameter nicht zulässig. Die Funktionsparameterausrichtung wird durch die verwendete Aufrufkonvention gesteuert. Weitere Informationen finden Sie unter [Aufrufen von Konventionen](../../cpp/calling-conventions.md).

Im folgenden Beispiel wird C2719 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```

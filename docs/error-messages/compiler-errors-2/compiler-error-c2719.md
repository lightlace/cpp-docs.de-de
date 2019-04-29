---
title: Compilerfehler C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: d635601fbf8b36218fb47c09444f3f5d023c823e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383086"
---
# <a name="compiler-error-c2719"></a>Compilerfehler C2719

'parameter': formeller Parameter mit __declspec(align('#')) wird nicht ausgerichtet

Die [ausrichten](../../cpp/align-cpp.md) `__declspec` Modifizierer ist in Funktionsparametern nicht zulässig. Die Funktionsparameterausrichtung wird durch die verwendete Aufrufkonvention gesteuert. Weitere Informationen finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md).

Im folgenden Beispiel wird C2719 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
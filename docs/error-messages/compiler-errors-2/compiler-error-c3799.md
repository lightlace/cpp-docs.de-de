---
title: Compilerfehler C3799
ms.date: 11/04/2016
f1_keywords:
- C3799
helpviewer_keywords:
- C3799
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
ms.openlocfilehash: 19ff414bde9bb24fca62fd10cfef6d18109199e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553542"
---
# <a name="compiler-error-c3799"></a>Compilerfehler C3799

indizierte Eigenschaft kann keine leere Parameterliste aufweisen.

Eine indizierte Eigenschaft wurde falsch deklariert. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von Eigenschaften in C++ / CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3799 generiert und gezeigt, wie Sie diesen Fehler beheben.

```cpp
// C3799.cpp
// compile with: /clr /c
ref struct C {
   property int default[] {   // C3799
   // try the following line instead
   // property int default[int] {
      int get(int index) { return 0; }
      void set(int index, int value) {}
   }
};
```
---
title: Compilerwarnung (Stufe 1) C4965
ms.date: 11/04/2016
f1_keywords:
- C4965
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
ms.openlocfilehash: ac1ffc1626a8b72fd7c9026afb6c6a54bace3750
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052230"
---
# <a name="compiler-warning-level-1-c4965"></a>Compilerwarnung (Stufe 1) C4965

Implizites Feld der Ganzzahl 0; Verwenden von nullptr oder expliziter Umwandlung

Visual C++ Features implizites Boxing von Werttypen. Eine Anweisung, die zu einer NULL-Zuweisung geführt hat, C++ bei der verwaltete Erweiterungen für jetzt verwendet werden, wird zu einer Zuweisung zu einer ganzzahligen

Weitere Informationen finden Sie unter [Boxing](../../extensions/boxing-cpp-component-extensions.md)definiert sind.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4965 generiert.

```cpp
// C4965.cpp
// compile with: /clr /W1
int main() {
   System::Object ^o = 0;   // C4965

   // the previous line is the same as the following line
   // using Managed Extensions for C++
   // System::Object *o = __box(0);

   // OK
   System::Object ^o2 = nullptr;
   System::Object ^o3 = safe_cast<System::Object^>(0);
}
```
---
title: Compilerfehler C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: 6772572d29765370d6cdbf52ed8470ff2f3f054e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758072"
---
# <a name="compiler-error-c3675"></a>Compilerfehler C3675

"Function": ist reserviert, da "Property" definiert ist.

Wenn Sie eine einfache Eigenschaft deklarieren, generiert der Compiler die Get-und set-Accessormethoden, und diese Namen sind im Gültigkeitsbereich des Programms vorhanden.  Die vom Compiler generierten Namen werden gebildet, indem get_ vorangestellt und dem Eigenschaftsnamen set_.  Daher können Sie keine Funktionen mit dem gleichen Namen wie die vom Compiler generierten Accessoren deklarieren.

Weitere Informationen finden Sie unter [property](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3675 generiert.

```cpp
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```

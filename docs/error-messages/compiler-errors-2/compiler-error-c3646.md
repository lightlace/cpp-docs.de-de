---
title: Compilerfehler C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 04ff1d026c97c56611f8b786d8a7254db711e4a8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769030"
---
# <a name="compiler-error-c3646"></a>Compilerfehler C3646

> "Spezifizierer": Unbekannter Überschreibungsspezifizierer

## <a name="remarks"></a>Hinweise

Der Compiler hat ein Token gefunden, an der Position, in dem sie ein Überschreibungsspezifizierer wurde erwartet, aber das Token wurde nicht vom Compiler erkannt, wird.

Z. B. wenn das nicht erkannte *Spezifizierer* ist **_NOEXCEPT**, ersetzen Sie ihn mit dem Schlüsselwort **"noexcept"**.

Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3646 generiert und zeigt, wie Sie diesen Fehler beheben:

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```
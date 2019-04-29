---
title: Compilerfehler C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 04ff1d026c97c56611f8b786d8a7254db711e4a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385588"
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
---
title: Compilerfehler C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: df2e52631ed75cc4a473429ea35e136ed0a88f98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606725"
---
# <a name="compiler-error-c3646"></a>Compilerfehler C3646

> "Spezifizierer": Unbekannter Überschreibungsspezifizierer

## <a name="remarks"></a>Hinweise

Der Compiler hat ein Token gefunden, an der Position, in dem sie ein Überschreibungsspezifizierer wurde erwartet, aber das Token wurde nicht vom Compiler erkannt, wird.

Z. B. wenn das nicht erkannte *Spezifizierer* ist **_NOEXCEPT**, ersetzen Sie ihn mit dem Schlüsselwort **"noexcept"**.

Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md).

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
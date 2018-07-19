---
title: Compilerfehler C3646 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3646
dev_langs:
- C++
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c038520c1a35fa5264e1e98b074687efb336d028
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "35658610"
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
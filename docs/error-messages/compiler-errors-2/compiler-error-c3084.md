---
title: Compilerfehler C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 337cd7f37bf94c7a3d5cffe6b167d4661e3b0a81
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751455"
---
# <a name="compiler-error-c3084"></a>Compilerfehler C3084

"Funktion": ein Finalizer/Destruktor kann nicht "Schlüsselwort" sein.

Ein Finalizer oder Destruktor wurde falsch deklariert.

Beispielsweise sollte ein Destruktor nicht als versiegelt gekennzeichnet werden.  Abgeleitete Typen können nicht auf den Destruktor zugreifen.  Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md) schreibungen und [Dekonstruktoren und Finalizer in Gewusst wie: definieren und Verarbeiten von Klassen und StrukturenC++(/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3084 generiert.

```cpp
// C3084.cpp
// compile with: /clr /c
ref struct R {
protected:
   !R() sealed;   // C3084
   !R() abstract;   // C3084
   !R();
};
```

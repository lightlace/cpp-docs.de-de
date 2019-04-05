---
title: Compilerfehler C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 01e229fe0ae5bf9e04c577bb653ff1ed7fdb33bf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773899"
---
# <a name="compiler-error-c3084"></a>Compilerfehler C3084

"Funktion": ein Finalizer/Destruktor kann nicht "Schlüsselwort" sein.

Ein Finalizer oder Destruktor wurde falsch deklariert.

Beispielsweise sollte ein Destruktor nicht als versiegelt gekennzeichnet werden.  Abgeleitete Typen können nicht auf den Destruktor zugreifen.  Weitere Informationen finden Sie unter [explizite Überschreibungen](../../extensions/explicit-overrides-cpp-component-extensions.md) und [Destruktoren und Finalizer unter How to: Definieren und Verarbeiten von Klassen und Strukturen (C++ / CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3084 generiert.

```
// C3084.cpp
// compile with: /clr /c
ref struct R {
protected:
   !R() sealed;   // C3084
   !R() abstract;   // C3084
   !R();
};
```
---
title: Compilerfehler C3665
ms.date: 11/04/2016
f1_keywords:
- C3665
helpviewer_keywords:
- C3665
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
ms.openlocfilehash: 30aaf67ac9f912059bb5726681e61feabc1e557d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644118"
---
# <a name="compiler-error-c3665"></a>Compilerfehler C3665

'Destruktor': Der Überschreibungsspezifizierer 'Schlüsselwort' ist für einen Destruktor/Finalizer nicht zulässig

Es wurde ein Schlüsselwort verwendet, das für einen Destruktor oder Finalizer nicht zulässig ist.

Es kann beispielsweise für einen Destruktor oder Finalizer kein neuer Slot angefordert werden.  Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md) und [Destruktoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Im folgende Beispiel wird die C3665 generiert:

```
// C3665.cpp
// compile with: /clr
public ref struct R {
   virtual ~R() { }
   virtual void a() { }
};

public ref struct S : R {
   virtual ~S() new {}   // C3665
   virtual void a() new {}   // OK
};
```
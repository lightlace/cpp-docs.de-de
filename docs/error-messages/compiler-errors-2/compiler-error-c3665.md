---
title: Compilerfehler C3665
ms.date: 11/04/2016
f1_keywords:
- C3665
helpviewer_keywords:
- C3665
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
ms.openlocfilehash: 40de7a7b1ede5e6dbbc20d2128b782c0ad6f798b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221593"
---
# <a name="compiler-error-c3665"></a>Compilerfehler C3665

'Destruktor': Der Überschreibungsspezifizierer 'Schlüsselwort' ist für einen Destruktor/Finalizer nicht zulässig

Es wurde ein Schlüsselwort verwendet, das für einen Destruktor oder Finalizer nicht zulässig ist.

Es kann beispielsweise für einen Destruktor oder Finalizer kein neuer Slot angefordert werden.  Weitere Informationen finden Sie unter [explizite Überschreibungen](../../extensions/explicit-overrides-cpp-component-extensions.md) und [Destruktoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

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
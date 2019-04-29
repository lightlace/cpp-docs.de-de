---
title: Compilerfehler C3657
ms.date: 11/04/2016
f1_keywords:
- C3657
helpviewer_keywords:
- C3657
ms.assetid: 89a28a18-4c17-43a1-bda6-deb52c32d203
ms.openlocfilehash: f979d5776bea5e8fb6e0255bdcdeaacb284932ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410485"
---
# <a name="compiler-error-c3657"></a>Compilerfehler C3657

Destruktoren können keine explizite Überschreibung durchführen oder explizit überschrieben werden.

Destruktoren oder Finalizer können nicht explizit außer Kraft gesetzt werden. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3657 generiert.

```
// C3657.cpp
// compile with: /clr
public ref struct I {
   virtual ~I() { }
   virtual void a();
};

public ref struct D : I {
   virtual ~D() = I::~I {}   // C3657
   virtual void a() = I::a {}   // OK
};
```
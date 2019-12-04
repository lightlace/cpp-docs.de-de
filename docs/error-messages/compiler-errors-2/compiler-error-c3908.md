---
title: Compilerfehler C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 2b57f3346427ff548d11fe776e909eca99433a81
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749034"
---
# <a name="compiler-error-c3908"></a>Compilerfehler C3908

die Zugriffsebene ist weniger restriktiv als "Konstrukt".

Eine Eigenschaftenaccessormethode (Get oder Set) kann nicht weniger einschränkenden Zugriff haben als der für die Eigenschaft selbst angegebene Zugriff.  Gleiches gilt für Ereignisaccessormethoden.

Weitere Informationen finden Sie unter [Eigenschaft](../../extensions/property-cpp-component-extensions.md) und [Ereignis](../../extensions/event-cpp-component-extensions.md).

Im folgenden Beispiel wird C3908 generiert:

```cpp
// C3908.cpp
// compile with: /clr
ref class X {
protected:
   property int i {
   public:   // C3908 property i is protected
      int get();
   private:
      void set(int);   // OK more restrictive
   };
};
```

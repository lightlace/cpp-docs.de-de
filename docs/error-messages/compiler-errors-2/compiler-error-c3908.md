---
title: Compilerfehler C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: e11d830c3d662ea424caadeb50df669700f8c78f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406549"
---
# <a name="compiler-error-c3908"></a>Compilerfehler C3908

die Zugriffsebene ist weniger restriktiv als 'Konstrukt'

Eine Eigenschaftenaccessormethode ("Get" oder "Set") darf nicht weniger restriktiv als der Zugriff auf die Eigenschaft selbst zugreifen.  Auf ähnliche Weise für die Methoden der eigenschaftenzugriffsmethode.

Weitere Informationen finden Sie unter [Eigenschaft](../../extensions/property-cpp-component-extensions.md) und [Ereignis](../../extensions/event-cpp-component-extensions.md).

Im folgende Beispiel wird die C3908 generiert:

```
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
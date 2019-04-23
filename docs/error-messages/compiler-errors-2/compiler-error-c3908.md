---
title: Compilerfehler C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: e11d830c3d662ea424caadeb50df669700f8c78f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778474"
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
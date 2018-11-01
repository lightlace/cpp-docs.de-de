---
title: Compilerfehler C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 84b21f20cbc8203a9cd70e487738c34c6ad3a89b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598926"
---
# <a name="compiler-error-c3908"></a>Compilerfehler C3908

die Zugriffsebene ist weniger restriktiv als 'Konstrukt'

Eine Eigenschaftenaccessormethode ("Get" oder "Set") darf nicht weniger restriktiv als der Zugriff auf die Eigenschaft selbst zugreifen.  Auf ähnliche Weise für die Methoden der eigenschaftenzugriffsmethode.

Weitere Informationen finden Sie unter [Eigenschaft](../../windows/property-cpp-component-extensions.md) und [Ereignis](../../windows/event-cpp-component-extensions.md).

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
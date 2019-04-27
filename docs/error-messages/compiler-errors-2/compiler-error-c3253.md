---
title: Compilerfehler C3253
ms.date: 11/04/2016
f1_keywords:
- C3253
helpviewer_keywords:
- C3253
ms.assetid: da40be26-0f78-4730-8727-ad11cddf8869
ms.openlocfilehash: 5d161dfab8dff48a1ddd5a8a5036c0bb4d5549aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173248"
---
# <a name="compiler-error-c3253"></a>Compilerfehler C3253

'Funktion': Fehler bei der expliziten Überschreibung

Eine explizite Überschreibung wurde falsch angegeben. Sie können nicht z. B. eine Implementierung für eine Außerkraftsetzung angeben, die Sie auch als reine angeben. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../extensions/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3253 generiert:

```
// C3253.cpp
// compile with: /clr
public interface struct I {
   void a();
   void b();
   void c();
};

public ref struct R : I {
   virtual void a() = 0, I::a {}   // C3253
   virtual void b() = I::a {}   // OK
   virtual void c() = 0;   // OK
};
```
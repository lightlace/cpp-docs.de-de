---
title: Compilerfehler C3670 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3670
dev_langs:
- C++
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1129a25e628710121d667a44022eec5a0450b092
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115332"
---
# <a name="compiler-error-c3670"></a>Compilerfehler C3670

"override": kann nicht zugegriffen werden Basisklassenmethode 'Methode' kann nicht überschrieben werden

Eine Außerkraftsetzung kann nur auf eine Funktion stattfinden, deren Zugriffsebene, die es in einem abgeleiteten Typ zur Verfügung stellt. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3670 generiert:

```
// C3670.cpp
// compile with: /clr /c
public ref class C {
// Uncomment the following line to resolve.
// public:
   virtual void g() { }
};

public ref class D : public C {
public:
   virtual void f() new sealed = C::g {};   // C3670
};
```
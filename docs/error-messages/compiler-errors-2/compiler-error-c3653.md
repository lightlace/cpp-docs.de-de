---
title: Compilerfehler C3653 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3653
dev_langs:
- C++
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d0409317cb0cdf6a248554cba2e18d7f9d2e0e0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019002"
---
# <a name="compiler-error-c3653"></a>Compilerfehler C3653

'Funktion': kann nicht als benannte Überschreibung verwendet werden: eine Funktion, die überschrieben wurde nicht gefunden; haben Sie vergessen, auf den Funktionsnamen explizit mithilfe einer:: Operator?

Eine explizite Überschreibung angegeben, eine Funktion, die nicht in einer beliebigen Schnittstelle gefunden wurde. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3653 generiert:

```
// C3653.cpp
// compile with: /clr
public interface struct I {
   void h();
};

public ref struct X : public I {
   virtual void f() new sealed = J {};   // C3653 no J in scope
   virtual void g() {}   // OK
   virtual void h() new sealed = I::h {};   // OK
};
```
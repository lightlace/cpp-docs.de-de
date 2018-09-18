---
title: Compilerfehler C3671 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3671
dev_langs:
- C++
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 455b9e2a6accbc98ee8bce49a35a672d9cd9c20d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017067"
---
# <a name="compiler-error-c3671"></a>Compilerfehler C3671

"" function_1 ": Funktion überschreibt nicht die 'Funktion_2'

Wenn Sie explizite Überschreibungssyntax verwenden zu können, generiert der Compiler einen Fehler, wenn eine Funktion nicht überschrieben wird.  Finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3671 generiert.

```
// C3671.cpp
// compile with: /clr /c
ref struct S {
   virtual void f();
};

ref struct S1 : S {
   virtual void f(int) new sealed = S::f;   // C3671
   virtual void f() new sealed = S::f;
};
```
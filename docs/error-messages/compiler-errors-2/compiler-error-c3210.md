---
title: Compilerfehler C3210 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3210
dev_langs:
- C++
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 804586a866f6a4d2c3cf206af14e0e2f907ed1b6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037111"
---
# <a name="compiler-error-c3210"></a>Compilerfehler C3210

'Typ': Zugriffsdeklaration kann nur auf ein Basisklassenmember angewendet werden

Ein [using-Deklaration](../../cpp/using-declaration.md) wurde falsch angegeben.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3210 generiert.

```
// C3210.cpp
// compile with: /c
struct A {
protected:
   int i;
};

struct B {
   using A::i;   // C3210
};

struct C : public A {
   using A::i;   // OK
};
```
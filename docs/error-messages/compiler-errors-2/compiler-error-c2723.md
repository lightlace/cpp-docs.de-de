---
title: Compilerfehler C2723 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2723
dev_langs:
- C++
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b1be2d81ecec7eb96fd9c1cd7e9938ce509f71e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072016"
---
# <a name="compiler-error-c2723"></a>Compilerfehler C2723

„Funktion“: Spezifizierer „Spezifizierer“ ist in Funktionsdefinition unzulässig.

Der Spezifizierer darf nicht mit einer Funktionsdefinition außerhalb einer Klassendeklaration vorkommen. Der `virtual`-Spezifizierer kann nur in einer Deklaration einer Memberfunktion innerhalb einer Klassendeklaration angegeben werden.

Im folgenden Beispiel wird C2723 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2723.cpp
struct X {
   virtual void f();
   virtual void g();
};

virtual void X::f() {}   // C2723

// try the following line instead
void X::g() {}
```
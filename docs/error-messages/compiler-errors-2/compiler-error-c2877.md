---
title: Compilerfehler C2877 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2877
dev_langs:
- C++
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2f293cefdc37c4adb2882f52d6676dcd912cfef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047537"
---
# <a name="compiler-error-c2877"></a>Compilerfehler C2877

'Symbol' kann nicht zugegriffen werden, von "Klasse"

Alle Elemente, die von einer Basisklasse abgeleitet, muss in der abgeleiteten Klasse zugegriffen werden kann.

Im folgende Beispiel wird die C2877 generiert:

```
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```
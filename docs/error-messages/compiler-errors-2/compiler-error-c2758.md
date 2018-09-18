---
title: Compilerfehler C2758 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2758
dev_langs:
- C++
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ffa6d33dba70a463d789f3b0f016dc1d157eb65
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072926"
---
# <a name="compiler-error-c2758"></a>Compilerfehler C2758

'member': Ein Member eines Verweistyps muss initialisiert werden

Der Compilerfehler C2758 wird ausgelöst, wenn der Konstruktor ein Member des Verweistyps in einer Initialisiererliste nicht initialisiert. Der Compiler lässt das Member undefiniert. Verweismembervariablen müssen initialisiert werden, wenn sie deklariert werden, oder sie müssen einen Wert in der Initialisierungsliste des Konstruktors erhalten.

Im folgenden Beispiel wird C2758 generiert:

```
// C2758.cpp
// Compile by using: cl /W3 /c C2758.cpp
struct A {
   const int i;

   A(int n) { };   // C2758
   // try the following line instead
   // A(int n) : i{n} {};
};
```
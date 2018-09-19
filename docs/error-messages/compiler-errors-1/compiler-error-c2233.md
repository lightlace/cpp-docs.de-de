---
title: Compilerfehler C2233 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2233
dev_langs:
- C++
helpviewer_keywords:
- C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 224e32735cb1cc4ad9e02c78f07e9efb9f5627bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083339"
---
# <a name="compiler-error-c2233"></a>Compilerfehler C2233

'Bezeichner': Arrays von Objekten, die Größe 0 (null) enthalten sind nicht zulässig

Jedes Objekt in einem Array muss mindestens ein Element enthalten.

Im folgende Beispiel wird die C2233 generiert:

```
// C2233.cpp
// compile with: /c
class A {
   char somearray[1];
};

class B {
   char zeroarray[];
};

A array[100];   // OK
B array2[100];   // C2233
```
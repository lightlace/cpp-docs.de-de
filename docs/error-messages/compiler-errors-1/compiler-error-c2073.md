---
title: Compilerfehler C2073 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2073
dev_langs:
- C++
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 950ca9551a605da392c1f033cb1784ff43a7fefc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112368"
---
# <a name="compiler-error-c2073"></a>Compilerfehler C2073

'Bezeichner': die Elemente der teilinitialisierung eines Arrays müssen über einen Standardkonstruktor verfügen

Für ein Array von benutzerdefinierten Typen oder Konstanten wurden zu wenige Initialisierer angegeben. Wenn keine explizite Initialisierung und kein entsprechender Konstruktor für einen Arraymember angeben nicht angegeben werden, muss ein Standardkonstruktor angegeben werden.

Im folgende Beispiel wird die C2073 generiert:

```
// C2073.cpp
class A {
public:
   A( int );   // constructor for ints only
};
A a[3] = { A(1), A(2) };   // C2073, no default constructor
```

```
// C2073b.cpp
// compile with: /c
class B {
public:
   B();   // default constructor declared
   B( int );
};
B b[3] = { B(1), B(2) };   // OK
```
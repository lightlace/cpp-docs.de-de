---
title: Compilerfehler C2805
ms.date: 11/04/2016
f1_keywords:
- C2805
helpviewer_keywords:
- C2805
ms.assetid: c997dc56-e199-442f-b94e-ac551ec9b015
ms.openlocfilehash: b0b3c0d4291787fb0b5664baa9159c84c8549dfd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282070"
---
# <a name="compiler-error-c2805"></a>Compilerfehler C2805

binärer 'Operator Operator' hat zu wenig Parameter

Der binäre Operator hat keine Parameter.

Im folgende Beispiel wird die C2805 generiert:

```
// C2805.cpp
// compile with: /c
class X {
public:
   X operator< ( void );   // C2805 must take one parameter
   X operator< ( X );   // OK
};
```
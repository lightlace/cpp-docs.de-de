---
title: Compilerfehler C2523
ms.date: 11/04/2016
f1_keywords:
- C2523
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
ms.openlocfilehash: 88a55a469fb8bc08d2ae73209c2e98a99dbc1df0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482017"
---
# <a name="compiler-error-c2523"></a>Compilerfehler C2523

' Klasse:: ~ Identifier ": Destruktor/Finalizer-Tag stimmt nicht überein

Der Name des Destruktors muss der Klassenname mit einer vorangestelltentilde (`~`). Sind nur Member mit den gleichen Namen wie die Klasse, Konstruktor und Destruktor.

Im folgende Beispiel wird die C2523 generiert:

```
// C2523.cpp
// compile with: /c
class A {
   ~B();    // C2523
   ~A();   // OK
};
```
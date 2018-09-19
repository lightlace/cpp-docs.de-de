---
title: Compilerfehler C2534 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2534
dev_langs:
- C++
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2febeeeb3b6c0e394070339f2310a22c1326ab5c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049032"
---
# <a name="compiler-error-c2534"></a>Compilerfehler C2534

"Bezeichner": Konstruktor kann keinen Wert zurückgeben

Ein Konstruktor kann keinen Wert zurückgeben oder keinen Rückgabetyp haben (nicht einmal eine `void` Rückgabetyp).

Dieser Fehler möglicherweise behoben werden, durch das Entfernen der `return` Anweisung aus der Konstruktordefinition.

Im folgende Beispiel wird die C2534 generiert:

```
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```
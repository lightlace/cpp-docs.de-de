---
title: Compilerfehler C2572 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2572
dev_langs:
- C++
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56d49fe95dca7861b18d417dcd6049a12776e8d2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057834"
---
# <a name="compiler-error-c2572"></a>Compilerfehler C2572

'class:: Member': Neudefinition des Standardparameters: Parameter Param

Standardparameter können nicht neu definiert werden. Wenn Sie einen anderen Wert für den Parameter, der Standardparameter nicht definiert werden soll benötigen.

Im folgende Beispiel wird die C2572 generiert:

```
// C2572.cpp
// compile with: /c
void f(int i = 1);   // function declaration

// function definition
void f(int i = 1) {}   // C2572

// try the following line instead
// void f(int i) {}
```
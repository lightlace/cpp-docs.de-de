---
title: Compilerfehler C3892 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3892
dev_langs:
- C++
helpviewer_keywords:
- C3892
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b9542f02c2ac72d9c5b4625c2b8fe6f7ba0169b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136087"
---
# <a name="compiler-error-c3892"></a>Compilerfehler C3892

'Var': Sie können nicht für eine Variable, die eine Konstante ist zuweisen

Eine const-Variable kann nicht geändert werden, nachdem sie deklariert und initialisiert wird.

Im folgende Beispiel wird die C3892 generiert:

```
// C3892.cpp
// compile with: /clr
ref struct Y1 {
   static const int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3892
}
```
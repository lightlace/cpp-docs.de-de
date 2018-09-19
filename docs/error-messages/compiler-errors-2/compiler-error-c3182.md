---
title: Compilerfehler C3182 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3182
dev_langs:
- C++
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 722f95b41f9f5ec467af25ccf927631590f90e45
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110216"
---
# <a name="compiler-error-c3182"></a>Compilerfehler C3182

'Klasse': eine using- oder Zugriffsdeklaration für Member ist innerhalb eines verwalteten oder WinRTtype nicht zulässig

Ein [mit](../../cpp/using-declaration.md) Deklaration ist in sämtlichen verwalteten Klassen unzulässig.

Im folgenden Beispiel wird C3182 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3182a.cpp
// compile with: /clr /c
ref struct B {
   void mf(int) {
   }
};

ref struct D : B {
   using B::mf;   // C3182, delete to resolve
   void mf(char) {
   }
};
```

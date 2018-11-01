---
title: Compilerfehler C2846
ms.date: 11/04/2016
f1_keywords:
- C2846
helpviewer_keywords:
- C2846
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
ms.openlocfilehash: 4e1e88e538008cff03349a35e193b7bcd471b950
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427884"
---
# <a name="compiler-error-c2846"></a>Compilerfehler C2846

'Konstruktor': eine Schnittstelle kann keinen Konstruktor besitzen

Eine Visual C++ [Schnittstelle](../../cpp/interface.md) kann keinen Konstruktor besitzen.

Im folgende Beispiel wird die C2846 generiert:

```
// C2846.cpp
// compile with: /c
__interface C {
   C();   // C2846 constructor not allowed in an interface
};
```
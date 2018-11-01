---
title: Compilerfehler C2998
ms.date: 11/04/2016
f1_keywords:
- C2998
helpviewer_keywords:
- C2998
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
ms.openlocfilehash: 16a3319e71d465082120cbc58e3c7c6b916be80f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499761"
---
# <a name="compiler-error-c2998"></a>Compilerfehler C2998

„identifier“: Kann keine Vorlagendefinition sein.

Der Compiler konnte die in der Vorlagendefinition verwendete Syntax nicht verarbeitet.

Im folgenden Beispiel wird C2998 generiert:

```
// C2998.cpp
// compile with: /c
template <class T> int x = 1018; // C2998
```
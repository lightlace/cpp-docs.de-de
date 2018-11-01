---
title: Compilerfehler C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: 5f9b60499fd3c3bd5f06834e3c4f6482031066d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469757"
---
# <a name="compiler-error-c2823"></a>Compilerfehler C2823

> eine Typedef-Vorlage ist nicht zulässig

Vorlagen sind nicht zulässig `typedef` Definitionen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2823 generiert und zeigt eine Möglichkeit, das Problem zu beheben:

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```
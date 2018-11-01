---
title: Compilerfehler C3232
ms.date: 11/04/2016
f1_keywords:
- C3232
helpviewer_keywords:
- C3232
ms.assetid: 3119b3a9-0eff-4a3f-b805-e4d160af9e39
ms.openlocfilehash: b69074e10d6ace4d050fe8684acc8cf183802b2f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427936"
---
# <a name="compiler-error-c3232"></a>Compilerfehler C3232

'Param': Ein generischer Typparameter kann nicht in einem qualifizierten Namen verwendet werden.

Ein generischer Typparameter wurde nicht ordnungsgemäß verwendet.

Im folgenden Beispiel wird C3232 generiert:

```
// C3232.cpp
// compile with: /clr
generic <class T>
ref class C {
   typename T::TYPE t;   // C3232
};
```
---
title: Compilerfehler C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: 61dd280caa3c8c9b28dd77ecab2ed50ab9532d4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501283"
---
# <a name="compiler-error-c3895"></a>Compilerfehler C3895

'Var': Typ-Datenmember darf nicht "volatile" sein

Bestimmte Arten von Datenmembern, z. B. [literal](../../windows/literal-cpp-component-extensions.md) oder [Initonly](../../dotnet/initonly-cpp-cli.md), nicht möglich, [flüchtige](../../cpp/volatile-cpp.md).

Im folgende Beispiel wird die C3895 generiert:

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```
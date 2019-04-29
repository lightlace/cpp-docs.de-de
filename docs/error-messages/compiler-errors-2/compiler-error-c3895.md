---
title: Compilerfehler C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: c4b1cad9ef48f1f16b411aab46e1bb9285d69ff3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385536"
---
# <a name="compiler-error-c3895"></a>Compilerfehler C3895

'Var': Typ-Datenmember darf nicht "volatile" sein

Bestimmte Arten von Datenmembern, z. B. [literal](../../extensions/literal-cpp-component-extensions.md) oder [Initonly](../../dotnet/initonly-cpp-cli.md), nicht möglich, [flüchtige](../../cpp/volatile-cpp.md).

Im folgende Beispiel wird die C3895 generiert:

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```
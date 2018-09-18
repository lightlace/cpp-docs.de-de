---
title: Compilerfehler C3895 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3895
dev_langs:
- C++
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a722ac9091e47db95bcc3e2d81293bf662d0c99
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033289"
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
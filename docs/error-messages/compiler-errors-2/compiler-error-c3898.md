---
title: Compilerfehler C3898 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3898
dev_langs:
- C++
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39fe816c2637df5e5a474718d70b404bbc0c2df6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030027"
---
# <a name="compiler-error-c3898"></a>Compilerfehler C3898

'Var': Typ-Datenmember können nur Member von verwalteten Typen sein

Ein [Initonly](../../dotnet/initonly-cpp-cli.md) Datenmember in einer systemeigenen Klasse deklariert wurde.  Ein `initonly` -Datenmember kann nur in einer CLR-Klasse deklariert werden.

Im folgende Beispiel wird die C3898 generiert:

```
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

Mögliche Lösung:

```
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```
---
title: Compilerfehler C2506 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2506
dev_langs:
- C++
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4967c410dfdce781a4191c9ac848883228ba4d3a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093414"
---
# <a name="compiler-error-c2506"></a>Compilerfehler C2506

'Member': '__declspec(Modifizierer)' kann nicht auf dieses Symbol angewendet werden

Sie können nicht prozessspezifisch oder pro-Appdomain für statische Member einer verwalteten Klasse deklarieren.

Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) .

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2506 generiert.

```
// C2506.cpp
// compile with: /clr /c
ref struct R {
   __declspec(process) static int n;   // C2506
   int o;   // OK
};
```
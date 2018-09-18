---
title: Compilerfehler C2341 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2341
dev_langs:
- C++
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adac1e6f6e5f5d58b6091a389537a42f0e496b31
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020198"
---
# <a name="compiler-error-c2341"></a>Compilerfehler C2341

'Abschnittsname': Segment muss definiert werden, verwenden #pragma Data_seg, Code_seg oder im vorherigen Abschnitt verwenden

Ein [zuordnen](../../cpp/allocate.md) Anweisung verweist auf ein Segment, das noch nicht durch definiert [Code_seg](../../preprocessor/code-seg.md), [Data_seg](../../preprocessor/data-seg.md), oder [Abschnitt](../../preprocessor/section.md) Pragmas.

Im folgende Beispiel wird die C2341 generiert:

```
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

Mögliche Lösung:

```
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```
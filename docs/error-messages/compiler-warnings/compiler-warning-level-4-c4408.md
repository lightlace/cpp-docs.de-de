---
title: Compilerwarnung (Stufe 4) C4408 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4408
dev_langs:
- C++
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7f804f8cbc3dce846783ce4937d7902d760511e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050189"
---
# <a name="compiler-warning-level-4-c4408"></a>Compilerwarnung (Stufe 4) C4408

Anonymousstruct oder Union wurden keine Datenmember deklariert.

Eine anonyme Struktur oder Union muss mindestens einen Datenmember aufweisen.

Im folgenden Beispiel wird C4408 generiert:

```
// C4408.cpp
// compile with: /W4 /LD
static union
{
   // int i;
};
// a named union can have no data members
// } MyUnion;
```
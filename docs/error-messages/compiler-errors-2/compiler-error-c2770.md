---
title: Compilerfehler C2770 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2770
dev_langs:
- C++
helpviewer_keywords:
- C2770
ms.assetid: 100001b5-80b0-4971-8ff6-9023f443c926
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b206f7667855e61bfb3fe5e53cdd82444597162
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027010"
---
# <a name="compiler-error-c2770"></a>Compilerfehler C2770

Ungültige explizite Template_or_generic-Argumente für "Template"

Funktionsvorlagen mit expliziten oder generischen Argumente führte zu unzulässigen Funktionstypen.

Im folgende Beispiel wird die C2770 generiert:

```
// C2770.cpp
#include <stdio.h>
template <class T>
int f(typename T::B*);   // expects type with member B

struct Err {};

int main() {
   f<int>(0);   // C2770 int has no B
   // try the following line instead
   f<OK>(0);
}
```
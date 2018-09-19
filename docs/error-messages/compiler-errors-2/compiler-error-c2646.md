---
title: Compilerfehler C2646 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2646
dev_langs:
- C++
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c94895dfd429723819190ad622e3a7d93fd38a99
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104262"
---
# <a name="compiler-error-c2646"></a>Compilerfehler C2646

Eine anonyme Struktur oder Union im globalen Gültigkeitsbereich oder im Namespacebereich muss als statisch deklariert werden.

Eine anonyme Struktur oder Union verfügt über einen globalen Gültigkeitsbereich oder Namespacebereich, ist jedoch nicht als `static` deklariert.

Im folgenden Beispiel wird C2646 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2646.cpp
// compile with: /c
union { int i; };   // C2646 not static

// OK
static union { int j; };
union U { int i; };
```
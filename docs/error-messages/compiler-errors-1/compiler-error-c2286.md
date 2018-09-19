---
title: Compilerfehler C2286 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2286
dev_langs:
- C++
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e4c3b8a71b29d0d1db5f3bc1eac642122844c22
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089126"
---
# <a name="compiler-error-c2286"></a>Compilerfehler C2286

Zeiger auf Member der Darstellung von 'Bezeichner' ist bereits auf "Vererbung" - Deklaration ignoriert festgelegt

Zwei unterschiedliche Darstellungen der Zeiger auf Member, die für die Klasse vorhanden sein.

Weitere Informationen finden Sie unter [Vererbungsschlüsselwörter](../../cpp/inheritance-keywords.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2286 generiert:

```
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```
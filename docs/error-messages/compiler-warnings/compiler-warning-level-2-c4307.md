---
title: Compilerwarnung (Stufe 2) C4307 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4307
dev_langs:
- C++
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed18c213b35e79aaae98efa5932ac404a8d84bff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079192"
---
# <a name="compiler-warning-level-2-c4307"></a>Compilerwarnung (Stufe 2) C4307

'Operator': Überlauf einer ganzzahligen Konstanten

Der Operator wird in einem Ausdruck verwendet, die eine ganzzahlige Konstante Überlauf für diese zugeordneten Speicherplatzes ergeben. Sie müssen möglicherweise einen größeren Typ für die Konstante verwenden. Ein **signiert Int** enthält einen kleineren Wert als ein `unsigned int` da die **signiert Int** ein Bit verwendet, um das Zeichen darzustellen.

Im folgende Beispiel wird die C4307 generiert:

```
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```
---
title: Compilerwarnung (Stufe 2) C4756 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4756
dev_langs:
- C++
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b80596ede2cc93e64b79b1d5c08e091a880c7771
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086615"
---
# <a name="compiler-warning-level-2-c4756"></a>Compilerwarnung (Stufe 2) C4756

Überlauf bei arithmetischer Auswertung einer Konstanten

Der Compiler hat eine Ausnahme während der Durchführung von Arithmetik während der Kompilierung generiert.

Im folgende Beispiel wird die C4756 generiert:

```
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```
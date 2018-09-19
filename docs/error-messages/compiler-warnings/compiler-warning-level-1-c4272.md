---
title: Compilerwarnung (Stufe 1) C4272 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4272
dev_langs:
- C++
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00e30646c9fe56132da9cf87ba71cb54ae6a3e8f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052958"
---
# <a name="compiler-warning-level-1-c4272"></a>Compilerwarnung (Stufe 1) C4272

'Funktion': ist als __declspec(dllimport) markiert. systemeigene Aufrufkonvention muss angegeben werden, beim Importieren einer Funktion.

Es ist ein Fehler so exportieren Sie eine Funktion mit dem [__clrcall](../../cpp/clrcall.md) Aufrufkonvention und der Compiler gibt diese Warnung, wenn Sie versuchen, eine Funktion importieren `__clrcall`.

Im folgende Beispiel wird die C4272 generiert:

```
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```
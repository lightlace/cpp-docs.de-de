---
title: Compilerwarnung (Stufe 4) C4233 | Microsoft Docs
ms.custom: ''
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4233
dev_langs:
- C++
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a933d41fd8e7cf3b94e458efff72193b8ce5e187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4233"></a>Compilerwarnung (Stufe 4) C4233

> nicht dem Standard entsprechende Erweiterung: '*Schlüsselwort*' Schlüsselwort nur in C++ unterstützt und nicht in C

Der Compiler kompiliert den Quellcode als C und nicht in C++, und Sie verwendet ein Schlüsselwort, das nur in C++ gültig ist. Der Compiler kompiliert die Quelldatei als C, wenn die Erweiterung der Quelldatei .c enthält ist, oder Sie mittels [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md). Fügen Sie z. B. um C4233 in eine Warnung der Stufe 4 zu machen, diese Zeile auf die Quellcodedatei:

```cpp
#pragma warning(4:4233)
```

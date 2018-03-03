---
title: Compilerwarnung (Stufe 4) C4233 | Microsoft Docs
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4233
dev_langs:
- C++
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad27d2ec3d59df147d8bfc26372a2d25397e651f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4233"></a>Compilerwarnung (Stufe 4) C4233

> nicht dem Standard entsprechende Erweiterung: '*Schlüsselwort*' Schlüsselwort nur in C++ unterstützt und nicht in C

Der Compiler kompiliert den Quellcode als C und nicht in C++, und Sie verwendet ein Schlüsselwort, das nur in C++ gültig ist. Der Compiler kompiliert die Quelldatei als C, wenn die Erweiterung der Quelldatei .c enthält ist, oder Sie mittels [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md). Fügen Sie z. B. um C4233 in eine Warnung der Stufe 4 zu machen, diese Zeile auf die Quellcodedatei:

```cpp
#pragma warning(4:4233)
```

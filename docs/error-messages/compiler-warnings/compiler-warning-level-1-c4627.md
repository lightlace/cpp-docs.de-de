---
title: Compilerwarnung (Stufe 1) C4627 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fef8d0ab55205d2377fc52049c40a1c50151b93e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024176"
---
# <a name="compiler-warning-level-1-c4627"></a>Compilerwarnung (Stufe 1) C4627

> "*Header_file*": beim Suchen nach Verwendung des vorkompilierten Headers übersprungen

Wenn es sich bei die aktuellen Quelldatei wurde die ["/ Yu" \(Verwendung des vorkompilierten Headerdatei)](../../build/reference/yu-use-precompiled-header-file.md) Optionssatz, und klicken Sie dann der Compiler ignoriert alles, was in der Datei, bevor der vorkompilierte Header enthalten ist. Warnung **C4627** wird in Visual Studio 2015 und früheren Versionen generiert, wenn *Header_file* enthalten ist, bevor Sie die vorkompilierte Headerdatei, und wenn der vorkompilierte Header auch keine umfasst*Header_file*.

## <a name="example"></a>Beispiel

In diesem Beispiel wird veranschaulicht, wie der Fehler kann auftreten, und zeigt, wie Sie diesen Fehler beheben:

```cpp
// c4627.cpp
#include <iostream>       // C4627 - iostream not included by pch.h
#include "pch.h"          // precompiled header file that does not include iostream
// #include <iostream>    // To fix, move the iostream header include here from above
int main()
{
    std::cout << "std::cout is defined!\n";
}
```

## <a name="see-also"></a>Siehe auch

[Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)

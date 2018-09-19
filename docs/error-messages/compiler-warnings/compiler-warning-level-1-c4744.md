---
title: Compilerwarnung (Stufe 1) C4744 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1754977486327e06fb56a786be523c1b2fb7b917
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068974"
---
# <a name="compiler-warning-level-1-c4744"></a>Compilerwarnung (Stufe 1) C4744

'Var' hat einen anderen Typ in "Datei1" und "Datei2": "Typ1" und "Typ2"

Eine externe Variable verwiesen wird, oder in zwei Dateien definiert verfügt über verschiedene Arten in diesen Dateien.  Um zu beheben, stellen Sie den Typdefinitionen identisch oder ändern Sie Variablennamen in eine der Dateien zu.

C4744 wird nur ausgegeben, wenn Dateien mit "/ GL" kompiliert werden  Weitere Informationen finden Sie unter [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
>  C4744 rührt in der Regel in C (nicht in C++)-Dateien in C++ ein Variablennamen mit den Typinformationen ergänzt wird.  Wenn Sie das Beispiel (siehe unten) als C++ kompiliert wird, erhalten Sie die Linker-Fehler LNK2019.

## <a name="example"></a>Beispiel

Dieses Beispiel enthält die erste Definition.

```
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4744 generiert.

```
// C4744b.c
// compile with: C4744.c /GL /W1
// C4744 expected
#include <stdio.h>

extern unsigned global;

main()
{
    printf_s("%d\n", global);
}
```
---
title: Compilerwarnung (Stufe 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: f6954ae7966edf200249bb5d10f0dfb011bcef22
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051550"
---
# <a name="compiler-warning-level-1-c4744"></a>Compilerwarnung (Stufe 1) C4744

"var" weist einen anderen Typ in "file1" und "file2" auf: "Typ1" und "Typ2".

Eine externe Variable, auf die in zwei Dateien verwiesen oder diese definiert wird, weist in diesen Dateien unterschiedliche Typen auf  Legen Sie zum Auflösen entweder die Typdefinitionen identisch, oder ändern Sie den Variablennamen in einer der Dateien.

C4744 wird nur ausgegeben, wenn Dateien mit/GL. kompiliert werden.  Weitere Informationen finden Sie unter [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
>  C4744 tritt normalerweise in C- C++Dateien (nicht) auf C++ , da in einem Variablennamen mit Typinformationen versehen ist.  Wenn das Beispiel (unten) als C++kompiliert wird, erhalten Sie den Linker-Fehler LNK2019.

## <a name="example"></a>Beispiel

Dieses Beispiel enthält die erste Definition.

```c
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4744 generiert.

```c
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
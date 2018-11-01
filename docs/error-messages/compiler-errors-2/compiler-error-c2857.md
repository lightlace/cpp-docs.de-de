---
title: Compilerfehler C2857
ms.date: 09/13/2018
f1_keywords:
- C2857
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
ms.openlocfilehash: 10c0ea3b54ded29bf80f83713cea33428dca6ca0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432150"
---
# <a name="compiler-error-c2857"></a>Compilerfehler C2857

> ' #include "mit der" / Yc "angegebene Anweisung*Filename* Befehlszeilenoption wurde in der Quelldatei nicht gefunden

Die ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md) Option gibt den Namen einer Include-Datei, die nicht in der Quelldatei kompiliert wird.

## <a name="remarks"></a>Hinweise

Bei Verwendung der **"/ Yc"**<em>Dateiname</em> muss die Option auf die Quelldatei, erstellen Sie eine Datei, die Datei als source vorkompilierter Headerdateien (PCH) enthalten die *Filename* Headerdatei. Jede Datei, die von der bis zur und einschließlich der angegebenen Quelldatei enthaltenen *Filename*, befindet sich auf die PCH-Datei. In anderen Quelldateien kompiliert werden, mithilfe der **"/ Yu"**<em>Dateiname</em> eine Einbeziehung der Möglichkeit, verwenden den PCH neu Datei *Filename* muss die erste nicht kommentierten Zeile in der Datei. Der Compiler ignoriert alle Elemente in der Quelldatei, bevor Sie diese einschließen.

Dieser Fehler kann verursacht werden, indem ein `#include "filename"` Anweisung in einem Block von für die bedingte Kompilierung, die nicht in der PCH-Quelldatei kompiliert wird.

## <a name="example"></a>Beispiel

Klicken Sie in der typischen Verwendung einer Quelldatei im Projekt wird festgelegt, wie die PCH-Quelldatei, und eine Headerdatei wird als die PCH-Headerdatei verwendet. Eine typische PCH-Headerdatei enthält alle den Bibliothek-Header, die in Ihrem Projekt verwendet, aber nicht für lokale Header, die noch in Entwicklung sind. In diesem Beispiel heißt die PCH-Headerdatei *my_pch.h*.

```cpp
// my_pch.h
#pragma once
#include <stdio.h>
```

Die PCH-Quelldatei kompiliert wird, mithilfe der **"/ Yc"**<em>my_pch.h</em> Option. Wenn der Compiler eine einschließen dieser PCH-Headerdatei nicht findet, wird es C2857 generiert:

```cpp
// my_pch.cpp
// Compile by using: cl /EHsc /W4 /Yumy_pch.h /c my_pch.cpp

#if 0
#include "my_pch.h"  // C2857; remove conditional directives to fix
#endif
```

Um diese PCH-Datei zu verwenden, müssen mithilfe von Quelldateien kompiliert werden die **"/ Yu"**<em>my_pch.h</em> Option. Die PCH-Headerdatei muss in zuerst in Quelldateien verwendet werden, die den PCH neu zu verwenden:

```cpp
// C2857.cpp
// Compile my_pch.cpp first, then
// compile by using: cl /EHsc /W4 /Yumy_pch.h my_project.cpp my_pch.obj
// Include the pch header before any other non-comment line
#include "my_pch.h"

int main()
{
    puts("Using a precompiled header file.\n");
}
```
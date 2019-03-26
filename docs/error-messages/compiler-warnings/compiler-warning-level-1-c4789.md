---
title: Compilerwarnung (Stufe 1) C4789
ms.date: 03/25/2019
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: 36a5032098c5caabb1b050833e487fd58679a782
ms.sourcegitcommit: 6e4dd21759caaed262a7255735cf8d6e8fb9f4d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58476851"
---
# <a name="compiler-warning-level-1-c4789"></a>Compilerwarnung (Stufe 1) C4789

> Puffer "*Bezeichner*' Größe *N* Bytes werden überlaufen; *M* Bytes werden ab Offset geschrieben *L*

## <a name="remarks"></a>Hinweise

**C4789** Pufferüberläufe warnt, wenn bestimmte Funktionen der C-Laufzeit (CRT) verwendet werden. Sie können auch unterschiedliche Größen melden, wenn Parameter übergeben oder Zuweisungen erfolgen. Die Warnung ist möglich, wenn die Datengrößen zur Kompilierzeit bekannt sind. Diese Warnung gilt für Situationen, in denen die typische Datengrößen-Konflikterkennung umgangen wird.

**C4789** warnt, wenn Daten in einen Datenblock, der zu klein zum Zeitpunkt der Kompilierung bekannt wurde kopiert.

Die Warnung tritt auf, wenn die Kopie mit das systeminterne Formular einer der folgenden CRT-Funktionen verwendet:

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

Die Warnung wird auch angezeigt, wenn Sie Parameter für einen größeren Datentyp umgewandelt, und stellen Sie dann eine kopierzuweisung über einen Lvalue-Verweis.

Visual C++ möglicherweise diese Warnung für einen Codepfad generieren, die nicht ausgeführt wird. Sie können die Warnung mithilfe von `#pragma` vorübergehend deaktivieren, wie im folgenden Beispiel gezeigt:

```cpp
#pragma warning( push )
#pragma warning( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma warning( pop )
```

Diese Sprache wird verhindert, dass Visual C++ die Warnung für diese bestimmten Codeblock generiert. `#pragma warning(push)` behält den vorhandenen Zustand bei, bevor dieser von `#pragma warning(disable: 4789)` geändert wird. `#pragma warning(pop)` stellt den gepushten Zustand wieder her und entfernt die Auswirkungen der `#pragma warning(disable:4789)`. Weitere Informationen zu C++-präprozessoranweisung `#pragma`, finden Sie unter [Warnung](../../preprocessor/warning.md) und [Pragma-Direktiven und das __Pragma-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4789 generiert.

```cpp
// C4789.cpp
// compile with: /Oi /W1 /c
#include <string.h>
#include <stdio.h>

int main()
{
    char a[20];
    strcpy(a, "0000000000000000000000000\n");   // C4789

    char buf2[20];
    memset(buf2, 'a', 21);   // C4789

    char c;
    wchar_t w = 0;
    memcpy(&c, &w, sizeof(wchar_t));
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird außerdem C4789 generiert.

```cpp
// C4789b.cpp
// compile with: /W1 /O2 /c
// processor: x86
short G;

void main()
{
   int * p = (int *)&G;
   *p = 3;   // C4789 - writes an int through a pointer to short
}
```
---
title: Compilerwarnung (Stufe 1) C4789
ms.date: 03/25/2019
f1_keywords:
- C4789
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
ms.openlocfilehash: 36278615631d017db1d1c2fc4eecf8c1612892de
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518399"
---
# <a name="compiler-warning-level-1-c4789"></a>Compilerwarnung (Stufe 1) C4789

> der Puffer "*Bezeichner*" der Größe von *N* Bytes wird überlaufen. *M* Bytes werden ab Offset *L* geschrieben.

## <a name="remarks"></a>Hinweise

**C4789** warnt vor Pufferüberläufen, wenn bestimmte CRT-Funktionen (C Run-Time) verwendet werden. Sie kann auch Größen Konflikte melden, wenn Parameter weitergegeben werden oder Zuweisungen vorgenommen werden. Die Warnung ist möglich, wenn die Datengrößen zum Zeitpunkt der Kompilierung bekannt sind. Diese Warnung gilt für Situationen, in denen die typische Datengrößen-Konflikterkennung umgangen wird.

**C4789** warnt, wenn Daten in einen Datenblock kopiert werden, der bekanntermaßen zum Zeitpunkt der Kompilierung zu klein ist.

Die Warnung tritt auf, wenn die Kopie das intrinsische Formular einer dieser CRT-Funktionen verwendet:

- [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)

- [memset](../../c-runtime-library/reference/memset-wmemset.md)

- [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)

Die Warnung wird auch angezeigt, wenn Sie einen Parameter in einen größeren Datentyp umwandeln und dann eine Kopier Zuweisung aus einem Lvalue-Verweis erstellen.

Visual C++ generiert diese Warnung möglicherweise für einen Codepfad, der nie ausgeführt wird. Sie können die Warnung mithilfe von `#pragma` vorübergehend deaktivieren, wie im folgenden Beispiel gezeigt:

```cpp
#pragma warning( push )
#pragma warning( disable : 4789 )
// unused code that generates compiler warning C4789`
#pragma warning( pop )
```

Diese Ausdrucksweise verhindert C++ , dass die Warnung für diesen spezifischen Codeblock von Visual erzeugt wird. `#pragma warning(push)` behält den vorhandenen Zustand bei, bevor dieser von `#pragma warning(disable: 4789)` geändert wird. `#pragma warning(pop)` stellt den gepushten Zustand wieder her und entfernt die Auswirkungen der `#pragma warning(disable:4789)`. Weitere Informationen zur C++ Präprozessordirektive `#pragma`finden Sie unter [Warning](../../preprocessor/warning.md) -und [pragma-Direktiven und das __Pragma-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

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

int main()
{
   int * p = (int *)&G;
   *p = 3;   // C4789 - writes an int through a pointer to short
}
```

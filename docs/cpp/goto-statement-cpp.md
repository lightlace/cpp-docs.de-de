---
title: goto-Anweisung (C++)
ms.date: 11/04/2016
f1_keywords:
- goto_cpp
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
ms.openlocfilehash: aac308905a01a52a4ce5ee0fa3be03f2f33ac1cd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153696"
---
# <a name="goto-statement-c"></a>goto-Anweisung (C++)

Die **Goto** -Anweisung überträgt die Steuerung bedingungslos an die Anweisung anhand des angegebenen Bezeichners.

## <a name="syntax"></a>Syntax

```
goto identifier;
```

## <a name="remarks"></a>Hinweise

Die bezeichnete Anweisung, die durch `identifier` angegeben wird, muss sich in der aktuellen Funktion befinden. Alle `identifier`-Namen sind Member eines internen Namespace und beeinträchtigen daher andere Bezeichner nicht.

Eine anweisungsbezeichnung ist nur sinnvoll ein **"GoTo"** -Anweisung; andernfalls werden anweisungsbezeichnungen ignoriert. Bezeichnungen können nicht erneut deklariert werden.

Ein **Goto** Anweisung ist nicht zulässig, um das Steuerelement an einen Speicherort übertragen, die über die Initialisierung von allen Variablen überspringt, die im Bereich an diesem Speicherort befindet. Im folgende Beispiel löst C2362 aus:

```cpp
int goto_fn(bool b)
{
    if (!b)
    {
        goto exit;  // C2362
    }
    else
    { /*...*/ }

    int error_code = 42;

exit:
    return error_code;
}
```

Programmierung empfiehlt es sich beim der **Break**, **weiterhin**, und **zurückgeben** -Anweisungen anstelle von der **Goto** Anweisung immer möglich ist. Allerdings da die **Break** Anweisung, die nur eine Ebene einer Schleife beendet wird, müssen Sie möglicherweise mit einer **"GoTo"** Anweisung, um eine tief geschachtelte Schleife zu beenden.

Weitere Informationen über Bezeichnungen und der **Goto** -Anweisung finden Sie unter [Anweisungen mit Bezeichnung](../cpp/labeled-statements.md).

## <a name="example"></a>Beispiel

In diesem Beispiel eine **Goto** -Anweisung überträgt die Steuerung an den Punkt mit der Bezeichnung `stop` beim `i` gleich 3.

```cpp
// goto_statement.cpp
#include <stdio.h>
int main()
{
    int i, j;

    for ( i = 0; i < 10; i++ )
    {
        printf_s( "Outer loop executing. i = %d\n", i );
        for ( j = 0; j < 2; j++ )
        {
            printf_s( " Inner loop executing. j = %d\n", j );
            if ( i == 3 )
                goto stop;
        }
    }

    // This message does not print:
    printf_s( "Loop exited. i = %d\n", i );

    stop:
    printf_s( "Jumped to stop. i = %d\n", i );
}
```

```Output
Outer loop executing. i = 0
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 1
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 2
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 3
Inner loop executing. j = 0
Jumped to stop. i = 3
```

## <a name="see-also"></a>Siehe auch

[Sprunganweisungen](../cpp/jump-statements-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)

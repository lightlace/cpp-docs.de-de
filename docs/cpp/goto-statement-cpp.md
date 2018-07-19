---
title: Goto-Anweisung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- goto_cpp
dev_langs:
- C++
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7676f38e52734fa2f0ce8ecbc9b268be1939f6dc
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953394"
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
 [Sprunganweisungen](../cpp/jump-statements-cpp.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
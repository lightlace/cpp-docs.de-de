---
title: Goto-Anweisung (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- goto_cpp
dev_langs:
- C++
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3bdad97f36902762f34816a04a4fc0c5c0c16856
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="goto-statement-c"></a>goto-Anweisung (C++)
Die `goto`-Anweisung überträgt ohne Bedingungen das Steuerelement an die Anweisung, die vom festgelegten Bezeichner angegeben wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
goto identifier;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die bezeichnete Anweisung, die durch `identifier` angegeben wird, muss sich in der aktuellen Funktion befinden. Alle `identifier`-Namen sind Member eines internen Namespace und beeinträchtigen daher andere Bezeichner nicht.  
  
 Eine Anweisungsbezeichnung ist nur im Fall einer `goto`-Anweisung sinnvoll; andernfalls werden Anweisungsbezeichnungen ignoriert. Bezeichnungen können nicht erneut deklariert werden.  
  
 Zu Programmierzwecken wird empfohlen, wann immer möglich die Anweisungen `break`, `continue` und `return` anstelle der `goto`-Anweisung zu verwenden. Da die `break`-Anweisung nur eine Ebene einer Schleife beendet, müssen Sie möglicherweise eine `goto`-Anweisung verwenden, um eine tief geschachtelte Schleife zu beenden.  
  
 Weitere Informationen über Bezeichnungen und der `goto` -Anweisung finden Sie unter [Anweisungen mit Bezeichnung](../cpp/labeled-statements.md) und [Verwenden von Bezeichnungen mit der Goto-Anweisung](http://msdn.microsoft.com/en-us/6cd7c31a-9822-4241-8566-f79f51be48fe).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel übergibt eine `goto`-Anweisung das Steuerelement an den Punkt mit der Bezeichnung `stop`, wenn `i` gleich 3 ist.  
  
```  
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

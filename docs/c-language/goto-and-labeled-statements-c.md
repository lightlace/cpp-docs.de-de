---
title: goto und bezeichnete Anweisungen (C) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- labeled statement
- statements, labeled
- goto keyword [C]
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf56a409f9a76cdf401323d1425ee28fc6cf286b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386413"
---
# <a name="goto-and-labeled-statements-c"></a>goto und bezeichnete Anweisungen (C)
Die Anweisung `goto` übertragt die Steuerung an eine Bezeichnung. Die angegebene Bezeichnung muss sich in derselben Funktion befinden und kann nur vor einer Anweisung in derselben Funktion stehen.  
  
## <a name="syntax"></a>Syntax  
 *Anweisung*:  
 *labeled-statement*  
  
 *jump-statement*  
  
 *jump-statement*:  
 **goto**  *identifier*  **;**  
  
 *labeled-statement*:  
 *identifier*  **:**  *statement*  
  
 Eine Anweisungsmarke ist nur für eine `goto`-Anweisung sinnvoll. In jedem anderen Kontext wird eine bezeichnete Anweisung ohne Berücksichtigung der Bezeichnung ausgeführt.  
  
 Ein *jump-statement* muss sich in der gleichen Funktion befinden und kann nur vor einer Anweisung in der gleichen Funktion stehen. Der Satz der *Bezeichnernamen*, die auf `goto` folgen, verfügt über einen eigenen Namespace, sodass die Namen nicht mit anderen Bezeichnern in Konflikt treten. Bezeichnungen können nicht erneut deklariert werden. Weitere Informationen finden Sie unter [Namespaces](../c-language/name-spaces.md).  
  
 Zur Programmierung empfiehlt es sich, die **break**-, **continue**- und `return`-Anweisung der `goto`-Anweisung vorzuziehen, wann immer dies möglich ist. Da die **break**-Anweisung nur eine Ebene der Schleife beendet, ist möglicherweise eine `goto`-Anweisung erforderlich, um die Schleife aus einer tief verschachtelten Schleife heraus zu beenden.  
  
 In diesem Beispiel wird die `goto`-Anweisung veranschaulicht.  
  
```  
// goto.c  
#include <stdio.h>  
  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 3; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 5 )  
                goto stop;  
        }  
    }  
  
    /* This message does not print: */  
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop: printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
 In diesem Beispiel übergibt eine `goto`-Anweisung die Steuerung an den Punkt mit der Bezeichnung `stop`, wenn `i` gleich 5 ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../c-language/statements-c.md)
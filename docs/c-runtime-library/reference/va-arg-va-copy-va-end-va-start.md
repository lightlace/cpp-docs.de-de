---
title: va_arg, va_copy, va_end, va_start | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- va_arg
- va_end
- va_copy
- va_start
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- va_arg
- va_start
- va_list
- va_alist
- va_dcl
- va_copy
- va_end
dev_langs:
- C++
helpviewer_keywords:
- variable argument lists, accessing
- va_start macro
- va_arg macro
- va_end macro
- arguments [C++], argument lists
- va_list macro
- va_dcl macro
- va_alist macro
- va_copy macro
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 1b8ddbc48b00a037ae20632f4cd396e8e0ff2722
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="vaarg-vacopy-vaend-vastart"></a>va_arg, va_copy, va_end, va_start
Greift auf Variablenargumentelisten zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
type va_arg(  
   va_list arg_ptr,  
   type   
);
void va_copy(  
   va_list dest,  
   va_list src  
); // (ISO C99 and later)  
void va_end(  
   va_list arg_ptr   
);  
void va_start(  
   va_list arg_ptr,  
   prev_param   
); // (ANSI C89 and later)  
void va_start(  
   arg_ptr   
);  // (deprecated Pre-ANSI C89 standardization version)  
```  
  
#### <a name="parameters"></a>Parameter  
 `type`  
 Typ des abzurufenden Arguments.  
  
 `arg_ptr`  
 Zeiger auf die Liste der Argumente.  
  
 `dest`  
 Zeiger auf die Liste von Argumenten, die von `src` initialisiert werden  
  
 `src`  
 Zeiger auf die initialisierte Liste von Argumenten, die von `dest` kopiert werden.  
  
 `prev_param`  
 Parameter, der dem ersten optionalen Argument vorausgeht.  
  
## <a name="return-value"></a>Rückgabewert  
 `va_arg` gibt das aktuelle Argument zurück. `va_copy`, `va_start` und `va_end` geben keine Werte zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die Makros `va_arg`, `va_copy`, `va_end` und `va_start` ermöglichen auf portierbare Weise, auf die Argumente für eine Funktion zuzugreifen, wenn die Funktion eine variable Anzahl von Argumenten akzeptiert. Es gibt zwei Versionen der Makros: Die in STDARG.H definierten Makros, die mit dem ISO-Standard C99 konform sind, und die in VARARGS.H definierten Makros, die zwar als veraltet markiert sind, aber beibehalten werden, da sie für Code abwärts kompatibel sind, der vor dem ANSI-Standard C89 geschrieben wurde.  
  
 Diese Makros setzen voraus, dass die Funktion eine feste Anzahl von erforderlichen Argumenten akzeptiert, gefolgt von einer variablen Anzahl von optionalen Argumenten. Die erforderlichen Argumente werden als gewöhnliche Parameter für die Funktion deklariert und können über die Parameternamen aufgerufen werden. Die optionalen Argumente werden über Makros in STDARG.H (oder in VARARGS.H für Code, der vor dem ANSI-Standard C89 geschrieben wurde) aufgerufen, wodurch ein Zeiger auf das erste optionale Argument in der Argumentliste festgelegt wird und zurückgesetzt wird, nachdem das Verarbeiten der Argumente abgeschlossen ist.  
  
 Die in STDARG.H definierten C-Standardmakros werden wie folgt verwendet:  
  
-   `va_start` legt `arg_ptr` auf das erste optionale Argument in der Liste der Argumente fest, die an die Funktion übergeben wird. Das Argument `arg_ptr` muss über den Typ `va_list` verfügen. Das Argument `prev_param` ist der Name des erforderlichen Parameters, der dem ersten optionalen Argument in der Argumentliste direkt vorausgeht. Wenn `prev_param` mit der Registerspeicherklasse deklariert wird, ist das Verhalten des Makros undefiniert. `va_start` muss verwendet werden, bevor `va_arg` zum ersten Mal verwendet wird.  
  
-   `va_arg` ruft einen `type`-Wert vom Speicherort ab, der von `arg_ptr` angegeben wird, und inkrementiert `arg_ptr`, um auf das folgende Argument in der Liste zu verweisen, indem mithilfe der Größe von `type` bestimmt wird, wo das folgende Argument beginnt. `va_arg` kann in der Funktion beliebig oft verwendet werden, um Argumente aus der Liste abzurufen.  
  
-   `va_copy` erstellt eine Kopie von einer Argumentliste im aktuellen Zustand. Der `src`-Parameter muss bereits mit `va_start` initialisiert sein. Er kann mithilfe von `va_arg`-Aufrufen aktualisiert worden sein, doch darf er nicht mit `va_end` zurückgesetzt worden sein. Das folgende Argument, das von `va_arg` aus `dest` abgerufen wird, entspricht dem folgenden Argument, das von `src` abgerufen wird.  
  
-   Nach dem Abruf aller Argumente setzt `va_end` den Zeiger auf **NULL** zurück. `va_end` muss in jeder mit `va_start` oder `va_copy` initialisierten Argumentliste aufgerufen werden, bevor die Funktion Daten zurückgibt.  
  
> [!NOTE]
>  Die in VARARGS.H definierten Makros sind als veraltet markiert und werden nur beibehalten, weil sie für Code abwärts kompatibel sind, der vor dem ANSI-Standard C89 geschrieben wurde. Verwenden Sie in allen anderen Fällen die Makros in STDARGS.H.  
  
 Da sie mithilfe von [/clr (CLR-Kompilierung, Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden, generieren Programme, die diese Makros verwenden, möglicherweise unerwartete Ergebnisse. Dies liegt an den Unterschieden zwischen nativen und CLR-Typsystemen (Common Language Runtime). Beachten Sie dieses Programm:  
  
```  
#include <stdio.h>  
#include <stdarg.h>  
  
void testit (int i, ...)  
{  
    va_list argptr;  
    va_start(argptr, i);  
  
    if (i == 0)  
    {  
        int n = va_arg(argptr, int);  
        printf("%d\n", n);  
    }  
    else  
    {  
        char *s = va_arg(argptr, char*);  
        printf("%s\n", s);  
    }  

    va_end(argptr);  
}  
  
int main()  
{  
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int  
    testit(1, NULL);       // 2nd problem: NULL is not a char*  
}  
```  
  
 Berücksichtigen Sie, dass `testit` als zweiten Parameter entweder `int` oder `char*` voraussetzt. Die übergebenen Argumente sind 0xffffffff ( `unsigned int`, aber nicht `int`) und `NULL` (tatsächlich ein `int`, aber kein `char*`). Wenn das Programm für nativen Code kompiliert wird, erzeugt es diese Ausgabe:  
  
```Output  
-1  
  
(null)  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<stdio.h> und \<stdarg.h>  
  
 **Veralteter Header:** \<varargs.h>  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_va.c  
/* Compile with: cl /W3 /Tc crt_va.c  
 * The program below illustrates passing a variable  
 * number of arguments using the following macros:  
 *      va_start            va_arg              va_copy  
 *      va_end              va_list  
 */  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <math.h>  
  
double deviation(int first, ...);  
  
int main( void )  
{  
    /* Call with 3 integers (-1 is used as terminator). */  
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));  
  
    /* Call with 4 integers. */  
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));  
  
    /* Call with just -1 terminator. */  
    printf("Deviation is: %f\n", deviation(-1));  
}  
  
/* Returns the standard deviation of a variable list of integers. */  
double deviation(int first, ...)  
{  
    int count = 0, i = first;  
    double mean = 0.0, sum = 0.0;  
    va_list marker;  
    va_list copy;  
  
    va_start(marker, first);     /* Initialize variable arguments. */  
    va_copy(copy, marker);       /* Copy list for the second pass */  
    while (i != -1)  
    {  
        sum += i;  
        count++;  
        i = va_arg(marker, int);  
    }  
    va_end(marker);              /* Reset variable argument list. */  
    mean = sum ? (sum / count) : 0.0;  
  
    i = first;                  /* reset to calculate deviation */  
    sum = 0.0;  
    while (i != -1)  
    {  
        sum += (i - mean)*(i - mean);  
        i = va_arg(copy, int);  
    }  
    va_end(copy);               /* Reset copy of argument list. */  
    return count ? sqrt(sum / count) : 0.0;  
}  
  
```  
  
## <a name="output"></a>Ausgabe  
  
```Output  
Deviation is: 0.816497  
Deviation is: 2.236068  
Deviation is: 0.000000  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Argumentzugriff](../../c-runtime-library/argument-access.md)   
 [vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)

---
title: _matherr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _matherr
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
- _matherr
- matherr
dev_langs:
- C++
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: bd2ab4ac1c6772a06a2da6ac15f7f4b29f83c120
ms.lasthandoff: 02/24/2017

---
# <a name="matherr"></a>_matherr
Behandlung von Mathematikfehlern  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *except*  
 Ein Zeiger auf die Struktur, die Fehlerinformationen enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 _**matherr** gibt 0 zurück, um auf einen Fehler oder einen Wert ungleich null hinzuweisen, um einen Erfolg anzuzeigen. Wenn \_**matherr** 0 zurückgibt, kann eine Fehlermeldung angezeigt werden, und `errno` wird auf einen ordnungsgemäßen Fehlerwert festgelegt. Wenn \_**matherr** einen Wert ungleich null zurückgibt, wird eine Fehlermeldung angezeigt, und `errno` bleibt unverändert.  
  
 Weitere Informationen zu Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die _**matherr**-Funktion verarbeitet Fehler, die von Gleitkommafunktionen der mathematischen Bibliothek generiert werden. Diese Funktionen rufen \_**matherr** auf, wenn ein Fehler erkannt wird.  
  
 Für spezielle Fehlerbehandlungen können Sie eine andere Definition von _**matherr** bereitstellen. Wenn Sie die dynamisch verknüpfte Version der C-Laufzeitbibliothek (Msvcr90.dll) verwenden, können Sie die Standardroutine \_**matherr** in einem ausführbaren Client durch eine benutzerdefinierte Version ersetzen. Sie können jedoch nicht die Standardroutine `_matherr` in einem DLL-Client von Msvcr90.dll ersetzen.  
  
 Wenn ein Fehler in einer mathematischen Routine erkannt wird, wird _**matherr** mit einem Zeiger auf eine **_exception**-Typstruktur (in Math.h definiert) als Argument aufgerufen. Die Struktur **_exception** enthält die folgenden Elemente:  
  
 **int type**  
 Ausnahmetyp.  
  
 **char \*name**  
 Name der Funktion, in der der Fehler aufgetreten ist.  
  
 **double arg1**, **arg2**  
 Erste und zweite (sofern vorhanden) Argumente der Funktion.  
  
 **double retval**  
 Wert, der von der Funktion zurückgegeben wird.  
  
 Der **type** gibt den Typ des mathematischen Fehlers an. Dieser ist einer der folgenden Werte, die in Math.h definiert sind.  
  
 `_DOMAIN`  
 Argumentdomänenfehler  
  
 `_SING`  
 Einzigartigkeit des Arguments  
  
 `_OVERFLOW`  
 Überlaufbereichsfehler  
  
 `_PLOSS`  
 Teilweiser Verlust von Bedeutung  
  
 `_TLOSS`  
 Vollständiger Verlust von Bedeutung  
  
 `_UNDERFLOW`  
 Das Ergebnis ist zu klein, um dargestellt werden zu können. (Diese Bedingung wird derzeit nicht unterstützt.)  
  
 Der Strukturmember **name** ist ein Zeiger auf eine mit NULL endende Zeichenfolge mit dem Namen der Funktion, die den Fehler verursacht hat. Die Strukturmember **arg1** und **arg2** geben die Werte an, die den Fehler verursacht haben. (Wenn nur ein Argument angegeben ist, befindet es sich in **arg1**.)  
  
 Der Standardrückgabewert für den angegebenen Fehler ist **retval**. Wenn Sie den Rückgabewert ändern, muss dieser angeben, ob ein Fehler wirklich passiert ist.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_matherr`|\<math.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_matherr.c  
/* illustrates writing an error routine for math   
 * functions. The error function must be:  
 *      _matherr  
 */  
  
#include <math.h>  
#include <string.h>  
#include <stdio.h>  
  
int main()  
{  
    /* Do several math operations that cause errors. The _matherr  
     * routine handles _DOMAIN errors, but lets the system handle  
     * other errors normally.  
     */  
    printf( "log( -2.0 ) = %e\n", log( -2.0 ) );  
    printf( "log10( -5.0 ) = %e\n", log10( -5.0 ) );  
    printf( "log( 0.0 ) = %e\n", log( 0.0 ) );  
}  
  
/* Handle several math errors caused by passing a negative argument  
 * to log or log10 (_DOMAIN errors). When this happens, _matherr  
 * returns the natural or base-10 logarithm of the absolute value  
 * of the argument and suppresses the usual error message.  
 */  
int _matherr( struct _exception *except )  
{  
    /* Handle _DOMAIN errors for log or log10. */  
    if( except->type == _DOMAIN )  
    {  
        if( strcmp( except->name, "log" ) == 0 )  
        {  
            except->retval = log( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
        else if( strcmp( except->name, "log10" ) == 0 )  
        {  
            except->retval = log10( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
    }  
    printf( "Normal: " );  
    return 0;    /* Else use the default actions */  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   

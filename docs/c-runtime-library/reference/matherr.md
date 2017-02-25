---
title: "_matherr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_matherr"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_matherr"
  - "matherr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_matherr-Funktion"
  - "matherr-Funktion"
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _matherr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Behandelt mathematische Fehler.  
  
## Syntax  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### Parameter  
 *Ausnahme*  
 Zeiger zur Struktur, die Fehlerinformationen enthält.  
  
## Rückgabewert  
 \_**matherr** gibt 0 zurück, um einen Fehler oder einen Wert ungleich 0 \(null\) angeben, um Erfolg anzugeben.  Wenn \_**matherr** 0 zurückgibt, kann eine Fehlermeldung angezeigt und `errno` wird auf einen geeigneten Fehlerwert festgelegt.  Wenn \_**matherr** einen Wert ungleich 0 \(null\) zurückgibt, wird keine Fehlermeldung angezeigt und `errno` bleibt unverändert.  
  
 Weitere Informationen über Rückgabecodes, finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die **matherr**\-Funktionsprozessfehler \_generiert durch die Gleitkommafunktionen der mathematischen Bibliothek.  Diese Funktionen rufen \_**matherr** auf, wenn ein Fehler erkannt wird.  
  
 Bei speziellen Fehlerbehandlung können Sie eine andere Definition von \_**matherr** bereitstellen.  Wenn Sie die dynamisch verknüpfte Version der C\-Laufzeitbibliothek \(Msvcr90.dll\), können Sie die Standardeinstellung \_**matherr** Routine in einer ausführbaren Clients von einer benutzerdefinierten Version ersetzen.  Sie können die standardmäßige `_matherr` Routine in einem DLL\-Client von Msvcr90.dll nicht ersetzen.  
  
 Wenn ein Fehler in einer mathematischen Routine auftritt, wird \_**matherr** mit einem Zeiger auf eine **\_exception**\-Typstruktur \(definiert in Math.h\) als Argument aufgerufen.  Die **\_exception**\-Struktur enthält die folgenden Elemente.  
  
 **int type**  
 Ausnahmetyp.  
  
 **char \*name**  
 Name der Funktion, in der Fehler aufgetreten ist.  
  
 **double arg1**, **arg2**  
 Das erste und zweite \(wenn vorhanden\) Argumente der Funktion.  
  
 **double retval**  
 Durch die Funktion zurückgegeben werden, Wert.  
  
 **Typ** gibt den Typ von mathematischen Fehlers an.  Es wurde einer der folgenden Werte, die in Math.h.  
  
 `_DOMAIN`  
 Argumentbereichsfehler.  
  
 `_SING`  
 Argumenteigenheit.  
  
 `_OVERFLOW`  
 Bereichsüberlauf\-Fehler.  
  
 `_PLOSS`  
 Teilverlust Signifikanz an.  
  
 `_TLOSS`  
 Gesamter Verlust des Schritts.  
  
 `_UNDERFLOW`  
 Das Ergebnis ist zu klein dargestellt. \(Diese Bedingung wird derzeit nicht unterstützt.\)  
  
 Der Strukturmember **name** ist ein Zeiger auf eine auf NULL endende Zeichenfolge, die den Namen der Funktion enthält, die den Fehler verursacht hat.  Der Strukturmember **arg1** und **arg2** geben die Werte an, die den Fehler verursacht hat. \(Wenn nur ein Argument angegeben ist, wird es in **arg1** gespeichert.\)  
  
 Der Standardrückgabewert für den angegebenen Fehler ist **retval**.  Wenn Sie den Rückgabewert ändern, muss er angeben, ob ein Fehler tatsächlich aufgetreten ist.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_matherr`|\<math.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
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
  
## Ausgabe  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Long Double](../../misc/long-double.md)
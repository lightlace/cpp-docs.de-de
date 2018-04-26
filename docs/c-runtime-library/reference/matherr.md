---
title: _matherr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: a6c30b75b9c3a1d39e1b941fc65df1589d41a120
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="matherr"></a>_matherr

Behandlung von Mathematikfehlern

## <a name="syntax"></a>Syntax

```C
int _matherr( struct _exception * except );
```

### <a name="parameters"></a>Parameter

*except*<br/>
Ein Zeiger auf die Struktur, die Fehlerinformationen enthält.

## <a name="return-value"></a>Rückgabewert

**_matherr** gibt 0 für einen Fehler oder einen Wert ungleich NULL, um den Erfolg anzugeben. Wenn **_matherr** 0 zurückgibt, eine Fehlermeldung angezeigt werden können und **Errno** auf einen entsprechenden Fehlerwert festgelegt ist. Wenn **_matherr** gibt ein Wert ungleich NULL, keine Fehlermeldung angezeigt wird und **Errno** bleibt unverändert.

Weitere Informationen zu Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_matherr** Funktion verarbeitet, durch die Gleitkommafunktionen der mathematischen Bibliothek generierten Fehler. Diese Funktionen aufrufen **_matherr** kein Fehler aufgetreten ist.

Für die spezielle Fehlerbehandlung, bieten Sie eine andere Definition von **_matherr**. Wenn Sie die dynamisch verknüpfte Version der C-Laufzeitbibliothek (CRT) verwenden, können Sie die Standardeinstellung ersetzen **_matherr** routinemäßige in einem Client, die ausführbare Datei mit der eine benutzerdefinierte Versionsnummer. Sie können nicht ersetzt jedoch die Standardeinstellung **_matherr** routinemäßige in einem DLL-Client, der die CRT-DLL.

Tritt ein Fehler in einer Routine mathematische **_matherr** aufgerufen wird und ein Zeiger auf ein **_exception** Geben Sie die Struktur (definiert \<math.h >) als Argument. Die Struktur **_exception** enthält die folgenden Elemente:

```C
struct _exception
{
    int    type;   // exception type - see below
    char*  name;   // name of function where error occurred
    double arg1;   // first argument to function
    double arg2;   // second argument (if any) to function
    double retval; // value to be returned by function
};
```

Die **Typ** Element gibt den Typ der Mathematik-Fehler. Es ist einer der folgenden Werte, die in definierten \<math.h >:

|Makro|Bedeutung|
|-|-|
**_DOMAIN**|Domänenfehler Argument
**_SING**|Argument Singularität
**_OVERFLOW**|Überlaufbereichsfehler
**_PLOSS**|Partielle Verlust von "significance"
**_TLOSS**|Insgesamt Verlust von "significance"
**_UNDERFLOW**|Das Ergebnis ist zu klein, um dargestellt werden zu können. (Diese Bedingung wird derzeit nicht unterstützt.)

Der Strukturmember **name** ist ein Zeiger auf eine mit NULL endende Zeichenfolge mit dem Namen der Funktion, die den Fehler verursacht hat. Die Strukturmember **arg1** und **arg2** geben die Werte an, die den Fehler verursacht haben. Wenn nur ein Argument angegeben ist, wird Sie in gespeichert **arg1**.

Der Standardrückgabewert für den angegebenen Fehler ist **retval**. Wenn Sie den Rückgabewert ändern, muss dieser angeben, ob ein Fehler wirklich passiert ist.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_matherr**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
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

```Output
Special: using absolute value: log: _DOMAIN error
log( -2.0 ) = 6.931472e-01
Special: using absolute value: log10: _DOMAIN error
log10( -5.0 ) = 6.989700e-01
Normal: log( 0.0 ) = -inf
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>

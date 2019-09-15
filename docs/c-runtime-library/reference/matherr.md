---
title: _matherr
ms.date: 04/05/2018
api_name:
- _matherr
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _matherr
- matherr
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
ms.openlocfilehash: 340e3b8562e1f0f564810bc63cf6bd2e87ffdf63
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952759"
---
# <a name="_matherr"></a>_matherr

Behandlung von Mathematikfehlern

## <a name="syntax"></a>Syntax

```C
int _matherr( struct _exception * except );
```

### <a name="parameters"></a>Parameter

*except*<br/>
Ein Zeiger auf die Struktur, die Fehlerinformationen enthält.

## <a name="return-value"></a>Rückgabewert

**_matherr** gibt 0 zurück, um einen Fehler anzugeben, oder einen Wert ungleich NULL, um den Erfolg anzugeben. Wenn **_matherr** 0 zurückgibt, kann eine Fehlermeldung angezeigt werden, und **errno** wird auf einen entsprechenden Fehlerwert festgelegt. Wenn **_matherr** einen Wert ungleich 0 (null) zurückgibt, wird keine Fehlermeldung angezeigt, und **errno** bleibt unverändert.

Weitere Informationen zu Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_matherr** -Funktion verarbeitet Fehler, die von den Gleit Komma Funktionen der mathematischen Bibliothek generiert werden. Diese Funktionen nennen **_matherr** , wenn ein Fehler erkannt wird.

Für eine spezielle Fehlerbehandlung können Sie eine andere Definition von **_matherr**bereitstellen. Wenn Sie die dynamisch verknüpfte Version der C-Lauf Zeit Bibliothek (CRT) verwenden, können Sie die **_matherr** -Standard Routine in einer ausführbaren Client Datei durch eine benutzerdefinierte Version ersetzen. Die **_matherr** -Standard Routine kann jedoch nicht in einem DLL-Client der CRT-DLL ersetzt werden.

Wenn ein Fehler in einer mathematischen Routine auftritt, wird **_matherr** mit einem Zeiger auf eine **_Exception** -Typstruktur (definiert in \<Math. h >) als Argument aufgerufen. Die Struktur **_exception** enthält die folgenden Elemente:

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

Der **Typmember** gibt den Typ des mathematischen Fehlers an. Es handelt sich um einen der folgenden Werte, der \<in Math. h > definiert ist:

|Makro|Bedeutung|
|-|-|
| **_DOMAIN** | Argument Domänen Fehler |
| **_SING** | Argument Singularität |
| **_OVERFLOW** | Überlaufbereichsfehler |
| **_PLOSS** | Partieller Bedeutungsverlust |
| **_TLOSS** | Gesamtverlust der Bedeutung |
| **_UNDERFLOW** | Das Ergebnis ist zu klein, um dargestellt werden zu können. (Diese Bedingung wird derzeit nicht unterstützt.) |

Der Strukturmember **name** ist ein Zeiger auf eine mit NULL endende Zeichenfolge mit dem Namen der Funktion, die den Fehler verursacht hat. Die Strukturmember **arg1** und **arg2** geben die Werte an, die den Fehler verursacht haben. Wenn nur ein Argument angegeben wird, wird es in **arg1**gespeichert.

Der Standardrückgabewert für den angegebenen Fehler ist **retval**. Wenn Sie den Rückgabewert ändern, muss dieser angeben, ob ein Fehler wirklich passiert ist.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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

---
title: _onexit, _onexit_m
ms.date: 11/04/2016
api_name:
- _onexit
- _onexit_m
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
- _onexit
- onexit_m
- onexit
- _onexit_m
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
ms.openlocfilehash: 9afcd729f19f11b82e8f24c2b7fcf9ec40990deb
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951346"
---
# <a name="_onexit-_onexit_m"></a>_onexit, _onexit_m

Registriert eine Routine, die zum Zeitpunkt der Beendigung aufgerufen werden soll.

## <a name="syntax"></a>Syntax

```C
_onexit_t _onexit(
   _onexit_t function
);
_onexit_t_m _onexit_m(
   _onexit_t_m function
);
```

### <a name="parameters"></a>Parameter

*function*<br/>
Zeiger an eine bei Beendigung aufzurufende Funktion.

## <a name="return-value"></a>Rückgabewert

**_onexit** gibt bei Erfolg einen Zeiger auf die Funktion zurück oder **null** , wenn kein Speicherplatz zum Speichern des Funktions Zeigers vorhanden ist.

## <a name="remarks"></a>Hinweise

Der **_onexit** -Funktion wird die Adresse einer Funktion (*Funktion*) überlassen, die aufgerufen wird, wenn das Programm normal beendet wird. Aufeinanderfolgende Aufrufe von **_onexit** erstellen ein Register von Funktionen, die in der LIFO-Reihenfolge (Last-in-First-Out) ausgeführt werden. Die an **_onexit** über gebenden Funktionen können keine Parameter annehmen.

Wenn **_onexit** innerhalb einer DLL aufgerufen wird, werden mit **_onexit** registrierte Routinen beim Entladen einer DLL ausgeführt, nachdem **DllMain** mit DLL_PROCESS_DETACH aufgerufen wurde.

**_onexit** ist eine Microsoft-Erweiterung. Verwenden Sie für ANSI-Portabilität [Atexit](atexit.md). Die **_onexit_m** -Version der Funktion ist für die Verwendung im gemischten Modus vorgesehen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_onexit**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_onexit.c

#include <stdlib.h>
#include <stdio.h>

/* Prototypes */
int fn1(void), fn2(void), fn3(void), fn4 (void);

int main( void )
{
   _onexit( fn1 );
   _onexit( fn2 );
   _onexit( fn3 );
   _onexit( fn4 );
   printf( "This is executed first.\n" );
}

int fn1()
{
   printf( "next.\n" );
   return 0;
}

int fn2()
{
   printf( "executed " );
   return 0;
}

int fn3()
{
   printf( "is " );
   return 0;
}

int fn4()
{
   printf( "This " );
   return 0;
}
```

### <a name="output"></a>Ausgabe

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[__dllonexit](../../c-runtime-library/dllonexit.md)<br/>

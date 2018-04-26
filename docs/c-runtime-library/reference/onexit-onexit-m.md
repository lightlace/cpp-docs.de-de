---
title: _onexit, _onexit_m | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _onexit
- _onexit_m
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
- _onexit
- onexit_m
- onexit
- _onexit_m
dev_langs:
- C++
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ac59e64c1e47d699170af772aeba60a7895dfdc2
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="onexit-onexitm"></a>_onexit, _onexit_m

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

**_onexit** einen Zeiger auf die Funktion zurückgibt, im Erfolgsfall oder **NULL** es ist kein Speicherplatz zum Speichern des Funktionszeigers.

## <a name="remarks"></a>Hinweise

Die **_onexit** Funktion wird die Adresse einer Funktion übergeben (*Funktion*) aufgerufen werden, wenn das Programm normal beendet wird. Aufeinander folgende Aufrufe von **_onexit** erstellen ein Registers Funktionen, die in LIFO (Last-in-First-Out)-Reihenfolge ausgeführt werden. Die Funktionen übergeben, um **_onexit** können keine Parameter akzeptieren.

In die Groß-/Kleinschreibung beim **_onexit** innerhalb einer DLL registriert Routinen heißt **_onexit** ausführen auf eine DLL-Datei nach dem Entladen des **DllMain** mit DLL_PROCESS_DETACH aufgerufen wird.

**_onexit** ist eine Microsoft-Erweiterung. Verwenden Sie für ANSI-Portabilität [Atexit](atexit.md). Die **_onexit_m** Version der Funktion ist für die Verwendung des gemischten Modus.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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

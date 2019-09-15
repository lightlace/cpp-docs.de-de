---
title: atexit
ms.date: 11/04/2016
api_name:
- atexit
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
- atexit
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
ms.openlocfilehash: b91e6dad81f006b0b94ac17a940e840386f6d2b1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939657"
---
# <a name="atexit"></a>atexit

Verarbeitet die angegebene Funktion beim Beenden.

## <a name="syntax"></a>Syntax

```C
int atexit(
   void (__cdecl *func )( void )
);
```

### <a name="parameters"></a>Parameter

*func*<br/>
Die aufzurufende Funktion.

## <a name="return-value"></a>Rückgabewert

**atexit** gibt bei Erfolg 0 (null) oder einen Wert ungleich 0 (null) zurück, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Der **atexit** -Funktion wird die Adresse eines Funktions- *Func* , die aufgerufen wird, wenn das Programm normal beendet wird, übermittelt. Aufeinanderfolgende Aufrufe von **atexit** erstellen ein Register von Funktionen, die in der LIFO-Reihenfolge (Last in, First Out) ausgeführt werden. Die an " **atexit** " über gebenden Funktionen können keine Parameter annehmen. **atexit** und **_onexit** verwenden den Heap, um das Register von Funktionen zu speichern. Dementsprechend wird die Anzahl an Funktionen, die verzeichnet werden können, nur durch den Heapspeicher eingeschränkt.

Der Code in der **atexit** -Funktion sollte keine Abhängigkeit von einer DLL enthalten, die möglicherweise bereits entladen worden ist, wenn die **atexit** -Funktion aufgerufen wird.

Um eine ANSI-kompatible Anwendung zu generieren, verwenden Sie die ANSI-Standard- **atexit** -Funktion (anstelle der ähnlichen **_onexit** -Funktion).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**atexit**|\<stdlib.h>|

## <a name="example"></a>Beispiel

Dieses Programm überträgt vier Funktionen auf den Stapel von Funktionen, die ausgeführt werden, wenn **atexit** aufgerufen wird. Wenn das Programm beendet wird, werden die Programme nach dem Last In, First Out-Prinzip ausgeführt.

```C
// crt_atexit.c
#include <stdlib.h>
#include <stdio.h>

void fn1( void ), fn2( void ), fn3( void ), fn4( void );

int main( void )
{
   atexit( fn1 );
   atexit( fn2 );
   atexit( fn3 );
   atexit( fn4 );
   printf( "This is executed first.\n" );
}

void fn1()
{
   printf( "next.\n" );
}

void fn2()
{
   printf( "executed " );
}

void fn3()
{
   printf( "is " );
}

void fn4()
{
   printf( "This " );
}
```

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>

---
title: atexit
ms.date: 11/04/2016
apiname:
- atexit
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
- atexit
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
ms.openlocfilehash: 48f0fbfa1f3350f73899fcdbb3bf7922f1c6174d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556641"
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

**von "atexit"** gibt bei Erfolg 0 oder einen Wert ungleich NULL zurück, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Die **von "atexit"** Funktion wird die Adresse einer Funktion übergeben *Func* aufgerufen werden, wenn das Programm normal beendet wird. Aufeinander folgende Aufrufe von **von "atexit"** Erstellung eines Registers von Funktion, in der Last in, First Out (LIFO) Reihenfolge ausgeführt werden. Die Funktionen, die an **von "atexit"** können keine Parameter akzeptieren. **von "atexit"** und **_onexit** verwenden Sie den Heap, um die Registers von Funktion zu speichern. Dementsprechend wird die Anzahl an Funktionen, die verzeichnet werden können, nur durch den Heapspeicher eingeschränkt.

Der Code in der **von "atexit"** Funktion sollte eine Abhängigkeit von einer DLL, die bereits entladen wurde konnte keine enthalten die **von "atexit"** Funktion wird aufgerufen.

Um eine ANSI-kompatible Anwendung zu generieren, verwenden Sie die ANSI-Standardfunktion **von "atexit"** Funktion (statt der ähnlichen **_onexit** Funktion).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**atexit**|\<stdlib.h>|

## <a name="example"></a>Beispiel

Dieses Programm legt vier neue Funktionen im Stapel von Funktionen, die ausgeführt wird, wenn **von "atexit"** aufgerufen wird. Wenn das Programm beendet wird, werden die Programme nach dem Last In, First Out-Prinzip ausgeführt.

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

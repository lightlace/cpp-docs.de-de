---
title: atexit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a5dbe5e8bf71c268783893665e8e95bb587891a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

**Atexit** gibt 0 bei Erfolg oder einen Wert ungleich NULL zurück, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Die **Atexit** Funktion wird die Adresse einer Funktion übergeben *Func* aufgerufen werden, wenn das Programm normal beendet wird. Aufeinander folgende Aufrufe von **Atexit** erstellen ein Registers Funktionen, die in der Last in, First Out (LIFO) Reihenfolge ausgeführt werden. Die Funktionen übergeben, um **Atexit** können keine Parameter akzeptieren. **Atexit** und **_onexit** verwenden Sie den Heap, um die Registrierung von Funktionen aufzunehmen. Dementsprechend wird die Anzahl an Funktionen, die verzeichnet werden können, nur durch den Heapspeicher eingeschränkt.

Der Code in der **Atexit** Funktion dürfen nicht für jede Abhängigkeit auf eine beliebige DLL, die bereits entladen Wenn hätten verwendet werden können die **Atexit** Funktion aufgerufen wird.

Um eine ANSI-kompatible Anwendung zu erstellen, verwenden Sie die ANSI-Standard **Atexit** Funktion (anstatt das ähnliche **_onexit** Funktion).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**atexit**|\<stdlib.h>|

## <a name="example"></a>Beispiel

Dieses Programm Pushvorgänge vier Funktionen auf den Stapel von Funktionen, um ausgeführt wird, wenn **Atexit** aufgerufen wird. Wenn das Programm beendet wird, werden die Programme nach dem Last In, First Out-Prinzip ausgeführt.

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

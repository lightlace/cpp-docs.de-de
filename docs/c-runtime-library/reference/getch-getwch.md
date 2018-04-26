---
title: _getch, _getwch | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _getch
- _getwch
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getwch
- _getch
- _getwch
dev_langs:
- C++
helpviewer_keywords:
- characters, getting from console
- getch function
- _getwch function
- console, reading from
- _getch function
- getwch function
ms.assetid: cc116be7-cff2-4274-970f-5e7b18ccc05c
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a438af27f2191b8a612b01b7c12ef139d6361dc4
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="getch-getwch"></a>_getch, _getwch

Ruft ein Zeichen aus der Konsole ab, ohne es zu wiederholen.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _getch( void );
wint_t _getwch( void );
```

## <a name="return-value"></a>Rückgabewert

Gibt das gelesene Zeichen zurück. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die **_getch** und **_getwch** Funktionen lesen ein einzelnes Zeichen aus der Konsole ohne Echo das Zeichen. Mit keiner dieser Funktionen kann STRG+C gelesen werden. Beim Lesen einer Steuertaste oder einer Pfeiltaste muss jede Funktion zweimal aufgerufen werden. Der erste Aufruf gibt 0 oder 0xE0 und der zweite Aufruf den tatsächlichen Tastencode zurück.

Diese Funktionen sperren den aufrufenden Thread und sind daher threadsicher. Nicht sperrende Versionen finden Sie unter [_getch_nolock _getwch_nolock](getch-nolock-getwch-nolock.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettch**|**_getch**|**_getch**|**_getwch**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_getch**|\<conio.h>|
|**_getwch**|\<conio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_getch.c
// compile with: /c
// This program reads characters from
// the keyboard until it receives a 'Y' or 'y'.

#include <conio.h>
#include <ctype.h>

int main( void )
{
   int ch;

   _cputs( "Type 'Y' when finished typing keys: " );
   do
   {
      ch = _getch();
      ch = toupper( ch );
   } while( ch != 'Y' );

   _putch( ch );
   _putch( '\r' );    // Carriage return
   _putch( '\n' );    // Line feed
}
```

```Input
abcdefy
```

```Output
Type 'Y' when finished typing keys: Y
```

## <a name="see-also"></a>Siehe auch

[Konsole und Port-E/A](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getche, _getwche](getche-getwche.md)<br/>
[_cgets, _cgetws](../../c-runtime-library/cgets-cgetws.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>

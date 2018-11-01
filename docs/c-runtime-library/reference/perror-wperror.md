---
title: perror, _wperror
ms.date: 11/04/2016
apiname:
- _wperror
- perror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wperror
- _tperror
- perror
helpviewer_keywords:
- _tperror function
- tperror function
- wperror function
- error messages, printing
- printing error messages
- _wperror function
- perror function
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
ms.openlocfilehash: c9026a96ecc74640eb2bcd7004d5d1e0fc287e38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474476"
---
# <a name="perror-wperror"></a>perror, _wperror

Druckt eine Fehlermeldung.

## <a name="syntax"></a>Syntax

```C
void perror(
   const char *message
);
void _wperror(
   const wchar_t *message
);
```

### <a name="parameters"></a>Parameter

*message*<br/>
Zu druckende Zeichenfolgennachricht.

## <a name="remarks"></a>Hinweise

Die **Perror** -Funktion druckt eine Fehlermeldung an **"stderr"**. **_wperror** ist eine Breitzeichen-Version von **_perror**; die *Nachricht* Argument **_wperror** ist eine Breitzeichen-Zeichenfolge. **_wperror** und **_perror** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tperror**|**perror**|**perror**|**_wperror**|

*Nachricht* wird zuerst gedruckt, gefolgt von einem Doppelpunkt und dann nach der Systemfehlermeldung für den letzten Bibliotheksaufruf, der den Fehler erzeugt und schließlich ein neue-Zeile-Zeichen. Wenn *Nachricht* ist ein null-Zeiger oder ein Zeiger auf eine null-Zeichenfolge **Perror** druckt nur die System-Fehlermeldung.

Die Fehlernummer wird in der Variablen [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) (in ERRNO.H definiert) gespeichert. Über die Variable [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird auf die Systemfehlermeldungen zugegriffen, die als Array von Meldungen nach Fehlernummern geordnet sind. **pError** druckt die entsprechende Fehlermeldung, indem die **Errno** Wert als Index für **_sys_errlist**. Der Wert der Variablen [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ist definiert als die maximale Anzahl von Elementen in der **_sys_errlist** Array.

Rufen Sie für genaue Ergebnisse zu erhalten **Perror** sofort, nachdem eine Bibliotheksroutine einen Fehler zurückgibt. Andernfalls können nachfolgende Aufrufe überschreiben die **Errno** Wert.

In der Windows Betriebssystem werden einige **Errno** Werte in ERRNO aufgeführt. H werden nicht verwendet. Diese Werte sind für die Verwendung des UNIX-Betriebssystems reserviert. Finden Sie unter [_doserrno, Errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) eine Liste der **Errno** Werte, die von der Windows-Betriebssystem verwendet. **pError** druckt eine leere Zeichenfolge für eine beliebige **Errno** Wert, der nicht von diesen Plattformen verwendet.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**perror**|\<stdio.h > oder \<stdlib.h >|
|**_wperror**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_perror.c
// compile with: /W3
/* This program attempts to open a file named
* NOSUCHF.ILE. Because this file probably doesn't exist,
* an error message is displayed. The same message is
* created using perror, strerror, and _strerror.
*/

#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <share.h>

int main( void )
{
   int  fh;

   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )
   {
      /* Three ways to create error message: */
      perror( "perror says open failed" );
      printf( "strerror says open failed: %s\n",
         strerror( errno ) ); // C4996
      printf( _strerror( "_strerror says open failed" ) ); // C4996
      // Note: strerror and _strerror are deprecated; consider
      // using strerror_s and _strerror_s instead.
   }
   else
   {
      printf( "open succeeded on input file\n" );
      _close( fh );
   }
}
```

```Output
perror says open failed: No such file or directory
strerror says open failed: No such file or directory
_strerror says open failed: No such file or directory
```

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md)<br/>

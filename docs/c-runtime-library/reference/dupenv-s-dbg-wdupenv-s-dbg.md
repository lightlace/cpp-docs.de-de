---
title: _dupenv_s_dbg, _wdupenv_s_dbg
ms.date: 11/04/2016
apiname:
- _dupenv_s_dbg
- _wdupenv_s_dbg
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
- _tdupenv_s_dbg
- _dupenv_s_dbg
- _wdupenv_s_dbg
helpviewer_keywords:
- _tdupenv_s_dbg function
- dupenv_s_dbg function
- _wdupenv_s_dbg function
- environment variables
- tdupenv_s_dbg function
- wdupenv_s_dbg function
- _dupenv_s_dbg function
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
ms.openlocfilehash: 95d8c18a0ebc543304fdb6bf51c4adde589333aa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579588"
---
# <a name="dupenvsdbg-wdupenvsdbg"></a>_dupenv_s_dbg, _wdupenv_s_dbg

Ruft einen Wert aus der aktuellen Umgebung ab.  Versionen von [_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md), die Speicher mit [_malloc_dbg](malloc-dbg.md) belegen, um zusätzliche Debuginformationen bereitzustellen.

## <a name="syntax"></a>Syntax

```C
errno_t _dupenv_s_dbg(
   char **buffer,
   size_t *numberOfElements,
   const char *varname,
   int blockType,
   const char *filename,
   int linenumber
);
errno_t _wdupenv_s_dbg(
   wchar_t **buffer,
   size_t * numberOfElements,
   const wchar_t *varname,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Puffer zum Speichern des Variablenwerts.

*numberOfElements*<br/>
Größe des *Puffer*.

*Variablenname*<br/>
Umgebungsvariablenname.

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei oder **NULL**.

## <a name="return-value"></a>Rückgabewert

Null bei Erfolg, ein Fehlercode, wenn ein Fehler auftritt.

Diese Funktionen überprüfen ihre Parameter; Wenn *Puffer* oder *Varname* ist **NULL**, wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzen die Funktionen **Errno** zu **EINVAL** und zurückgeben **EINVAL**.

Wenn diese Funktionen können nicht genügend Arbeitsspeicher zuordnen, die sie festgelegt *Puffer* zu **NULL** und *NumberOfElements* 0, und Rückgabe **ENOMEM**.

## <a name="remarks"></a>Hinweise

Die **_dupenv_s_dbg** und **_wdupenv_s_dbg** -Funktionen sind identisch mit **_dupenv_s** und **_wdupenv_s** mit dem Unterschied, dass wenn **_DEBUG** wird definiert, verwenden Sie diese Funktionen die Debugversion von [Malloc](malloc.md), [_malloc_dbg](malloc-dbg.md), um Speicher für den Wert der Umgebungsvariable zu belegen. Informationen zu den Debugfunktionen von **_malloc_dbg**, finden Sie unter [_malloc_dbg](malloc-dbg.md).

In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen. Stattdessen definieren Sie das Flag **_CRTDBG_MAP_ALLOC**. Wenn **_CRTDBG_MAP_ALLOC** definiert ist, werden Aufrufe von **_dupenv_s** und **_wdupenv_s** neu zu **_dupenv_s_dbg** und **_wdupenv_s_dbg**, mit der *BlockType* festgelegt **_NORMAL_BLOCK**. Also, Sie müssen nicht dieser Funktionen explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als markieren **_CLIENT_BLOCK**. Weitere Informationen zu den Blocktypen finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s_dbg**|**_dupenv_s_dbg**|**_dupenv_s_dbg**|**_wdupenv_s_dbg**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_dupenv_s_dbg**|\<crtdbg.h>|
|**_wdupenv_s_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_dupenv_s_dbg.c
#include  <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
   if ( err ) return -1;
   printf( "nonexistentvariable = %s\n", pValue );
   free( pValue ); // It's OK to call free with NULL
}
```

```Output
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl
nonexistentvariable = (null)
```

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[Umgebungskonstanten](../../c-runtime-library/environmental-constants.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>

---
title: rename, _wrename
ms.date: 11/04/2016
apiname:
- rename
- _wrename
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wrename
- _trename
- Rename
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
ms.openlocfilehash: 3536bfb6c38c99a8d6d943102fb9303dd4d85b7b
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326134"
---
# <a name="rename-wrename"></a>rename, _wrename

Benennt eine Datei oder ein Verzeichnis um.

## <a name="syntax"></a>Syntax

```C
int rename(
   const char *oldname,
   const char *newname
);
int _wrename(
   const wchar_t *oldname,
   const wchar_t *newname
);
```

### <a name="parameters"></a>Parameter

*oldname*<br/>
Zeiger auf den alten Namen.

*newname*<br/>
Zeiger auf den neuen Namen.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt bei Erfolg 0 zurück. Bei einem Fehler, die Funktion gibt einen Wert ungleich NULL zurück und legt **Errno** auf einen der folgenden Werte:

|errno-Wert|Bedingung|
|-|-|
| **EACCES** | Die Datei oder das Verzeichnis, das von *newname* angegeben wird, ist bereits vorhanden oder konnte nicht erstellt werden (ungültiger Pfad). Möglicherweise ist auch *oldname* ein Verzeichnis, und *newname* gibt einen anderen Pfad an. |
| **ENOENT** | Von *oldname* angegebene Datei oder Pfad wurden nicht gefunden. |
| **EINVAL** | Name enthält ungültige Zeichen. |

Weitere mögliche Rückgabewerte finden Sie unter [_doserrno, _errno, syserrlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **rename**-Funktion benennt die Datei oder das Verzeichnis, die von *oldname* angegeben wurden, auf den von *newname* gegebenen Namen. Der alte Name muss der Pfad einer vorhandenen Datei oder eines vorhandenen Verzeichnisses sein. Der neue Name darf nicht der Name einer vorhandenen Datei oder eines vorhandenen Verzeichnisses sein. Sie können **rename** nutzen, um eine Datei von einem Verzeichnis oder Gerät zu einem anderen zu verschieben, indem Sie einen anderen Pfad im *newname*-Argument angeben. Allerdings können Sie **rename** nicht verwenden, um ein Verzeichnis zu verschieben. Verzeichnisse können umbenannt, aber nicht verschoben werden.

**_wrename** ist eine Breitzeichen-Version von **_rename**; die Argumente für **_wrename** sind Breitzeichen Zeichenfolgen. **_wrename** und **_rename** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_trename**|**rename**|**rename**|**_wrename**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**rename**|\<io.h> oder \<stdio.h>|
|**_wrename**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_renamer.c
/* This program attempts to rename a file named
* CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation
* to succeed, a file named CRT_RENAMER.OBJ must exist and
* a file named CRT_RENAMER.JBO must not exist.
*/

#include <stdio.h>

int main( void )
{
   int  result;
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";

   /* Attempt to rename file: */
   result = rename( old, new );
   if( result != 0 )
      printf( "Could not rename '%s'\n", old );
   else
      printf( "File '%s' renamed to '%s'\n", old, new );
}
```

### <a name="output"></a>Output

```Output
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>

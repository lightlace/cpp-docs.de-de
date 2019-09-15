---
title: _umask_s
ms.date: 11/04/2016
api_name:
- _umask_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- unmask_s
- _umask_s
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
ms.openlocfilehash: 21d9ba194f85e40c3c5a4d67d16ebca9721f68f8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945984"
---
# <a name="_umask_s"></a>_umask_s

Legt die Standard-Dateiberechtigungsmaske fest. Dies ist eine Version von [_umask](umask.md) mit Sicherheitserweiterungen wie in den [Sicherheitsfunktionen in CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t _umask_s(
   int mode,
   int * pOldMode
);
```

### <a name="parameters"></a>Parameter

*mode*<br/>
Standard-Berechtigungseinstellung.

*pOldMode*<br/>
Der vorherige Wert der Berechtigungseinstellung.

## <a name="return-value"></a>Rückgabewert

Gibt einen Fehlercode zurück, wenn der *Modus* keinen gültigen Modus angibt oder der *poldmode* -Zeiger **null**ist.

### <a name="error-conditions"></a>Fehlerbedingungen

|*mode*|*pOldMode*|Rückgabewert|Inhalt von *poldmode*|
|------------|----------------|----------------------|--------------------------------|
|any|**NULL**|**EINVAL**|nicht geändert|
|ungültiger Modus|any|**EINVAL**|nicht geändert|

Wenn eine der obengenannten Bedingungen auftritt, wird der Handler für ungültige Parameter aufgerufen wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt _umask_s **EINVAL** zurück und legt **errno** auf **EINVAL**fest.

## <a name="remarks"></a>Hinweise

Die **_umask_s** -Funktion legt die Datei Berechtigungs Maske des aktuellen Prozesses auf den Modus fest, der durch den- *Modus*angegeben wird. Die Datei Berechtigungs Maske ändert die Berechtigungseinstellung für neue Dateien, die von **_creat**, **_open**oder **_sopen**erstellt wurden. Wenn ein Bit in der Maske 1 ist, wird das entsprechende Bit im angeforderten Berechtigungswert der Datei auf 0 (nicht zulässig) festgelegt. Wenn ein Bit in der Maske 0 ist, bleibt das entsprechende Bit unverändert. Die Berechtigungseinstellung für eine neue Datei wird erst festgelegt, wenn die Datei zum ersten Mal geschlossen wird.

Der ganzzahlige Ausdruck " *pmode* " enthält eine oder beide der folgenden Manifest-Konstanten, die in "sys\status" definiert sind. Micha

|*pmode*||
|-|-|
|**_S_IWRITE**|Schreiben zugelassen.|
|**_S_IREAD**|Lesen erlaubt.|
|**_S_IREAD** \| **_S_IWRITE**|Lesen und Schreiben erlaubt.|

Wenn beide Konstanten angegeben werden, werden Sie mit dem bitweisen OR-Operator ( **|** ) verknüpft. Wenn das *Mode* -Argument **_S_IREAD**ist, ist das Lesen nicht zulässig (die Datei ist schreibgeschützt). Wenn das *Mode* -Argument **_S_IWRITE**ist, ist das Schreiben nicht zulässig (die Datei ist schreibgeschützt). Wenn z.B. das Schreib-Bit in der Maske festgelegt ist, sind alle neuen Dateien schreibgeschützt. Beachten Sie, dass in MS-DOS und Windows-Betriebssystemen alle Dateien lesbar sind und es nicht möglich ist, nur Schreibberechtigungen zu vergeben. Daher hat das Festlegen des gelesenen Bits mit **_umask_s** keine Auswirkung auf den Modus der Datei.

Wenn *pmode* keine Kombination aus einer der Manifest-Konstanten ist oder einen alternativen Satz von Konstanten enthält, ignoriert die Funktion diese einfach.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_umask_s**|\<io.h> und \<sys/stat.h> und \<sys/types.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_umask_s.c
/* This program uses _umask_s to set
* the file-permission mask so that all future
* files will be created as read-only files.
* It also displays the old mask.
*/

#include <sys/stat.h>
#include <sys/types.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int oldmask, err;

   /* Create read-only files: */
   err = _umask_s( _S_IWRITE, &oldmask );
   if (err)
   {
      printf("Error setting the umask.\n");
      exit(1);
   }
   printf( "Oldmask = 0x%.4x\n", oldmask );
}
```

```Output
Oldmask = 0x0000
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_umask](umask.md)<br/>

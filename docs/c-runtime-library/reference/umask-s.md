---
title: _umask_s
ms.date: 11/04/2016
apiname:
- _umask_s
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
ms.openlocfilehash: 878a22cb2884c36e792ff8dead1453582addb5b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268910"
---
# <a name="umasks"></a>_umask_s

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

Gibt einen Fehlercode zurück, wenn *Modus* gibt keinen gültigen Modus oder den *pOldMode* Zeiger **NULL**.

### <a name="error-conditions"></a>Fehlerbedingungen

|*mode*|*pOldMode*|Rückgabewert|Inhalt der *pOldMode*|
|------------|----------------|----------------------|--------------------------------|
|any|**NULL**|**EINVAL**|nicht geändert|
|ungültiger Modus|any|**EINVAL**|nicht geändert|

Wenn eine der obengenannten Bedingungen auftritt, wird der Handler für ungültige Parameter aufgerufen wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **_umask_s** gibt **EINVAL** und **Errno** zu **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_umask_s** Funktion setzt die dateiberechtigungsmaske des aktuellen Prozesses auf den vom angegebenen Modus *Modus*. Die dateiberechtigungsmaske ändert die berechtigungseinstellung neuer Dateien, die von erstellten **_creat**, **_open**, oder **_sopen**. Wenn ein Bit in der Maske 1 ist, wird das entsprechende Bit im angeforderten Berechtigungswert der Datei auf 0 (nicht zulässig) festgelegt. Wenn ein Bit in der Maske 0 ist, bleibt das entsprechende Bit unverändert. Die Berechtigungseinstellung für eine neue Datei wird erst festgelegt, wenn die Datei zum ersten Mal geschlossen wird.

Der ganzzahlige Ausdruck *Pmode* enthält eine oder beide der folgenden Manifestkonstanten, die in SYS\STAT definiert. H:

|*pmode*||
|-|-|
|**_S_IWRITE**|Schreiben zugelassen.|
|**_S_IREAD**|Lesen erlaubt.|
|**_S_IREAD** \| **_S_IWRITE**|Lesen und Schreiben erlaubt.|

Wenn beide Konstanten gegeben sind, werden sie mit dem bitweisen OR-Operator verbunden ( **|** ). Wenn die *Modus* Argument **_S_IREAD**, lesen, ist nicht zulässig (die Datei ist lesegeschützt). Wenn die *Modus* Argument **_S_IWRITE**, Schreiben nicht zulässig (die Datei ist schreibgeschützt). Wenn z.B. das Schreib-Bit in der Maske festgelegt ist, sind alle neuen Dateien schreibgeschützt. Beachten Sie, dass in MS-DOS und Windows-Betriebssystemen alle Dateien lesbar sind und es nicht möglich ist, nur Schreibberechtigungen zu vergeben. Daher ist das Festlegen der Lesevorgangs-bit mit **_umask_s** hat keine Auswirkungen auf den Dateimodus.

Wenn *Pmode* keine Kombination aus einer der Manifestkonstanten ist oder enthält eine Alternative Gruppe von Konstanten, die Funktion einfach ignoriert diese.

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

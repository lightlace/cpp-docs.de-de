---
title: _umask
ms.date: 11/04/2016
apiname:
- _umask
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
- _umask
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
ms.openlocfilehash: 113bf97b0fe93204cd41de20bc36a8be080a88b6
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327667"
---
# <a name="umask"></a>_umask

Legt die Standard-Dateiberechtigungsmaske fest. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_umask_s](umask-s.md).

## <a name="syntax"></a>Syntax

```C
int _umask( int pmode );
```

### <a name="parameters"></a>Parameter

*pmode*<br/>
Standard-Berechtigungseinstellung.

## <a name="return-value"></a>Rückgabewert

**_umask** gibt zurück, den vorherigen Wert der *Pmode*. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die **_umask** Funktion setzt die dateiberechtigungsmaske des aktuellen Prozesses auf den vom angegebenen Modus *Pmode*. Die dateiberechtigungsmaske ändert die berechtigungseinstellung neuer Dateien, die von erstellten **_creat**, **_open**, oder **_sopen**. Wenn ein Bit in der Maske 1 ist, wird das entsprechende Bit im angeforderten Berechtigungswert der Datei auf 0 (nicht zulässig) festgelegt. Wenn ein Bit in der Maske 0 ist, bleibt das entsprechende Bit unverändert. Die Berechtigungseinstellung für eine neue Datei wird erst festgelegt, wenn die Datei zum ersten Mal geschlossen wird.

Der ganzzahlige Ausdruck *Pmode* enthält eine oder beide der folgenden Manifestkonstanten, die in SYS\STAT definiert. H:

|*pmode*| |
|-|-|
| **_S_IWRITE** | Schreiben zugelassen. |
| **_S_IREAD** | Lesen erlaubt. |
| **_S_IREAD** &AMP;#124; **_S_IWRITE** | Lesen und Schreiben erlaubt. |

Wenn beide Konstanten gegeben sind, werden sie mit dem bitweisen OR-Operator verbunden ( **&#124;** ). Wenn die *Pmode* Argument **_S_IREAD**, lesen, ist nicht zulässig (die Datei ist lesegeschützt). Wenn die *Pmode* Argument **_S_IWRITE**, Schreiben nicht zulässig (die Datei ist schreibgeschützt). Wenn z.B. das Schreib-Bit in der Maske festgelegt ist, sind alle neuen Dateien schreibgeschützt. Beachten Sie, dass in MS-DOS und Windows-Betriebssystemen alle Dateien lesbar sind und es nicht möglich ist, nur Schreibberechtigungen zu vergeben. Daher ist das Festlegen der Lesevorgangs-bit mit **_umask** hat keine Auswirkungen auf den Dateimodus.

Wenn *Pmode* keine Kombination aus einer der Manifestkonstanten ist oder enthält eine Alternative Gruppe von Konstanten, die Funktion einfach ignoriert diese.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_umask**|\<io.h>, \<sys/stat.h>, \<sys/types.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_umask.c
// compile with: /W3
// This program uses _umask to set
// the file-permission mask so that all future
// files will be created as read-only files.
// It also displays the old mask.
#include <sys/stat.h>
#include <sys/types.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int oldmask;

   /* Create read-only files: */
   oldmask = _umask( _S_IWRITE ); // C4996
   // Note: _umask is deprecated; consider using _umask_s instead
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

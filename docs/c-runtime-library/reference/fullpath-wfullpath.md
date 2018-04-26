---
title: _fullpath, _wfullpath | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _fullpath
- _wfullpath
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
- wfullpath
- fullpath
- _wfullpath
- _fullpath
dev_langs:
- C++
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f619bae0c3d6d0d3f45e4c8ee6b25458f10007e4
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="fullpath-wfullpath"></a>_fullpath, _wfullpath

Erstellt einen absoluten oder vollständigen Pfadnamen für den angegebenen relativen Pfadnamen

## <a name="syntax"></a>Syntax

```C
char *_fullpath(
   char *absPath,
   const char *relPath,
   size_t maxLength
);
wchar_t *_wfullpath(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength
);
```

### <a name="parameters"></a>Parameter

*absPath*<br/>
Zeiger auf einen Puffer, der den absoluten oder vollständigen Pfadnamen oder NULL enthält

*relPath*<br/>
Relativer Pfadname.

*maxLength*<br/>
Maximale Länge des Puffers des absoluten Pfadnamens (*AbsPath*). Diese Länge in Byte für wird **_fullpath** jedoch in Breitzeichen (**Wchar_t**) für **_wfullpath**.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf einen Puffer, enthält des absolute Pfadname (*AbsPath*). Wenn ein Fehler vorliegt (z. B., wenn der Wert übergeben *RelPath* enthält einen Laufwerkbuchstaben an, die ist ungültig oder kann nicht gefunden werden, oder wenn die Länge der erstellte absolute Pfadname (*AbsPath*) ist größer als *MaxLength*), gibt die Funktion **NULL**.

## <a name="remarks"></a>Hinweise

Die **_fullpath** Funktion erweitert den relativen Pfadnamen in *RelPath* an ihre voll qualifizierten oder absolute Pfad und speichert diese Namen in *AbsPath*. Wenn *AbsPath* NULL ist, **"malloc"** wird verwendet, um einen Puffer von ausreichend lang ist, um den Pfadnamen halten zuzuordnen. Der Aufrufer muss diesen Puffer freigeben. Dieser relative Pfadname gibt vom aktuellen Speicherort einen Pfad zu einem anderen Speicherort an (z.B. das aktuelle Arbeitsverzeichnis: "."). Ein absoluter Pfadname ist die Erweiterung eines relativen Pfadnamens, der den gesamten Pfad ausdrückt, der dafür erforderlich ist, um die gewünschte Position aus dem Stammverzeichnis des Dateisystems zu erreichen. Im Gegensatz zu **_makepath**, **_fullpath** können verwendet werden, um den absoluten Pfadnamen für relative Pfade zu erhalten (*RelPath*), enthalten ". /"oder".. / "im Namen.

Um beispielsweise C-Laufzeitroutinen verwenden zu können, muss die Anwendung die Headerdateien enthalten, die die Deklarationen für die Routinen enthalten. Jede Headerdatei enthält Anweisungen, die relativ auf den Speicherort der Datei verweisen (aus dem Arbeitsverzeichnis der Anwendung):

```C
#include <stdlib.h>
```

Wenn der absolute Pfad (der tatsächliche Dateisystem-Speicherort) der Datei z.B. wie folgt lautet:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** automatisch behandelt Multibyte-Zeichenfolgenargumente nach Bedarf, erkennen Multibyte-Zeichensequenzen entsprechend der multibyte-Codepage aktuell in Verwendung. **_wfullpath** ist eine Breitzeichen-Version von **_fullpath**; die Zeichenfolgenargumente auf **_wfullpath** sind Zeichenfolgen mit Breitzeichen. **_wfullpath** und **_fullpath** Verhalten sich identisch, außer dass **_wfullpath** verarbeitet keine Multibyte-Zeichenfolgen.

Wenn **_DEBUG** und **_CRTDBG_MAP_ALLOC** sind beide definiert, Aufrufe von **_fullpath** und **_wfullpath** werden durch Aufrufe von ersetzt **_fullpath_dbg** und **_wfullpath_dbg** zum Debuggen von speicherbelegungen zuzulassen. Weitere Informationen finden Sie unter [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md).

Ruft diese Funktion den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md), wenn *Maxlen* kleiner oder gleich 0 ist. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt **NULL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

Wenn die *AbsPath* Puffer ist **NULL**, **_fullpath** Aufrufe ["malloc"](malloc.md) keinen Puffer zuweisen und ignoriert die *MaxLength*  Argument. Es liegt in der Verantwortung des Aufrufers, die Zuordnung für diesen Puffer richtig wieder aufzuheben (mithilfe von [free](free.md)). Wenn die *RelPath* Argument gibt an, ein Laufwerk, das aktuelle Verzeichnis des fehlenden Laufwerks mit dem Pfad kombiniert wird.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h>|
|**_wfullpath**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fullpath.c
// This program demonstrates how _fullpath
// creates a full path from a partial path.

#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <direct.h>

void PrintFullPath( char * partialPath )
{
   char full[_MAX_PATH];
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )
      printf( "Full path is: %s\n", full );
   else
      printf( "Invalid path\n" );
}

int main( void )
{
   PrintFullPath( "test" );
   PrintFullPath( "\\test" );
   PrintFullPath( "..\\test" );
}
```

```Output
Full path is: C:\Documents and Settings\user\My Documents\test
Full path is: C:\test
Full path is: C:\Documents and Settings\user\test
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>

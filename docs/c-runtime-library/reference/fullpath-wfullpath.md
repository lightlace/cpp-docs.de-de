---
title: _fullpath, _wfullpath
ms.date: 11/04/2016
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
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
ms.openlocfilehash: aeacaf581b7f33ee893754c192ae547376ce73ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550396"
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
Zeiger auf einen Puffer, der den absoluten oder vollständigen Pfadnamen enthält oder **NULL**.

*relPath*<br/>
Relativer Pfadname.

*MaxLength*<br/>
Maximale Länge des Puffers Namen absoluten Pfad (*AbsPath*). Diese Länge ist, in Bytes für **_fullpath** jedoch in Breitzeichen (**"wchar_t"**) für **_wfullpath**.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf einen Puffer mit den absoluten Pfadnamen zurück (*AbsPath*). Wenn ein Fehler auftritt (z. B., wenn der Wert übergeben *RelPath* enthält einen Laufwerkbuchstaben an, die ist ungültig oder wurde nicht gefunden, oder wenn die Länge der erstellte absolute Pfadname (*AbsPath*) ist größer als *MaxLength*), die Funktion gibt **NULL**.

## <a name="remarks"></a>Hinweise

Die **_fullpath** Funktion erweitert den relativen Pfadnamen in *RelPath* zum vollqualifizierten oder absoluten Pfad und speichert diesen Namen in *AbsPath*. Wenn *AbsPath* ist **NULL**, **Malloc** wird verwendet, um einen Puffer von ausreichender Größe der Pfadname enthält zuordnen. Der Aufrufer muss diesen Puffer freigeben. Dieser relative Pfadname gibt vom aktuellen Speicherort einen Pfad zu einem anderen Speicherort an (z.B. das aktuelle Arbeitsverzeichnis: "."). Ein absoluter Pfadname ist die Erweiterung eines relativen Pfadnamens, der den gesamten Pfad ausdrückt, der dafür erforderlich ist, um die gewünschte Position aus dem Stammverzeichnis des Dateisystems zu erreichen. Im Gegensatz zu **_makepath**, **_fullpath** kann verwendet werden, um den absoluten Pfadnamen für relative Pfade zu erhalten (*RelPath*), enthalten ". /"oder".. / "im Namen.

Um beispielsweise C-Laufzeitroutinen verwenden zu können, muss die Anwendung die Headerdateien enthalten, die die Deklarationen für die Routinen enthalten. Jede Headerdatei enthält Anweisungen, die relativ auf den Speicherort der Datei verweisen (aus dem Arbeitsverzeichnis der Anwendung):

```C
#include <stdlib.h>
```

Wenn der absolute Pfad (der tatsächliche Dateisystem-Speicherort) der Datei z.B. wie folgt lautet:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** behandelt automatisch Multibyte-Zeichenfolge nach Bedarf erkennt multibytezeichensequenzen gemäß dem multibyte-Codepage aktuell. **_wfullpath** ist eine Breitzeichen-Version von **_fullpath**; die Zeichenfolgenargumente für **_wfullpath** sind Breitzeichen Zeichenfolgen. **_wfullpath** und **_fullpath** Verhalten sich identisch, außer dass **_wfullpath** verarbeitet keine Multibyte-Zeichenfolgen.

Wenn **_DEBUG** und **_CRTDBG_MAP_ALLOC** werden beide definiert, Aufrufe von **_fullpath** und **_wfullpath** werden durch Aufrufe von ersetzt **_fullpath_dbg** und **_wfullpath_dbg** zum Debuggen von speicherbelegungen zuzulassen. Weitere Informationen finden Sie unter [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md).

Ruft diese Funktion den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md), wenn *Maxlen* ist kleiner als oder gleich 0. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt **NULL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

Wenn die *AbsPath* Puffer **NULL**, **_fullpath** Aufrufe [Malloc](malloc.md) keinen Puffer zuweisen und ignoriert die *MaxLength*  Argument. Es liegt in der Verantwortung des Aufrufers, die Zuordnung für diesen Puffer richtig wieder aufzuheben (mithilfe von [free](free.md)). Wenn die *RelPath* Argument gibt an, ein Laufwerk, das aktuelle Verzeichnis dieses Laufwerks mit dem Pfad kombiniert wird.

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

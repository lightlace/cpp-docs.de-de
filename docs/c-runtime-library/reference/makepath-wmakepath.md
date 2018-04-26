---
title: _makepath, _wmakepath | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _makepath
- _wmakepath
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
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c6ad1331021331e9c9ddc1d1344aae8ed164ce2
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath

Erstellen Sie einen Pfadnamen aus Komponenten. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="syntax"></a>Syntax

```C
void _makepath(
   char *path,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
void _wmakepath(
   wchar_t *path,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
```

### <a name="parameters"></a>Parameter

*Pfad* vollständiger Pfad Puffer.

*Laufwerk* enthält einen Buchstaben (A, B usw.), das gewünschte Laufwerk und einen optionalen nachgestellten Doppelpunkt entspricht. **_makepath** fügt den Doppelpunkt im zusammengesetzten Pfad, wenn er nicht vorhanden ist. Wenn *Laufwerk* ist **NULL** oder zeigt auf eine leere Zeichenfolge, ohne Laufwerkbuchstabe angezeigt, in der kombinierten *Pfad* Zeichenfolge.

*Dir* enthält den Pfad von Verzeichnissen, nicht einschließlich der Laufwerkkennzeichner oder den tatsächlichen Dateinamen. Der nachstehende Schrägstrich ist optional, und entweder einem Schrägstrich (/) oder einen umgekehrten Schrägstrich (\\) oder beide können verwendet werden, in einer einzelnen *Dir* Argument. Wenn kein nachstehender Schrägstrich (/ oder \\) angegeben ist, wird er automatisch eingefügt. Wenn *Dir* ist **NULL** oder verweist auf eine leere Zeichenfolge, die keine Verzeichnispfad wird an die kombinierten eingefügt *Pfad* Zeichenfolge.

*Fname* enthält den Basisdateinamen ohne Dateinamenerweiterungen. Wenn *Fname* ist **NULL** oder verweist auf eine leere Zeichenfolge ist, kein Dateiname eingefügt wird, in die kombinierten *Pfad* Zeichenfolge.

*Ext* enthält die tatsächlichen Dateinamenerweiterung mit oder ohne führenden Punkt (.). **_makepath** fügt automatisch den Zeitraum ein, wenn er nicht in erscheint *Ext*. Wenn *Ext* ist **NULL** oder verweist auf eine leere Zeichenfolge, die keine Erweiterung eingefügt wird, in die kombinierten *Pfad* Zeichenfolge.

## <a name="remarks"></a>Hinweise

Die **_makepath** Funktion erstellt eine zusammengesetzten Pfadzeichenfolge aus Einzelkomponenten Speichern des Ergebnisses in *Pfad*. Die *Pfad* kann ein Laufwerkbuchstabe, Verzeichnispfad, Dateiname und Erweiterung enthalten. **_wmakepath** ist eine Breitzeichen-Version von **_makepath**; die Argumente für **_wmakepath** sind Zeichenfolgen mit Breitzeichen. **_wmakepath** und **_makepath** Verhalten sich andernfalls identisch.

**Sicherheitshinweis** Verwenden Sie eine mit NULL endende Zeichenfolge. Um Sicherheitsangriffen durch Pufferüberläufe zu vermeiden, die Null-terminierte Zeichenfolge darf maximal die Größe der *Pfad* Puffer. **_makepath** wird nicht sichergestellt, dass die Länge der Zeichenfolge für den zusammengesetzten Pfad nicht überschritten wird **_MAX_PATH**. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

Die *Pfad* -Argument muss zu einem leeren Puffer groß genug für den vollständigen Pfad verweisen. Die kombinierten *Pfad* muss nicht größer als die **_MAX_PATH** Konstante in Stdlib.h definiert.

Wenn der Pfad ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Darüber hinaus **Errno** festgelegt ist, um **EINVAL**. **NULL** Werte für alle anderen Parameter zulässig sind.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_makepath.c
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];

   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996
   // Note: _makepath is deprecated; consider using _makepath_s instead
   printf( "Path created with _makepath: %s\n\n", path_buffer );
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996
   // Note: _splitpath is deprecated; consider using _splitpath_s instead
   printf( "Path extracted with _splitpath:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath: c:\sample\crt\makepath.c

Path extracted with _splitpath:
   Drive: c:
   Dir: \sample\crt\
   Filename: makepath
   Ext: .c
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>

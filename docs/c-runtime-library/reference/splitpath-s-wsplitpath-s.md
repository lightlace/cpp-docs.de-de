---
title: _splitpath_s, _wsplitpath_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wsplitpath_s
- _splitpath_s
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
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs:
- C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 29
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7b04dec6f1f8129283815c2dcb6211f93139800f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s

Unterteilen eines Pfadnamens in Komponenten Dies sind Versionen von [_splitpath, _wsplitpath](splitpath-wsplitpath.md) mit Sicherheitsverbesserungen, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t _splitpath_s(
   const char * path,
   char * drive,
   size_t driveNumberOfElements,
   char * dir,
   size_t dirNumberOfElements,
   char * fname,
   size_t nameNumberOfElements,
   char * ext,
   size_t extNumberOfElements
);
errno_t _wsplitpath_s(
   const wchar_t * path,
   wchar_t * drive,
   size_t driveNumberOfElements,
   wchar_t *dir,
   size_t dirNumberOfElements,
   wchar_t * fname,
   size_t nameNumberOfElements,
   wchar_t * ext,
   size_t extNumberOfElements
);
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _splitpath_s(
   const char *path,
   char (&drive)[drivesize],
   char (&dir)[dirsize],
   char (&fname)[fnamesize],
   char (&ext)[extsize]
); // C++ only
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _wsplitpath_s(
   const wchar_t *path,
   wchar_t (&drive)[drivesize],
   wchar_t (&dir)[dirsize],
   wchar_t (&fname)[fnamesize],
   wchar_t (&ext)[extsize]
); // C++ only
```

### <a name="parameters"></a>Parameter

*path*<br/>
Vollständiger Pfad

*Laufwerk*<br/>
Laufwerkbuchstabe, gefolgt von einem Doppelpunkt (**:**). Sie können übergeben **NULL** für diesen Parameter, wenn Sie nicht den Buchstaben des Laufwerks erforderlich ist.

*driveNumberOfElements*<br/>
Die Größe der *Laufwerk* Puffers in Einzelbyte-oder Breitzeichen. Wenn *Laufwerk* ist **NULL**, dieser Wert muss 0 sein.

*dir*<br/>
Verzeichnispfad, einschl. nachstehender Schrägstrich. Schrägstriche ( **/** ), umgekehrten Schrägstrichen ( **\\** ), oder beides verwendet werden können. Sie können übergeben **NULL** für diesen Parameter, wenn Sie keinen Pfad für das Verzeichnis benötigen.

*dirNumberOfElements*<br/>
Die Größe der *Dir* Puffers in Einzelbyte-oder Breitzeichen. Wenn *Dir* ist **NULL**, dieser Wert muss 0 sein.

*fname*<br/>
Basisdateiname (ohne Erweiterung). Sie können übergeben **NULL** für diesen Parameter, wenn Sie den Dateinamen nicht benötigen.

*nameNumberOfElements*<br/>
Die Größe der *Fname* Puffers in Einzelbyte-oder Breitzeichen. Wenn *Fname* ist **NULL**, dieser Wert muss 0 sein.

*ext*<br/>
Erweiterung, einschließlich führender Zeitraum (**.**). Sie können übergeben **NULL** für diesen Parameter, wenn Sie nicht mit die Erweiterung benötigen.

*extNumberOfElements*<br/>
Die Größe des *Ext* Puffers in Einzelbyte-oder Breitzeichen. Wenn *Ext* ist **NULL**, dieser Wert muss 0 sein.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.

### <a name="error-conditions"></a>Fehlerbedingungen

|Bedingung|Rückgabewert|
|---------------|------------------|
|*Pfad* ist **NULL**|**EINVAL**|
|*Laufwerk* ist **NULL**, *DriveNumberOfElements* ungleich NULL ist|**EINVAL**|
|*Laufwerk* nicht**NULL**, *DriveNumberOfElements* 0 (null)|**EINVAL**|
|*Dir* ist **NULL**, *DirNumberOfElements* ungleich NULL ist|**EINVAL**|
|*Dir* nicht**NULL**, *DirNumberOfElements* 0 (null)|**EINVAL**|
|*Fname* ist **NULL**, *NameNumberOfElements* ungleich NULL ist|**EINVAL**|
|*Fname* nicht**NULL**, *NameNumberOfElements* 0 (null)|**EINVAL**|
|*Ext* ist **NULL**, *ExtNumberOfElements* ungleich NULL ist|**EINVAL**|
|*Ext* nicht**NULL**, *ExtNumberOfElements* 0 (null)|**EINVAL**|

Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** inventurüberprüfung **EINVAL**.

Eine der Puffer ist zu kurz, um das Ergebnis aufzunehmen, diese Funktionen deaktivieren, wenn alle Puffer leere Zeichenfolgen, legen Sie **Errno** auf **ERANGE**, inventurüberprüfung **ERANGE**.

## <a name="remarks"></a>Hinweise

Die **_splitpath_s** Funktion teilt einen Pfad in vier Komponenten. **_splitpath_s** automatisch behandelt Multibyte-Zeichenfolgenargumente nach Bedarf, erkennen Multibyte-Zeichensequenzen entsprechend der multibyte-Codepage aktuell in Verwendung. **_wsplitpath_s** ist eine Breitzeichen-Version von **_splitpath_s**; die Argumente für **_wsplitpath_s** sind Zeichenfolgen mit Breitzeichen. Andernfalls verhalten sich diese Funktionen identisch

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Jede Komponente des vollständigen Pfads wird in einem separaten Puffer gespeichert. die Manifestkonstanten **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME**, und **_MAX_EXT** (definiert in STDLIB. H) Geben Sie die maximale zulässige Größe für die einzelnen Komponenten der Datei ein. Dateikomponenten, die größer als die entsprechenden Manifestkonstanten sind, können zur Beschädigung des Heaps führen.

In der folgenden Tabelle werden die Werte der Manifestkonstanten aufgelistet.

|name|Wert|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Wenn der vollständige Pfad eine Komponente (z. B. ein Dateiname), keinen enthält **_splitpath_s** weist eine leere Zeichenfolge in den entsprechenden Puffer.

Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_makepath_s _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>

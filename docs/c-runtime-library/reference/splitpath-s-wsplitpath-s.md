---
title: _splitpath_s, _wsplitpath_s
ms.date: 11/04/2016
api_name:
- _wsplitpath_s
- _splitpath_s
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
ms.openlocfilehash: 8eeb6a0f43827578c5d5ba900c35a3ac30f4ae7c
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625841"
---
# <a name="_splitpath_s-_wsplitpath_s"></a>_splitpath_s, _wsplitpath_s

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

*Antrie*<br/>
Laufwerk Buchstabe, gefolgt von einem Doppelpunkt ( **:** ). Sie können **null** für diesen Parameter übergeben, wenn Sie den Laufwerk Buchstaben nicht benötigen.

*drivenverberofelements*<br/>
Die Größe des *Laufwerk* Puffers in Einzel Byte-oder breit Zeichen. Wenn das *Laufwerk* NULL ist, muss dieser Wert 0 ( **null**) sein.

*has*<br/>
Verzeichnispfad, einschl. nachstehender Schrägstrich. Schrägstriche ( **/** ), umgekehrte Schrägstriche ( **\\** ) oder beides können verwendet werden. Sie können **null** für diesen Parameter übergeben, wenn Sie den Verzeichnispfad nicht benötigen.

*dirnumosterements*<br/>
Die Größe des *dir* -Puffers in Einzel Byte-oder breit Zeichen. Wenn *dir* NULL ist, muss dieser Wert 0 ( **null**) sein.

*fname*<br/>
Basisdateiname (ohne Erweiterung). Sie können **null** für diesen Parameter übergeben, wenn Sie den Dateinamen nicht benötigen.

*namenumberofelements*<br/>
Die Größe des *bName* -Puffers in Einzel Byte-oder breit Zeichen. Wenn der Name von " *f* " **null**ist, muss dieser Wert "0" lauten.

*Antrags*<br/>
Erweiterung des Datei namens, einschließlich des führenden Zeitraums ( **.** ). Sie können **null** für diesen Parameter übergeben, wenn Sie die Dateinamenerweiterung nicht benötigen.

*extzahlosterements*<br/>
Die Größe des *ext* -Puffers in Einzel Byte-oder breit Zeichen. Wenn *ext* NULL ist, muss dieser Wert 0 ( **null**) sein.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.

### <a name="error-conditions"></a>Fehlerbedingungen

|Bedingung|Rückgabewert|
|---------------|------------------|
|der *Pfad* ist **null** .|**EINVAL**|
|*Laufwerk* ist **null**, *drivenumschlag* ist nicht NULL|**EINVAL**|
|*Laufwerk* ist nicht**null**, *drivenumschlag* ist 0 (null)|**EINVAL**|
|" *dir* " ist **null**, *dirnumosterements* ist ungleich 0 (null).|**EINVAL**|
|" *dir* " ist nicht**null**, *dirnumosterements* ist 0 (null).|**EINVAL**|
|*fname* ist **null**, *namenumberosterements* ist ungleich 0 (null).|**EINVAL**|
|*fname* ist nicht**null**, *namenumberosterements* ist 0 (null).|**EINVAL**|
|*ext* ist **null**, *extnummeriosterements* ist ungleich 0 (null).|**EINVAL**|
|*ext* ist nicht**null**, *extnumosterements* ist 0 (null).|**EINVAL**|

Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legen diese Funktionen " **errno** " auf " **EINVAL** " fest und geben " **EINVAL**" zurück.

Wenn einer der Puffer zu kurz ist, um das Ergebnis aufzunehmen, löschen diese Funktionen alle Puffer in leere Zeichen folgen, legen Sie **errno** auf **ERANGE**fest, und geben Sie **ERANGE**zurück.

## <a name="remarks"></a>Hinweise

Die **_splitpath_s** -Funktion unterteilt einen Pfad in seine vier Komponenten. **_splitpath_s** verarbeitet nach Bedarf automatisch Multibytezeichen-Zeichen folgen Argumente und erkennt multibytezeichensequenzen gemäß der derzeit verwendeten Multibytezeichen-Codepage. **_wsplitpath_s** ist eine breit Zeichen Version von **_splitpath_s**. die Argumente für **_wsplitpath_s** sind Zeichen folgen mit breit Zeichen. Andernfalls verhalten sich diese Funktionen identisch

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Jede Komponente des vollständigen Pfads wird in einem separaten Puffer gespeichert. Die Manifest-Konstanten **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME**und **_MAX_EXT** (in stdlib definiert). H) geben Sie die maximal zulässige Größe für jede Datei Komponente an. Dateikomponenten, die größer als die entsprechenden Manifestkonstanten sind, können zur Beschädigung des Heaps führen.

In der folgenden Tabelle werden die Werte der Manifestkonstanten aufgelistet.

|-Name|Wert|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Wenn der vollständige Pfad keine Komponente (z. b. ein Dateiname) enthält, weist **_splitpath_s** dem entsprechenden Puffer eine leere Zeichenfolge zu.

Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).

Die Debug-Bibliotheksversionen dieser Funktionen füllen zunächst den Puffer mit "0xFE" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> oder \<wchar.h>|

Zusätzliche Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_makepath_s _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>

---
title: _splitpath, _wsplitpath | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsplitpath
- _splitpath
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
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
dev_langs:
- C++
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69123bfd07d992d96c504e538ded157c49991dab
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221607"
---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath

Unterteilen Sie einen Pfadnamen in Komponenten. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

## <a name="syntax"></a>Syntax

```C
void _splitpath(
   const char *path,
   char *drive,
   char *dir,
   char *fname,
   char *ext
);
void _wsplitpath(
   const wchar_t *path,
   wchar_t *drive,
   wchar_t *dir,
   wchar_t *fname,
   wchar_t *ext
);
```

### <a name="parameters"></a>Parameter

*Pfad* vollständiger Pfad.

*Laufwerk* Laufwerkbuchstabe, gefolgt von einem Doppelpunkt (**:**). Sie können übergeben **NULL** für diesen Parameter, wenn Sie nicht der Buchstabe des Laufwerks erforderlich ist.

*Dir* Verzeichnispfad, einschl. nachstehenden Schrägstrich. Schrägstriche ( **/** ), umgekehrte Schrägstriche ( **\\** ), oder beides verwendet werden können. Sie können übergeben **NULL** für diesen Parameter, wenn Sie den Verzeichnispfad nicht erforderlich ist.

*Fname* Dateiname (ohne Erweiterung) basieren. Sie können übergeben **NULL** für diesen Parameter, wenn Sie den Dateinamen nicht erforderlich ist.

*Ext* Dateierweiterung, einschl. führender Punkt (**.**). Sie können übergeben **NULL** für diesen Parameter, wenn Sie die Dateierweiterung nicht erforderlich ist.

## <a name="remarks"></a>Hinweise

Die **_splitpath** -Funktion teilt einen Pfad in seine vier Komponenten. **_splitpath** behandelt automatisch Multibyte-Zeichenfolge nach Bedarf erkennt multibytezeichensequenzen gemäß dem multibyte-Codepage aktuell. **_wsplitpath** ist eine Breitzeichen-Version von **_splitpath**; die Argumente für **_wsplitpath** sind Breitzeichen Zeichenfolgen. Anderenfalls verhalten sich diese Funktionen identisch.

**Sicherheitshinweis:** Diese Funktionen stellen eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar. Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns). Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

Jede Komponente des vollständigen Pfads wird in einem separaten Puffer gespeichert. die Manifestkonstanten **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME**, und **_MAX_EXT** (definiert in STDLIB. H) Geben Sie die maximale Größe für jede Dateikomponente an. Dateikomponenten, die größer als die entsprechenden Manifestkonstanten sind, können zur Beschädigung des Heaps führen.

Jeder Puffer muss so groß wie die entsprechende Manifestkonstante sein, damit ein potenzieller Pufferüberlauf vermieden werden kann.

In der folgenden Tabelle werden die Werte der Manifestkonstanten aufgelistet.

|name|Wert|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

Wenn der vollständige Pfad keine Komponente (z. B. Dateiname), enthält **_splitpath** leere Zeichenfolgen zu den entsprechenden Puffern.

Sie können übergeben **NULL** zu **_splitpath** für alle Parameter außer *Pfad* , das ist nicht erforderlich.

Wenn *Pfad* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **EINVAL**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h>|
|**_wsplitpath**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe Beispiel für [_makepath](makepath-wmakepath.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>

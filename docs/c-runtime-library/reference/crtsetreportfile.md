---
title: _CrtSetReportFile
ms.date: 11/04/2016
apiname:
- _CrtSetReportFile
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
apitype: DLLExport
f1_keywords:
- CrtSetReportFile
- _CrtSetReportFile
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
ms.openlocfilehash: 32a560e09c47468daf48c185e23d6e289c6d1d9b
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343016"
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile

Nach der Verwendung von [_CrtSetReportMode](crtsetreportmode.md) an **_CRTDBG_MODE_FILE**, können Sie angeben, das Dateihandle, um den Meldungstext zu empfangen. **_CrtSetReportFile** wird auch vom verwendet [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) an das Ziel des Texts (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>Parameter

*reportType*<br/>
Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**, und **_CRT_ASSERT**.

*reportFile*<br/>
Neue Berichtsdatei für *ReportType*.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreichem Abschluss **_CrtSetReportFile** gibt die vorherige Berichtsdatei definiert der Typ im angegebenen *ReportType*. Wenn ein ungültiger Wert übergeben wird, für die *ReportType*, ruft diese Funktion den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **_CRTDBG_HFILE_ERROR**. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

**_CrtSetReportFile** wird zusammen mit den [_CrtSetReportMode](crtsetreportmode.md) Funktion, um das Ziel oder die Ziele für einen bestimmten Berichtstyp von generierten definieren **_CrtDbgReport**. Wenn **_CrtSetReportMode** aufgerufen wurde, um das Zuweisen der **_CRTDBG_MODE_FILE** -Berichtsmodus für einen bestimmten Berichtstyp, **_CrtSetReportFile** dann aufgerufen werden soll, um Definieren Sie die Datei oder den Stream, der als Ziel verwenden. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetReportFile** werden während der vorverarbeitung entfernt.

Die folgende Liste zeigt die verfügbaren Optionen für *ReportFile* und das resultierende Verhalten von **_CrtDbgReport**. Diese Optionen werden als Bitflags in Crtdbg.h definiert.

- **Datei-handle**

   Ein Handle für die Datei, die das Ziel der Meldungen ist. Es wird nicht versucht, die Gültigkeit des Handles zu überprüfen. Sie müssen das Handle für die Datei öffnen und schließen. Zum Beispiel:

   ```C
   HANDLE hLogFile;
   hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,
      FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,
      FILE_ATTRIBUTE_NORMAL, NULL);
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, hLogFile);

   _RPT0(_CRT_WARN,"file message\n");
   CloseHandle(hLogFile);
   ```

- **_CRTDBG_FILE_STDERR**

   Schreibt eine Meldung an **"stderr"**, die wie folgt umgeleitet werden können:

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   Schreibt eine Meldung an **"stdout"**, die umgeleitet werden können.

- **_CRTDBG_REPORT_FILE**

   Gibt den aktuellen Berichtsmodus zurück.

Die Berichtsdatei, die von jedem Berichtstyp verwendet wird, kann separat gesteuert werden. Es ist beispielsweise möglich, anzugeben, dass eine *ReportType* von **_CRT_ERROR** gemeldet werden **"stderr"**, während eine *ReportType* von **_CRT_ASSERT** an ein benutzerdefiniertes Dateihandle oder den Stream gemeldet werden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

Die Konsole wird in apps für universelle Windows-Plattform (UWP) nicht unterstützt. Standardstreamhandles, die mit der Konsole verknüpft sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in UWP-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken:** Debugversionen von [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md) nur.

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>

---
title: _CrtSetReportFile
ms.date: 11/04/2016
api_name:
- _CrtSetReportFile
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtSetReportFile
- _CrtSetReportFile
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
ms.openlocfilehash: bf88bae40031f6e92d6f936ac8a50f85d6c4e36c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942282"
---
# <a name="_crtsetreportfile"></a>_CrtSetReportFile

Nachdem Sie [_CrtSetReportMode](crtsetreportmode.md) zum Angeben von **_CRTDBG_MODE_FILE**verwendet haben, können Sie das Datei Handle angeben, um den Meldungs Text zu empfangen. **_CrtSetReportFile** wird auch von [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) verwendet, um das textziel anzugeben (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>Parameter

*reportType*<br/>
Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**und **_CRT_ASSERT**.

*reportFile*<br/>
Neue Berichtsdatei für Report *Type*.

## <a name="return-value"></a>Rückgabewert

Nach erfolgreichem Abschluss gibt **_CrtSetReportFile** die vorherige Berichtsdatei zurück, die für *den in Report Type angegebenen*Berichtstyp definiert ist. Wenn ein ungültiger Wert für Report *Type*übergeben wird, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird **errno** auf **EINVAL** festgelegt, und die Funktion gibt **_CRTDBG_HFILE_ERROR**zurück. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

**_CrtSetReportFile** wird mit der [_CrtSetReportMode](crtsetreportmode.md) -Funktion verwendet, um das Ziel oder die Ziele für einen bestimmten Berichtstyp zu definieren, der von **_CrtDbgReport**generiert wird. Wenn **_CrtSetReportMode** aufgerufen wurde, um den **_CRTDBG_MODE_FILE** -Berichtsmodus für einen bestimmten Berichtstyp zuzuweisen, dann sollte **_CrtSetReportFile** aufgerufen werden, um die spezifische Datei oder den Stream zu definieren, die als Ziel verwendet werden soll. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetReportFile** während der Vorverarbeitung entfernt.

In der folgenden Liste werden die verfügbaren Optionen für *Report File* und das resultierende Verhalten von **_CrtDbgReport**angezeigt. Diese Optionen werden als Bitflags in Crtdbg.h definiert.

- **Datei Handle**

   Ein Handle für die Datei, die das Ziel der Meldungen ist. Es wird nicht versucht, die Gültigkeit des Handles zu überprüfen. Sie müssen das Handle für die Datei öffnen und schließen. Beispiel:

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

   Schreibt eine Nachricht in **stderr**, die wie folgt umgeleitet werden kann:

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   Schreibt eine Nachricht in **stdout**, die Sie umleiten können.

- **_CRTDBG_REPORT_FILE**

   Gibt den aktuellen Berichtsmodus zurück.

Die Berichtsdatei, die von jedem Berichtstyp verwendet wird, kann separat gesteuert werden. Beispielsweise ist es möglich, anzugeben, dass ein Report *Type* von **_CRT_ERROR** an **stderr**gemeldet werden soll, während ein Report *Type* von **_CRT_ASSERT** an ein benutzerdefiniertes Datei Handle oder einen Stream gemeldet wird.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

Die-Konsole wird in universelle Windows-Plattform-Apps (UWP) nicht unterstützt. Die Standarddaten Strom Handles, die der Konsole, **stdin**, **stdout**und **stderr**zugeordnet sind, müssen umgeleitet werden, bevor Sie von C-Lauf Zeitfunktionen in UWP-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>

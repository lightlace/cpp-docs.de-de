---
title: _CrtSetReportMode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd4ac54cd4bd8877e8a6ba32f585ef5d5e29e65c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403260"
---
# <a name="crtsetreportmode"></a>_CrtSetReportMode

Gibt an, das Ziel bzw. die Ziele für einen bestimmten Berichtstyp von generierten **_CrtDbgReport** und Makros, die aufgerufen werden [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md), wie z. B. [_ASSERT-und _ASSERTE, _ASSERT_EXPR-Makros](assert-asserte-assert-expr-macros.md), [_ASSERT-und _ASSERTE-, _ASSERT_EXPR-Makros](assert-asserte-assert-expr-macros.md), [_RPT, _RPTF-, _RPTW-und _RPTFW-Makros](rpt-rptf-rptw-rptfw-macros.md), und [_RPT, _RPTF-, _RPTW-und _RPTFW-Makros](rpt-rptf-rptw-rptfw-macros.md) (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>Parameter

*Definition*<br/>
Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**, und **_CRT_ASSERT**.

*reportMode*<br/>
Neuer Berichtsmodus bzw. neue berichtsmodi für *Definition*.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreichem Abschluss **_CrtSetReportMode** gibt den vorherigen Berichtsmodus bzw. die Modi für der Berichtstyp im angegebenen *Definition*. Wenn ein ungültiger Wert, als übergeben wird *Definition* oder ein ungültiger Modus für angegeben wird *ReportMode*, **_CrtSetReportMode** wird als Handler für ungültige Parameter aufgerufen in der beschriebenen [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt-1 zurück. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

**_CrtSetReportMode** gibt das Ausgabeziel für **_CrtDbgReport**. Da die Makros [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md), [_RPT](rpt-rptf-rptw-rptfw-macros.md), und [_RPTF](rpt-rptf-rptw-rptfw-macros.md) Aufrufen **_CrtDbgReport**, **_CrtSetReportMode** gibt das Ausgabeziel von Text mit diesen Makros festgelegt.

Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetReportMode** während der vorverarbeitung entfernt.

Wenn Sie nicht aufrufen **_CrtSetReportMode** zum Definieren des ausgabeziels der Meldungen, dann sind die folgenden Standardwerte gültig:

- Assertionsfehler werden an ein Debugmeldungsfenster weitergeleitet.

- Warnungen von Windows-Anwendungen werden an das Ausgabefenster des Debuggers gesendet.

- Warnungen von Konsolenanwendungen werden nicht angezeigt.

In der folgenden Tabelle werden die Berichtstypen aufgeführt, die in "Crtdbg.h" definiert sind.

|Berichtstyp|Beschreibung|
|-----------------|-----------------|
|**_CRT_WARN**|Warnungen, Meldungen und Informationen, die keine unmittelbare Aufmerksamkeit erfordern.|
|**_CRT_ERROR**|Fehler, nicht behebbare Probleme sowie Probleme, die unmittelbare Aufmerksamkeit erfordern.|
|**_CRT_ASSERT**|Assertionsfehler (überwachte Ausdrücke, die zum Auswerten **"false"**).|

Die **_CrtSetReportMode** Funktion weist die im angegebenen neuen Berichtsmodus *ReportMode* in den Bericht im angegebenen *Definition* und gibt die zuvor definierte Berichtsmodus für *Definition*. Die folgende Tabelle listet die verfügbaren Optionen für *ReportMode* und das resultierende Verhalten von **_CrtDbgReport**. Diese Optionen werden als Bitflags in Crtdbg.h definiert.

|Berichtsmodus|_CrtDbgReport-Verhalten|
|-----------------|-----------------------------|
|**_CRTDBG_MODE_DEBUG**|Schreibt die Nachricht in das Ausgabefenster des Debuggers.|
|**_CRTDBG_MODE_FILE**|Schreibt die Nachricht an ein vom Benutzer bereitgestelltes Dateihandle. [_CrtSetReportFile](crtsetreportfile.md) sollte aufgerufen werden, um die als Ziel zu verwendende bestimmte Datei bzw. den bestimmten Stream zu definieren.|
|**_CRTDBG_MODE_WNDW**|Erstellt ein Meldungsfeld, um die Nachricht zusammen mit anzuzeigen die [abort](abort.md), **wiederholen**, und **ignorieren** Schaltflächen.|
|**_CRTDBG_REPORT_MODE**|Gibt *ReportMode* für den angegebenen *Definition*:<br /><br /> 1 **_CRTDBG_MODE_FILE**<br /><br /> 2 **_CRTDBG_MODE_DEBUG**<br /><br /> 4 **_CRTDBG_MODE_WNDW**|

Jeder Berichtstyp kann mithilfe von einem, zwei oder drei Modi oder keinem Modus gemeldet werden. Daher ist es möglich, mehrere Ziele festzulegen, die für einen einzelnen Berichtstyp definiert werden. Das folgende Codefragment verursacht beispielsweise Assertionsfehler Versand an beide ein debugmeldungsfenster und an **"stderr"**:

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

Außerdem können die Berichterstellungsmodi für jeden Berichtstyp separat gesteuert werden. Es ist beispielsweise möglich, anzugeben, dass eine *Definition* von **_CRT_WARN** werden an eine ausgabedebugzeichenfolge gesendet wird, während er sich **_CRT_ASSERT** werden mithilfe der Fenster einer Debugmeldung angezeigt und an **"stderr"**, wie zuvor veranschaulicht wurde.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_CrtSetReportMode**|\<crtdbg.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken:** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>

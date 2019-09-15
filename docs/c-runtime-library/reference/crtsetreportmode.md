---
title: _CrtSetReportMode
ms.date: 11/04/2016
api_name:
- _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
ms.openlocfilehash: ae7e83ac009d572f8a9f6484519b0cdfb7499ce3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938463"
---
# <a name="_crtsetreportmode"></a>_CrtSetReportMode

Gibt das Ziel oder die Ziele für einen bestimmten Berichtstyp an, der von **_CrtDbgReport** generiert wird, und alle Makros, die [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md), wie z. b. [_ASSERT, _ASSERTE, _ASSERT_EXPR Makros](assert-asserte-assert-expr-macros.md), [_ASSERT, _ASSERTE, _ ASSERT_EXPR Makros](assert-asserte-assert-expr-macros.md), [_RPT, _RPTF, _RPTW, _RPTFW Makros](rpt-rptf-rptw-rptfw-macros.md)und [_RPT, _RPTF, _RPTW, _RPTFW Makros](rpt-rptf-rptw-rptfw-macros.md) (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>Parameter

*reportType*<br/>
Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**und **_CRT_ASSERT**.

*reportMode*<br/>
Neuer Berichtsmodus oder-Modus für Report *Type*.

## <a name="return-value"></a>Rückgabewert

Nach erfolgreichem Abschluss gibt **_CrtSetReportMode** den vorherigen Berichtsmodus bzw. die Berichts Modi für den Berichtstyp zurück, der in *Report Type angegeben*ist. Wenn ein ungültiger Wert als Report *Type* übergeben wird oder ein ungültiger Modus für *Report Mode*angegeben ist, ruft **_CrtSetReportMode** den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion **errno** auf **EINVAL** fest und gibt-1 zurück. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

**_CrtSetReportMode** gibt das Ausgabeziel für **_CrtDbgReport**an. Da die Makros [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md), [_RPT](rpt-rptf-rptw-rptfw-macros.md)und [_RPTF](rpt-rptf-rptw-rptfw-macros.md) **call_CrtDbgReport _CrtSetReportMode**, gibt das Ausgabeziel von Text an, der mit diesen Makros angegeben wird.

Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetReportMode** während der Vorverarbeitung entfernt.

Wenn Sie **_CrtSetReportMode** nicht zum Definieren des Ausgabe Ziels von Nachrichten aufzurufen, sind die folgenden Standardwerte wirksam:

- Assertionsfehler werden an ein Debugmeldungsfenster weitergeleitet.

- Warnungen von Windows-Anwendungen werden an das Ausgabefenster des Debuggers gesendet.

- Warnungen von Konsolenanwendungen werden nicht angezeigt.

In der folgenden Tabelle werden die Berichtstypen aufgeführt, die in "Crtdbg.h" definiert sind.

|Berichtstyp|Beschreibung|
|-----------------|-----------------|
|**_CRT_WARN**|Warnungen, Meldungen und Informationen, die keine unmittelbare Aufmerksamkeit erfordern.|
|**_CRT_ERROR**|Fehler, nicht behebbare Probleme sowie Probleme, die unmittelbare Aufmerksamkeit erfordern.|
|**_CRT_ASSERT**|Assertionsfehler (übergebene Ausdrücke, die zu **false**ausgewertet werden).|

Die **_CrtSetReportMode** -Funktion weist den neuen Berichtsmodus, *der in Report* *Mode* angegeben ist, dem im Report Type angegebenen Berichtstyp zu und gibt den zuvor definierten Berichts *Modus für Report Type zurück*. In der folgenden Tabelle werden die verfügbaren Optionen für *Report Mode* und das resultierende Verhalten von **_CrtDbgReport**aufgelistet. Diese Optionen werden als Bitflags in Crtdbg.h definiert.

|Berichtsmodus|_CrtDbgReport-Verhalten|
|-----------------|-----------------------------|
|**_CRTDBG_MODE_DEBUG**|Schreibt die Nachricht in das Ausgabefenster des Debuggers.|
|**_CRTDBG_MODE_FILE**|Schreibt die Nachricht an ein vom Benutzer bereitgestelltes Dateihandle. [_CrtSetReportFile](crtsetreportfile.md) sollte aufgerufen werden, um die als Ziel zu verwendende bestimmte Datei bzw. den bestimmten Stream zu definieren.|
|**_CRTDBG_MODE_WNDW**|Erstellt ein Meldungs Feld, um die Meldung zusammen mit den Schaltflächen [Abbrechen](abort.md), **wiederholen**und **ignorieren** anzuzeigen.|
|**_CRTDBG_REPORT_MODE**|Gibt den *Report Mode* -Wert für den angegebenen *reportType*zurück:<br /><br /> 1   **_CRTDBG_MODE_FILE**<br /><br /> 2   **_CRTDBG_MODE_DEBUG**<br /><br /> 4   **_CRTDBG_MODE_WNDW**|

Jeder Berichtstyp kann mithilfe von einem, zwei oder drei Modi oder keinem Modus gemeldet werden. Daher ist es möglich, mehrere Ziele festzulegen, die für einen einzelnen Berichtstyp definiert werden. Beispielsweise bewirkt das folgende Code Fragment, dass Fehler bei der Überprüfung sowohl an das Fenster "Debugmeldung" als auch an " **stderr**" gesendet werden:

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

Außerdem können die Berichterstellungsmodi für jeden Berichtstyp separat gesteuert werden. Es ist z. b. möglich, anzugeben, dass ein Report *Type* von **_CRT_WARN** an eine debugabdebugzeichenfolge gesendet werden soll, während **_CRT_ASSERT** mithilfe eines debugmeldungs Fensters angezeigt und an **stderr**gesendet wird, wie zuvor veranschaulicht.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_CrtSetReportMode**|\<crtdbg.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>

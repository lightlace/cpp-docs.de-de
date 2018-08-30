---
title: _CrtDbgReport _CrtDbgReportW | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtDbgReport
- _CrtDbgReportW
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
- CrtDbgReport
- CrtDbgReportW
- _CrtDbgReportW
- _CrtDbgReport
dev_langs:
- C++
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5aa7efb7881b00933afab92a7157c09e0f769605
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204422"
---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW

Generiert einen Bericht mit einer Debugmeldung und sendet den Bericht zu drei möglichen Zielen (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
int _CrtDbgReport(
   int reportType,
   const char *filename,
   int linenumber,
   const char *moduleName,
   const char *format [,
   argument] ...
);
int _CrtDbgReportW(
   int reportType,
   const wchar_t *filename,
   int linenumber,
   const wchar_t *moduleName,
   const wchar_t *format [,
   argument] ...
);
```

### <a name="parameters"></a>Parameter

*reportType*<br/>
Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**, und **_CRT_ASSERT**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, in dem assert/Bericht aufgetreten ist, oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in dem assert/Bericht aufgetreten ist, oder **NULL**.

*moduleName*<br/>
Zeiger auf den Namen des Moduls (.exe oder .dll), in dem die Assertion oder der Bericht aufgetreten ist.

*format*<br/>
Zeiger auf die Formatsteuerelementzeichenfolge, mit der die Benutzermeldung erstellt wird.

*Argument*<br/>
Von verwendete optionale ersatzargumente *Format*.

## <a name="return-value"></a>Rückgabewert

Für alle berichtsziele **_CrtDbgReport** und **_CrtDbgReportW** 1, wenn ein Fehler tritt auf, und 0 zurückgeben, wenn keine Fehler aufgetreten sind. Wenn das Berichtsziel jedoch das Fenster einer Debugmeldung ist und der Benutzer auf die Schaltfläche **Wiederholen** klickt, dann geben diese Funktionen 1 zurück. Wenn der Benutzer im Fenster der Debugmeldung auf die Schaltfläche **Abbrechen** klickt, brechen diese Funktionen sofort ab und geben keinen Wert zurück.

Die [_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) Debuggen-Makros rufen **_CrtDbgReport** Berichte um ihre Debugberichte zu generieren. Die Breitzeichenversionen dieser Makros sowie [_ASSERT-, _ASSERTE](assert-asserte-assert-expr-macros.md), [_RPTW](rpt-rptf-rptw-rptfw-macros.md) und [_RPTFW](rpt-rptf-rptw-rptfw-macros.md), verwenden Sie **_CrtDbgReportW** auf Generieren Sie die Debug-Berichte. Wenn **_CrtDbgReport** oder **_CrtDbgReportW** 1 zurück, sofern die just-in-Time (JIT)-Debuggen aktiviert ist, starten diese Makros des Debuggers.

## <a name="remarks"></a>Hinweise

**_CrtDbgReport** und **_CrtDbgReportW** können den Debugbericht an drei verschiedene Ziele senden: eine debugberichtsdatei, einen Debugmonitor (der Visual Studio-Debugger) oder Fenster einer Debugmeldung. Mit den zwei Konfigurationsfunktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) werden die Ziele für die einzelnen Berichtstypen angegeben. Mithilfe dieser Funktionen können die Berichtsziele für die einzelnen Berichtstypen separat gesteuert werden. Es ist beispielsweise möglich, anzugeben, dass eine *ReportType* von **_CRT_WARN** nur zum Debugmonitor gesendet, während er sich eine *ReportType* von **_CRT_ASSERT** an ein debugmeldungsfenster und einer benutzerdefinierten Berichtsdatei gesendet werden.

**_CrtDbgReportW** ist die Breitzeichen-Version von **_CrtDbgReport**. Alle seine Ausgabe- und Zeichenfolgenparameter sind in Zeichenfolgen mit Breitzeichen. Ansonsten sind sie mit der Einzelbytezeichenversion identisch.

**_CrtDbgReport** und **_CrtDbgReportW** erstellen die benutzermeldung für den Debugbericht und Ersetzen Sie dabei die *Argument*[**n**]-Argumente in der *Format* string "," über die gleichen Regeln die **Printf** oder **Wprintf** Funktionen. Diese Funktionen generiert den Debugbericht und bestimmen das Ziel bzw. die Ziele, basierend auf den aktuellen berichtsmodi und der Datei definiert für *ReportType*. Wenn der Bericht an ein debugmeldungsfenster gesendet wird die *Filename*, **LineNumber**, und *ModuleName* befinden sich in den Informationen im Fenster angezeigt.

Die folgende Tabelle listet die verfügbaren Optionen für den Berichtsmodus oder Modi und die Datei- und das resultierende Verhalten von **_CrtDbgReport** und **_CrtDbgReportW**. Diese Optionen werden als Bitflags in \<crtdbg.h>. definiert.

|Berichtsmodus|Berichtsdatei|**_CrtDbgReport**, **_CrtDbgReportW** Verhalten|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|Nicht zutreffend|Schreibt die Meldung in die Windows-API[OutputDebugString](https://msdn.microsoft.com/library/windows/desktop/aa363362.aspx)|
|**_CRTDBG_MODE_WNDW**|Nicht zutreffend|Ruft die Windows-API [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) zum Erstellen eines Meldungsfelds auf, um die Meldung zusammen mit den Schaltflächen **Abbrechen**, **Wiederholen** und **Ignorieren** anzuzeigen Wenn ein Benutzer klickt **Abbrechen**, **_CrtDbgReport** oder **_CrtDbgReport** sofort abgebrochen. Wenn ein Benutzer auf **Wiederholen** klickt, wird 1 zurückgegeben. Wenn ein Benutzer klickt **ignorieren**, die Ausführung wird fortgeführt und **_CrtDbgReport** und **_CrtDbgReportW** gibt 0 zurück. Wenn ein Fehlerzustand vorliegt, führt das Klicken auf **Ignorieren** häufig zu einem „undefinierten Verhalten“.|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Schreibt eine Meldung an den Benutzer bereitgestellten **BEHANDELN**, mit der Windows [WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile) -API und unterstützt nicht die Gültigkeit des Dateihandles; die Anwendung ist verantwortlich für das Öffnen der Berichtsdatei, und übergeben eine gültige Datei Handle.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|Schreibt eine Meldung an **"stderr"**.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|Schreibt eine Meldung an **"stdout"**.|

Der Bericht entweder an ein Ziel, an zwei oder drei Ziele oder an kein Ziel gesendet werden. Weitere Informationen zum Angeben des Berichtsmodus bzw. der Berichtsmodi und der Berichtsdatei finden Sie unter den Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md). Weitere Informationen zum Verwenden der Debugmakros und der Berichtsfunktionen finden Sie unter [Makros für die Berichterstellung](/visualstudio/debugger/macros-for-reporting).

Wenn Ihre Anwendung mehr Flexibilität als die **_CrtDbgReport** und **_CrtDbgReportW**, Sie können Ihre eigene Berichtsfunktion schreiben und sie in der C-Laufzeitbibliothek-berichterstellung Mechanismus, mit der [_CrtSetReportHook](crtsetreporthook.md) Funktion.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtDbgReport**|\<crtdbg.h>|
|**_CrtDbgReportW**|\<crtdbg.h>|

**_CrtDbgReport** und **_CrtDbgReportW** sind Microsoft-Erweiterungen. Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_crtdbgreport.c
#include <crtdbg.h>

int main(int argc, char *argv[]) {
#ifdef _DEBUG
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);
#endif
}
```

Unter [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2) finden Sie ein Beispiel, wie Sie die Berichtsfunktion ändern können.

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportMode](crtsetreportmode.md)<br/>
[_CrtSetReportFile](crtsetreportfile.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>

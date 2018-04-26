---
title: _CrtDbgReport _CrtDbgReportW | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6857f264618065c6d88a5efa92ee5a19abbc0c67
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

*Definition*<br/>
Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**, und **_CRT_ASSERT**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, in der assert/Bericht aufgetreten ist, oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der assert/Bericht aufgetreten ist, oder **NULL**.

*moduleName*<br/>
Zeiger auf den Namen des Moduls (.exe oder .dll), in dem die Assertion oder der Bericht aufgetreten ist.

*format*<br/>
Zeiger auf die Formatsteuerelementzeichenfolge, mit der die Benutzermeldung erstellt wird.

*Argument*<br/>
Von verwendete optionale ersatzargumente *Format*.

## <a name="return-value"></a>Rückgabewert

Für alle berichtsziele **_CrtDbgReport** und **_CrtDbgReportW** 1, wenn ein Fehler auftritt und 0 zurückgeben, wenn keine Fehler auftreten. Wenn das Berichtsziel jedoch das Fenster einer Debugmeldung ist und der Benutzer auf die Schaltfläche **Wiederholen** klickt, dann geben diese Funktionen 1 zurück. Wenn der Benutzer im Fenster der Debugmeldung auf die Schaltfläche **Abbrechen** klickt, brechen diese Funktionen sofort ab und geben keinen Wert zurück.

Die [_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) Debuggen Makros Aufruf **_CrtDbgReport** Berichte an ihre Debugberichte zu generieren. Die Breitzeichenversionen dieser Makros sowie [_ASSERT-und _ASSERTE](assert-asserte-assert-expr-macros.md), [_RPTW](rpt-rptf-rptw-rptfw-macros.md) und [_RPTFW](rpt-rptf-rptw-rptfw-macros.md), verwenden Sie **_CrtDbgReportW** an Generieren Sie die Debug-Berichte. Wenn **_CrtDbgReport** oder **_CrtDbgReportW** 1 zurück, vorausgesetzt, dass der Just-in-Time (JIT)-Debuggen aktiviert ist, starten diese Makros den Debugger.

## <a name="remarks"></a>Hinweise

**_CrtDbgReport** und **_CrtDbgReportW** können den Debugbericht an drei verschiedene Ziele senden: eine debugberichtsdatei, einen Debugmonitor (Visual Studio-Debugger) oder ein debugmeldungsfenster. Mit den zwei Konfigurationsfunktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) werden die Ziele für die einzelnen Berichtstypen angegeben. Mithilfe dieser Funktionen können die Berichtsziele für die einzelnen Berichtstypen separat gesteuert werden. Es ist beispielsweise möglich, anzugeben, dass eine *Definition* von **_CRT_WARN** werden nur zum Debugmonitor gesendet, während er sich eine *Definition* von **_CRT_ASSERT** an ein debugmeldungsfenster und einer benutzerdefinierten Berichtsdatei gesendet werden.

**_CrtDbgReportW** ist die Breitzeichen-Version des **_CrtDbgReport**. Alle seine Ausgabe- und Zeichenfolgenparameter sind in Zeichenfolgen mit Breitzeichen. Ansonsten sind sie mit der Einzelbytezeichenversion identisch.

**_CrtDbgReport** und **_CrtDbgReportW** erstellen die benutzermeldung für den Debugbericht durch das Ersetzen der *Argument*[**n**]-Argumente der *Format* "string", mit den gleichen Regeln definiert werden, indem Sie die **Printf** oder **"wprintf"** Funktionen. Diese Funktionen generiert den Debugbericht und bestimmen das Ziel bzw. die Ziele, basierend auf den aktuellen berichtsmodi und Datei für definierten *Definition*. Wenn der Bericht an ein debugmeldungsfenster gesendet wird die *Filename*, **LineNumber**, und *"ModuleName"* befinden sich die Informationen im Fenster angezeigt.

Die folgende Tabelle listet die verfügbaren Optionen für den Berichtsmodus bzw. Modi und der Datei sowie das resultierende Verhalten von **_CrtDbgReport** und **_CrtDbgReportW**. Diese Optionen werden als Bitflags in \<crtdbg.h>. definiert.

|Berichtsmodus|Berichtsdatei|**_CrtDbgReport**, **_CrtDbgReportW** Verhalten|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|Nicht zutreffend|Schreibt die Meldung in die Windows-API[OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx)|
|**_CRTDBG_MODE_WNDW**|Nicht zutreffend|Ruft die Windows-API [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) zum Erstellen eines Meldungsfelds auf, um die Meldung zusammen mit den Schaltflächen **Abbrechen**, **Wiederholen** und **Ignorieren** anzuzeigen Wenn ein Benutzer klickt **Abort**, **_CrtDbgReport** oder **_CrtDbgReport** sofort abgebrochen. Wenn ein Benutzer auf **Wiederholen** klickt, wird 1 zurückgegeben. Wenn ein Benutzer klickt **ignorieren**, die Ausführung wird fortgeführt und **_CrtDbgReport** und **_CrtDbgReportW** geben 0 zurück. Wenn ein Fehlerzustand vorliegt, führt das Klicken auf **Ignorieren** häufig zu einem „undefinierten Verhalten“.|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Schreibt eine Meldung in die benutzerdefinierte **BEHANDELN**, mithilfe der Windowsfunktion [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) -API und wird nicht überprüft die Gültigkeit der Dateihandle; die Anwendung ist dafür verantwortlich, für die Berichtsdatei zu öffnen, und übergeben eine gültige Datei behandeln.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|Schreibt eine Meldung in **"stderr"**.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|Schreibt eine Meldung in **"stdout"**.|

Der Bericht entweder an ein Ziel, an zwei oder drei Ziele oder an kein Ziel gesendet werden. Weitere Informationen zum Angeben des Berichtsmodus bzw. der Berichtsmodi und der Berichtsdatei finden Sie unter den Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md). Weitere Informationen zum Verwenden der Debugmakros und der Berichtsfunktionen finden Sie unter [Makros für die Berichterstellung](/visualstudio/debugger/macros-for-reporting).

Wenn Ihre Anwendung mehr Flexibilität als derjenigen benötigt **_CrtDbgReport** und **_CrtDbgReportW**, Sie können Ihre eigene Berichtsfunktion schreiben und sie in der C-Laufzeitbibliothek reporting Mechanismus, mit dem [_CrtSetReportHook](crtsetreporthook.md) Funktion.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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

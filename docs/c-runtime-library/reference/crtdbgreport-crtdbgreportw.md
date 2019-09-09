---
title: _CrtDbgReport, _CrtDbgReportW
ms.date: 11/04/2016
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
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
ms.openlocfilehash: b5579a8996950c5f3e923f67ed2a5e667bb566fa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500003"
---
# <a name="_crtdbgreport-_crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW

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
Berichtstyp: **_CRT_WARN**, **_CRT_ERROR**und **_CRT_ASSERT**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, in der Assert/Report aufgetreten ist, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der Assert/Report aufgetreten ist, oder **null**.

*moduleName*<br/>
Zeiger auf den Namen des Moduls (.exe oder .dll), in dem die Assertion oder der Bericht aufgetreten ist.

*format*<br/>
Zeiger auf die Formatsteuerelementzeichenfolge, mit der die Benutzermeldung erstellt wird.

*argument*<br/>
Optionale Ersatz Argumente, die nach *Format*verwendet werden.

## <a name="return-value"></a>Rückgabewert

Für alle Berichts Ziele geben **_CrtDbgReport** und **_CrtDbgReportW** -1 zurück, wenn ein Fehler auftritt, und 0, wenn keine Fehler auftreten. Wenn das Berichtsziel jedoch das Fenster einer Debugmeldung ist und der Benutzer auf die Schaltfläche **Wiederholen** klickt, dann geben diese Funktionen 1 zurück. Wenn der Benutzer im Fenster der Debugmeldung auf die Schaltfläche **Abbrechen** klickt, brechen diese Funktionen sofort ab und geben keinen Wert zurück.

Die Debug-Makros [_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) rufen **_CrtDbgReport** auf, um Ihre Debugberichte zu generieren. Die breit Zeichen Versionen dieser Makros sowie [_ASSERT, _ASSERTE](assert-asserte-assert-expr-macros.md), [_RPTW](rpt-rptf-rptw-rptfw-macros.md) und [_RPTFW](rpt-rptf-rptw-rptfw-macros.md)verwenden **_CrtDbgReportW** , um Ihre Debugberichte zu generieren. Wenn **_CrtDbgReport** oder **_CrtDbgReportW** 1 zurückgeben, starten diese Makros den Debugger, vorausgesetzt, dass das Just-in-time (JIT)-Debugging aktiviert ist.

## <a name="remarks"></a>Hinweise

**_CrtDbgReport** und **_CrtDbgReportW** können den Debugbericht an drei verschiedene Ziele senden: an eine debugberichtsdatei, einen Debugmonitor (den Visual Studio-Debugger) oder an ein debugmeldungsfenster. Mit den zwei Konfigurationsfunktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) werden die Ziele für die einzelnen Berichtstypen angegeben. Mithilfe dieser Funktionen können die Berichtsziele für die einzelnen Berichtstypen separat gesteuert werden. Es ist z. b. möglich, anzugeben, dass ein Report *Type* von **_CRT_WARN** nur an den Debug-Monitor gesendet werden soll, während ein *reportType* von **_CRT_ASSERT** an ein debugmeldungs Fenster und eine benutzerdefinierte Berichtsdatei gesendet wird.

**_CrtDbgReportW** ist die breit Zeichen Version von **_CrtDbgReport**. Alle seine Ausgabe- und Zeichenfolgenparameter sind in Zeichenfolgen mit Breitzeichen. Ansonsten sind sie mit der Einzelbytezeichenversion identisch.

**_CrtDbgReport** und **_CrtDbgReportW** erstellen Sie die Benutzer Meldung für den Debugbericht, indem Sie die *Argument*[**n**]-Argumente in der *Format* Zeichenfolge ersetzen, indem Sie die gleichen Regeln verwenden, die von **printf** oder **verwendet werden. wprintf** -Funktionen. Diese Funktionen generieren dann den Debugbericht und bestimmen das Ziel bzw. die Ziele basierend auf den aktuellen Berichts Modi und der für Report *Type*definierten Datei. Wenn der Bericht an ein debugmeldungsfenster gesendet wird, sind *Dateiname*, **LineNumber**und *ModuleName* in den im Fenster angezeigten Informationen enthalten.

In der folgenden Tabelle sind die verfügbaren Optionen für den Berichtsmodus bzw. die Modi und die Datei sowie das resultierende Verhalten von **_CrtDbgReport** und **_CrtDbgReportW**aufgeführt. Diese Optionen werden als Bitflags in \<crtdbg.h>. definiert.

|Berichtsmodus|Berichtsdatei|**_CrtDbgReport**, **_CrtDbgReportW** behavior|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|Nicht verfügbar|Schreibt die Meldung in die Windows-API[OutputDebugString](/windows/win32/api/debugapi/nf-debugapi-outputdebugstringw)|
|**_CRTDBG_MODE_WNDW**|Nicht verfügbar|Ruft die Windows-API [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) zum Erstellen eines Meldungsfelds auf, um die Meldung zusammen mit den Schaltflächen **Abbrechen**, **Wiederholen** und **Ignorieren** anzuzeigen Wenn ein Benutzer auf **Abbrechen**klickt, wird " **_CrtDbgReport** " oder " **_CrtDbgReport** " sofort abgebrochen. Wenn ein Benutzer auf **Wiederholen** klickt, wird 1 zurückgegeben. Wenn ein Benutzer auf **ignorieren**klickt, wird die Ausführung fortgesetzt, und **_CrtDbgReport** und **_CrtDbgReportW** geben 0 zurück. Wenn ein Fehlerzustand vorliegt, führt das Klicken auf **Ignorieren** häufig zu einem „undefinierten Verhalten“.|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Schreibt eine Meldung in ein vom Benutzer bereitgestelltes **handle**mithilfe der Windows-API zum Schreiben [von Dateien und](/windows/win32/api/fileapi/nf-fileapi-writefile) überprüft die Gültigkeit des Datei Handles nicht. die Anwendung ist für das Öffnen der Berichtsdatei und das Übergeben eines gültigen Datei Handles verantwortlich.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|Schreibt eine Nachricht in **stderr**.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|Schreibt eine Nachricht in **stdout**.|

Der Bericht entweder an ein Ziel, an zwei oder drei Ziele oder an kein Ziel gesendet werden. Weitere Informationen zum Angeben des Berichtsmodus bzw. der Berichtsmodi und der Berichtsdatei finden Sie unter den Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md). Weitere Informationen zum Verwenden der Debugmakros und der Berichtsfunktionen finden Sie unter [Makros für die Berichterstellung](/visualstudio/debugger/macros-for-reporting).

Wenn Ihre Anwendung mehr Flexibilität benötigt, als von **_CrtDbgReport** und **_CrtDbgReportW**bereitgestellt wird, können Sie Ihre eigene Berichtsfunktion schreiben und Sie mit dem Bericht Erstellungs Mechanismus der C-Lauf Zeit Bibliothek verbinden, indem Sie die [_CrtSetReportHook](crtsetreporthook.md) Funktion.

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

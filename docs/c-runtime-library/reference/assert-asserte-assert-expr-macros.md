---
title: _ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros| Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
- _ASSERTE
- ASSERTE
- _ASSERT
- _ASSERT_EXPR
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8aa84e5c032cefa49ef3a9d21d3bbfc2073d02e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros

Auswerten eines Ausdrucks und erzeugt einen Debugbericht, wenn das Ergebnis ist **"false"** (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
// Typical usage:
_ASSERT_EXPR( booleanExpression, message );
_ASSERT( booleanExpression );
_ASSERTE( booleanExpression );
```

### <a name="parameters"></a>Parameter

*boolescher Ausdruck* ein skalarer Ausdruck (einschließlich zeigerausdrücken), der ungleich Null (True) oder 0 (False) ergibt.

*Nachricht* eine Breite Zeichenfolge als Teil des Berichts angezeigt.

## <a name="remarks"></a>Hinweise

Die **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** Makros stellen Anwendungen einen sauberen und einfachen Mechanismus für die Überprüfung von Annahmen während des Debugprozesses. Sie sind sehr flexibel, da sie nicht in `#ifdef` -Anweisungen eingeschlossen werden müssen, um ihren Aufruf in der Verkaufsversion einer Anwendung zu verhindern. Diese Flexibilität wird mithilfe des [_DEBUG](../../c-runtime-library/debug.md) -Makros erreicht. **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** sind nur verfügbar, wenn **_DEBUG** zum Zeitpunkt der Kompilierung definiert ist. Wenn **_DEBUG** ist nicht definiert ist, werden Aufrufe dieser Makros während der vorverarbeitung entfernt.

**_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** bewerten ihre *boolescher* Argument und wenn das Ergebnis ist **"false"**(0), auch eine diagnosemeldung aus und rufen gedruckt [_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) um einen Debugbericht zu generieren. Die **_ASSERT** -Makro gibt eine einfache diagnosemeldung **_ASSERTE** enthält eine Zeichenfolgendarstellung des fehlerausdrucks in der Nachricht und **_ASSERT_EXPR** enthält die *Nachricht* Zeichenfolge in die diagnosemeldung. Diese Makros führen keine Aktion beim *boolescher* ungleich null ergibt.

**_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** Aufrufen **_CrtDbgReportW**, wodurch Ausgabewerte in Breitzeichen sein. **_ASSERTE** ordnungsgemäß gibt Unicode-Zeichen in *boolescher* und **_ASSERT_EXPR** gibt Unicode-Zeichen in *Nachricht*.

Da die **_ASSERTE** Makro gibt den fehlerausdruck und **_ASSERT_EXPR** können Sie eine Nachricht in der generierte Bericht angeben, sie ermöglichen Benutzern, das Problem zu identifizieren, ohne auf die Quellcode der Anwendung. Allerdings ein Nachteil ist, dass jeder *Nachricht* von gedruckte **_ASSERT_EXPR** und jeder Ausdruck ausgewertet, indem **_ASSERTE** ist in der Ausgabe (Debugversion) enthalten die Datei der Anwendung als Zeichenfolgenkonstante. Aus diesem Grund, wenn eine große Anzahl der Aufrufe von **_ASSERT_EXPR** oder **_ASSERTE**, diesen Ausdrücken können die Größe Ihrer Ausgabedatei erheblich erhöhen.

Sofern Sie es nicht mithilfe der Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) anders festlegen, werden Meldungen in einem Popupdialogfeld angezeigt, entsprechend der Einstellung:

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_CrtDbgReportW** generiert den Debugbericht und bestimmt sein Ziel oder die Ziele, basierend auf den aktuellen Berichtsmodus oder die Modi und die Datei, die definiert, die für die **_CRT_ASSERT** Berichtstyp. Standardmäßig werden Assertionsfehler und Fehler an ein Debugmeldungsfenster geleitet. Die Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) werden verwendet, um die Ziele für jeden Berichtstyp zu definieren.

Wenn das Ziel ein debugmeldungsfenster und der Benutzer klickt der **wiederholen** Schaltfläche **_CrtDbgReportW** gibt 1 zurück, verursacht die **_ASSERT_EXPR**, **_ ASSERT** und **_ASSERTE** Makros, um den Debugger zu starten, vorausgesetzt, dass der Just-in-Time (JIT)-Debuggen aktiviert ist.

Weitere Informationen zum Berichtstellungsverfahren finden Sie bei der Funktion [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md). Weitere Informationen zum Beheben von Assertionsfehlern und zum Verwenden dieser Makros als Behandlungsmechanismus für Debugfehler finden Sie unter [Verwenden von Makros zur Überprüfung und Berichterstellung](/visualstudio/debugger/macros-for-reporting).

Zusätzlich zu den **_ASSERT** Makros, die [assert](assert-macro-assert-wassert.md) Makro kann zum Prüfen von Programmlogik verwendet werden. Dieses Makro steht sowohl in der Debug- als auch in der endgültigen Version der Bibliotheken zur Verfügung. Die Debugmakros [_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) sind ebenfalls für die Erstellung eines Debugberichts verfügbar, werten aber keinen Ausdruck aus. Die **_RPT** -Makros erstellen einen einfachen Bericht. Die **_RPTF** Makros umfassen die, in das Berichtsmakro aufgerufen wurde, und die Zeilennummer an, in den generierten Bericht. Breitzeichenversionen dieser Makros sind verfügbar (**_RPTW**, **_RPTFW**). Die Breitzeichenversionen sind mit den Versionen mit schmalen Zeichen identisch, mit dem Unterschied, dass für alle Zeichenfolgenparameter und Ausgaben Breitzeichen-Zeichenfolgen verwendet werden.

Obwohl **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** Makros sind und verwenden möchten, einschließlich \<"CRTDBG.h" >, die Anwendung muss mit einem Debugbuild verknüpfen Version der C-Laufzeitbibliothek beim **_DEBUG** definiert ist, da diese Makros andere Laufzeitfunktionen aufrufen.

## <a name="requirements"></a>Anforderungen

|Makro|Erforderlicher Header|
|-----------|---------------------|
|**_ASSERT_EXPR**, **_ASSERT**, **_ASSERTE**|\<crtdbg.h>|

## <a name="example"></a>Beispiel

In diesem Programm Aufrufe von der **_ASSERT** und **_ASSERTE** Makros zum Testen der Bedingung `string1 == string2`. Wenn bei der Bedingung ein Fehler auftritt, geben diese Makros eine Diagnosemeldung aus. Die **_RPT** und **_RPTF** Gruppe von Makros ist auch an diesem Programm ausgeführt, als Alternative zu den **Printf** Funktion.

```C
// crt_ASSERT_macro.c
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug
//
// This program uses the _ASSERT and _ASSERTE debugging macros.
//

#include <stdio.h>
#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

int main()
{
   char *p1, *p2;

   // The Reporting Mode and File must be specified
   // before generating a debug report via an assert
   // or report macro.
   // This program sends all report types to STDOUT.
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);

   // Allocate and assign the pointer variables.
   p1 = (char *)malloc(10);
   strcpy_s(p1, 10, "I am p1");
   p2 = (char *)malloc(10);
   strcpy_s(p2, 10, "I am p2");

   // Use the report macros as a debugging
   // warning mechanism, similar to printf.
   // Use the assert macros to check if the
   // p1 and p2 variables are equivalent.
   // If the expression fails, _ASSERTE will
   // include a string representation of the
   // failed expression in the report.
   // _ASSERT does not include the
   // expression in the generated report.
   _RPT0(_CRT_WARN,
       "Use the assert macros to evaluate the expression p1 == p2.\n");
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);
   _ASSERT(p1 == p2);

   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",
          p1, p2);
   _ASSERTE(p1 == p2);

   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);

   free(p2);
   free(p1);

   return 0;
}
```

```Output
Use the assert macros to evaluate the expression p1 == p2.
crt_ASSERT_macro.c(54) :
Will _ASSERT find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(55) : Assertion failed!
crt_ASSERT_macro.c(58) :

Will _ASSERTE find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2
'I am p1' != 'I am p2'
```

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[assert Macro, _assert, _wassert](assert-macro-assert-wassert.md)<br/>
[_RPT, _RPTF, _RPTW, _RPTFW Macros](rpt-rptf-rptw-rptfw-macros.md)<br/>

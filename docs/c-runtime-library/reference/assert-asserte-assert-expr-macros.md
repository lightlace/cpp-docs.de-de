---
title: _ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros
ms.date: 11/04/2016
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
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
ms.openlocfilehash: d2d83c3afa8e22c1f75480fe2afefa8bf68be858
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598457"
---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros

Wertet einen Ausdruck ein, und erzeugt einen Debugbericht, wenn das Ergebnis ist **"false"** (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
// Typical usage:
_ASSERT_EXPR( booleanExpression, message );
_ASSERT( booleanExpression );
_ASSERTE( booleanExpression );
```

### <a name="parameters"></a>Parameter

*boolescher Ausdruck*<br/>
Ein skalarer Ausdruck (einschließlich Zeigerausdrücken) der zu ungleich null (true) oder „0“ (false) ausgewertet wird.

*message*<br/>
Eine Breitzeichenfolge, die als Teil des Berichts angezeigt werden soll.

## <a name="remarks"></a>Hinweise

Die **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** Makros stellen Anwendungen einen sauberen und einfachen Mechanismus für die Überprüfung von Annahmen während des Debuggens. Sie sind sehr flexibel, da sie nicht in `#ifdef` -Anweisungen eingeschlossen werden müssen, um ihren Aufruf in der Verkaufsversion einer Anwendung zu verhindern. Diese Flexibilität wird mithilfe des [_DEBUG](../../c-runtime-library/debug.md) -Makros erreicht. **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** sind nur verfügbar, wenn **_DEBUG** zum Zeitpunkt der Kompilierung definiert ist. Wenn **_DEBUG** ist nicht definiert ist, werden Aufrufe dieser Makros während der vorverarbeitung entfernt.

**_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** bewerten ihre *boolescher Ausdruck* Argument und wenn das Ergebnis ist **"false"**(0), sie zu drucken, eine diagnosemeldung aus und rufen [_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) um einen Debugbericht zu generieren. Die **_ASSERT** -Makro gibt eine einfache diagnosemeldung **_ASSERTE** enthält eine Zeichenfolgendarstellung des fehlerausdrucks in der Nachricht und **_ASSERT_EXPR** enthält die *Nachricht* Zeichenfolge in die diagnosemeldung. Diese Makros führen keine Aktion beim *boolescher Ausdruck* ungleich null ergibt.

**_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** Aufrufen **_CrtDbgReportW**, die Ausgabewerte in Breitzeichen bewirkt. **_ASSERTE** ordnungsgemäß gibt Unicode-Zeichen in *boolescher Ausdruck* und **_ASSERT_EXPR** gibt Unicode-Zeichen in *Nachricht*.

Da die **_ASSERTE** Makro gibt den fehlerausdruck und **_ASSERT_EXPR** können Sie eine Nachricht im generierten Bericht angeben, sie ermöglichen es Benutzern, um das Problem zu identifizieren, ohne auf die Quellcode der Anwendung. Jedoch ein Nachteil ist, dass jede *Nachricht* ausgegebene **_ASSERT_EXPR** und jeder Ausdruck ausgewertet, indem **_ASSERTE** befindet sich in der Ausgabe (Debugversion) die Datei der Anwendung als eine Zeichenfolgenkonstante. Aus diesem Grund werden, wenn eine große Anzahl von Aufrufe von **_ASSERT_EXPR** oder **_ASSERTE**, diese Ausdrücke können die Größe Ihrer Ausgabedatei stark erhöhen.

Sofern Sie es nicht mithilfe der Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) anders festlegen, werden Meldungen in einem Popupdialogfeld angezeigt, entsprechend der Einstellung:

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_CrtDbgReportW** generiert den Debugbericht und bestimmt sein Ziel oder seine Ziele, basierend auf den aktuellen Berichtsmodus oder den Modi und die Datei, die für definiert die **_CRT_ASSERT** Berichtstyp. Standardmäßig werden Assertionsfehler und Fehler an ein Debugmeldungsfenster geleitet. Die Funktionen [_CrtSetReportMode](crtsetreportmode.md) und [_CrtSetReportFile](crtsetreportfile.md) werden verwendet, um das Ziel für jeden Berichtstyp zu definieren.

Wenn das Ziel ein debugmeldungsfenster und dem Benutzer klickt der **wiederholen** Schaltfläche **_CrtDbgReportW** gibt 1 zurück, verursacht die **_ASSERT_EXPR**, **_ ASSERT** und **_ASSERTE** Makros den Debugger zu starten, vorausgesetzt, dass die just-in-Time (JIT)-Debuggen aktiviert ist.

Weitere Informationen zum Berichtstellungsverfahren finden Sie bei der Funktion [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) . Weitere Informationen zum Beheben von Assertionsfehlern und zum Verwenden dieser Makros als Behandlungsmechanismus für Debugfehler finden Sie unter [Verwenden von Makros zur Überprüfung und Berichterstellung](/visualstudio/debugger/macros-for-reporting).

Zusätzlich zu den **_ASSERT** Makros, die [assert](assert-macro-assert-wassert.md) -Makro zum Prüfen von Programmlogik verwendet werden kann. Dieses Makro steht sowohl in der Debug- als auch in der endgültigen Version der Bibliotheken zur Verfügung. Die Debugmakros [_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) sind ebenfalls für die Erstellung eines Debugberichts verfügbar, werten aber keinen Ausdruck aus. Die **_RPT** -Makros erstellen einen einfachen Bericht. Die **_RPTF** Makros sind die Quell- und die Zeilennummer Anzahl, in denen das Berichtsmakro aufgerufen wurde, im generierten Bericht. Die Breitzeichenversionen dieser Makros sind verfügbar (**_RPTW**, **_RPTFW**). Die Breitzeichenversionen sind mit den Versionen mit schmalen Zeichen identisch, mit dem Unterschied, dass für alle Zeichenfolgenparameter und Ausgaben Breitzeichen-Zeichenfolgen verwendet werden.

Obwohl **_ASSERT_EXPR**, **_ASSERT** und **_ASSERTE** Makros sind und sind verfügbar, einschließlich \<crtdbg.h >, die Anwendung muss eine Verknüpfung mit einer Debugversion Version der C-Laufzeitbibliothek beim **_DEBUG** definiert ist, da diese Makros andere Laufzeitfunktionen aufrufen.

## <a name="requirements"></a>Anforderungen

|Makro|Erforderlicher Header|
|-----------|---------------------|
|**_ASSERT_EXPR**, **_ASSERT**, **_ASSERTE**|\<crtdbg.h>|

## <a name="example"></a>Beispiel

In diesem Programm Aufrufe von der **_ASSERT** und **_ASSERTE** Makros zum Testen der Bedingung `string1 == string2`. Wenn bei der Bedingung ein Fehler auftritt, geben diese Makros eine Diagnosemeldung aus. Die **_RPT** und **_RPTF** Gruppe von Makros ist auch in diesem Programm ausgeführt, als Alternative zu den **Printf** Funktion.

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

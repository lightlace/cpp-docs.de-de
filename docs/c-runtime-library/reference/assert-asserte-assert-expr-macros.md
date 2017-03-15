---
title: _ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 99698cf158118a876a3bb78edaaa52f2b9177d0a
ms.lasthandoff: 02/24/2017

---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT-, _ASSERTE-, _ASSERT_EXPR-Makros
Wertet einen Ausdruck aus und erzeugt einen Debugbericht, wenn das Ergebnis `False` lautet (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
_ASSERT_EXPR(  
   booleanExpression,  
   message  
);  
_ASSERT(   
   booleanExpression   
);  
_ASSERTE(   
   booleanExpression   
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `booleanExpression`  
 Ein skalarer Ausdruck (einschließlich Zeigerausdrücken) der zu ungleich null (true) oder „0“ (false) ausgewertet wird.  
  
 `message`  
 Eine Breitzeichenfolge, die als Teil des Berichts angezeigt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Die Makros `_ASSERT_EXPR`, `_ASSERT` und `_ASSERTE` stellen Anwendungen einen sauberen und einfachen Mechanismus für die Überprüfung von Annahmen während des Debugvorgangs zur Verfügung. Sie sind sehr flexibel, da sie nicht in `#ifdef` -Anweisungen eingeschlossen werden müssen, um ihren Aufruf in der Verkaufsversion einer Anwendung zu verhindern. Diese Flexibilität wird mithilfe des [_DEBUG](../../c-runtime-library/debug.md) -Makros erreicht. `_ASSERT_EXPR`, `_ASSERT` und `_ASSERTE` sind nur verfügbar, wenn `_DEBUG` zur Kompilierzeit definiert ist. Wenn `_DEBUG` nicht definiert ist, werden die Aufrufe dieser Makros während der Vorabverarbeitung entfernt.  
  
 `_ASSERT_EXPR`, `_ASSERT` und `_ASSERTE` werten ihr `booleanExpression`-Argument aus. Wenn das Ergebnis `false` (0) ist, geben sie eine Diagnosemeldung aus und rufen [_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) auf, um einen Debugbericht zu generieren. Das `_ASSERT` -Makro gibt eine einfache Diagnosemeldung aus,  `_ASSERTE` nimmt eine Zeichenfolgendarstellung des Fehlerausdrucks in die Nachricht mit auf, und `_ASSERT_EXPR` schließt die `message` -Zeichenfolge in die Diagnosemeldung ein. Diese Makros führen keine Aktion aus, wenn `booleanExpression` zu einem anderen Wert als null ausgewertet wird.  
  
 `_ASSERT_EXPR`, `_ASSERT` und `_ASSERTE` rufen `_CrtDbgReportW` auf, was die Ausgabe der Ausgabewerte in Breitzeichen bewirkt. `_ASSERTE` gibt Unicode-Zeichen in `booleanExpression` ordnungsgemäß aus, und `_ASSERT_EXPR` gibt Unicode-Zeichen in `message` aus.  
  
 Da das `_ASSERTE` -Makro den Fehlerausdruck angibt und `_ASSERT_EXPR` das Angeben einer Nachricht im erstellten Bericht ermöglicht, können Benutzer mit ihrer Hilfe das Problem identifizieren, ohne auf den Quellcode der Anwendung zurückgreifen zu müssen. Es besteht jedoch insofern ein Nachteil, als dass jede von `message` ausgegebene `_ASSERT_EXPR` und jeder von `_ASSERTE` ausgewertete Ausdruck als Zeichenfolgenkonstante in die Ausgabedatei (Debugversion) Ihrer Anwendung aufgenommen wird. Wenn daher viele Aufrufe von `_ASSERT_EXPR` oder `_ASSERTE`erfolgen, können diese Ausdrücke die Größe ihrer Ausgabedatei stark anwachsen lassen.  
  
 Sofern Sie es nicht mithilfe der Funktionen [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) und [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) anders festlegen, werden Meldungen in einem Popupdialogfeld angezeigt, entsprechend der Einstellung:  
  
`_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);`  
  
 `_CrtDbgReportW` generiert den Debugbericht und bestimmt sein Ziel oder seine Ziele, basierend auf dem aktuellen Berichtsmodus oder den aktuellen Berichtsmodi und der für den `_CRT_ASSERT`-Berichtstyp definierten Datei. Standardmäßig werden Assertionsfehler und Fehler an ein Debugmeldungsfenster geleitet. Die Funktionen [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) und [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) werden verwendet, um das Ziel für jeden Berichtstyp zu definieren.  
  
 Wenn das Ziel ein Debugmeldungsfenster ist und der Benutzer auf die Schaltfläche **Wiederholen** klickt, gibt `_CrtDbgReportW` „1“ zurück, was dazu führt, dass die Makros `_ASSERT_EXPR`, `_ASSERT` und `_ASSERTE` den Debugger starten, vorausgesetzt, dass JIT-Debuggen (Just-In-Time) aktiviert ist.  
  
 Weitere Informationen zum Berichtstellungsverfahren finden Sie bei der Funktion [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md). Weitere Informationen zum Beheben von Assertionsfehlern und zum Verwenden dieser Makros als Behandlungsmechanismus für Debugfehler finden Sie unter [Verwenden von Makros zur Überprüfung und Berichterstellung](/visualstudio/debugger/macros-for-reporting).  
  
 Über die `_ASSERT`-Makros hinaus kann das [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)-Makro zum Prüfen von Programmlogik verwendet werden. Dieses Makro steht sowohl in der Debug- als auch in der endgültigen Version der Bibliotheken zur Verfügung. Die Debugmakros [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) sind ebenfalls für die Erstellung eines Debugberichts verfügbar, werten aber keinen Ausdruck aus. Die `_RPT` -Makros erstellen einen einfachen Bericht. Die `_RPTF` -Makros schließen die Quelldatei und die Zeilennummer, in der das Berichtsmakro aufgerufen wurde, in den generierten Bericht ein. Breitzeichenversionen dieser Makros sind verfügbar (`_RPTWn`, `_RPTFWn`). Die Breitzeichenversionen sind mit den Versionen mit schmalen Zeichen identisch, mit dem Unterschied, dass für alle Zeichenfolgenparameter und Ausgaben Breitzeichen-Zeichenfolgen verwendet werden.  
  
 Obwohl `_ASSERT_EXPR`, `_ASSERT` und `_ASSERTE` Makros sind und durch Einschließen von \<<crtdbg.h> verfügbar gemacht werden, muss die Anwendung mit einer Debugversion der C-Laufzeitbibliothek gelinkt werden, wenn `_DEBUG` definiert ist, da diese Makros andere Laufzeitfunktionen aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Makro|Erforderlicher Header|  
|-----------|---------------------|  
|`_ASSERT_EXPR`,                  `_ASSERT`, `_ASSERTE`|\<crtdbg.h>|  
  
## <a name="example"></a>Beispiel  
 In diesem Programm werden Aufrufe der Makros `_ASSERT` und `_ASSERTE` vorgenommen, um die Bedingung `string1 == string2`zu testen. Wenn bei der Bedingung ein Fehler auftritt, geben diese Makros eine Diagnosemeldung aus. Die Makrogruppe `_RPTn` und `_RPTFn` wird in diesem Programm ebenfalls ausgeführt, als Alternative zur Funktion `printf` .  
  
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
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [assert-Makro, _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [_RPT-, _RPTF-, _RPTW- und _RPTFW-Makros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)

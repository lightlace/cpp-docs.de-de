---
title: _RPT-, _RPTF-, _RPTW- und _RPTFW-Makros | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
- RPT3
- RPTF4
- _RPT4
- RPT1
- _RPTF0
- RPTF3
- _RPTF4
- RPTF1
- RPT4
- _RPT1
- _RPT0
- RPT0
- _RPTF2
- RPTF0
- _RPT3
- _RPT2
- _RPTF3
- RPT2
- _RPTF1
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _RPTW3 macro
- _RPT0 macro
- RPTW4 macro
- _RPTF3 macro
- _RPTW4 macro
- RPTF4 macro
- RPTFW2 macro
- RPTW macros
- RPT1 macro
- _RPTF macros
- RPTFW3 macro
- _RPTW0 macro
- _RPTF0 macro
- macros, debugging with
- _RPTW2 macro
- RPTF3 macro
- RPT3 macro
- RPT0 macro
- _RPT macros
- RPTW3 macro
- _RPTFW macros
- debug reporting macros
- RPTF macros
- RPT macros
- _RPTW macros
- RPTF2 macro
- _RPTF1 macro
- _RPT1 macro
- _RPT4 macro
- _RPTFW2 macro
- _RPTFW1 macro
- RPTF0 macro
- _RPT2 macro
- RPTFW macros
- _RPTW1 macro
- _RPTFW0 macro
- RPT4 macro
- _RPT3 macro
- _RPTFW3 macro
- _RPTF4 macro
- _RPTFW4 macro
- _RPTF2 macro
- RPTW0 macro
- RPTFW4 macro
- RPTFW0 macro
- RPTW2 macro
- RPTF1 macro
- RPT2 macro
- RPTFW1 macro
- RPTW1 macro
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ca0ae546af28c342db2e452bec432ced0437738a
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT-, _RPTF-, _RPTW- und _RPTFW-Makros
Verfolgt den Status einer Anwendung durch Generieren eines Debugberichts (nur in der Debugversion). Beachten Sie, dass *n* die Anzahl der Argumente in `args` angibt und 0, 1, 2, 3, 4 oder 5 sein kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      _RPT  
      n  
      (  
   reportType,  
   format,  
...[args]  
);  
_RPTFn(  
   reportType,  
   format,  
   [args]  
);  
_RPTWn(  
   reportType,  
   format   
   [args]  
);  
_RPTFWn(  
   reportType,  
   format   
   [args]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `reportType`  
 Berichtstyp: `_CRT_WARN`, `_CRT_ERROR` oder `_CRT_ASSERT`.  
  
 `format`  
 Formatsteuerelementzeichenfolge, mit der die Benutzermeldung erstellt wird.  
  
 `args`  
 Von `format` verwendete optionale Ersatzargumente.  
  
## <a name="remarks"></a>Hinweise  
 Nehmen Sie alle diese Makros den `reportType` und `format` Parameter. Darüber hinaus können sie auch bis zu vier zusätzliche Argumente annehmen, gekennzeichnet durch die zum Makronamen angefügte Zahl. Beispielsweise nehmen `_RPT0` und `_RPTF0` keine zusätzlichen Argumente, `_RPT1` und `_RPTF1` nehmen `arg1`, `_RPT2` und `_RPTF2` nehmen `arg1` und `arg2` und so weiter.  
  
 Die `_RPT`- und `_RPTF`-Makros sind ähnlich wie die [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)-Funktion, da sie während des Debuggens Fortschritt einer Anwendung verwendet werden können. Dies Makros sind flexibler als `printf`, da sie nicht in `#ifdef`-Anweisungen eingeschlossen werden müssen, um ihren Aufruf in der Verkaufsversion einer Anwendung zu verhindern. Diese Flexibilität wird erreicht, indem das [_DEBUG](../../c-runtime-library/debug.md)-Makro verwendet wird; `_RPT`- und `_RPTF`-Makros sind nur verfügbar, wenn das `_DEBUG`-Flag definiert wird. Wenn `_DEBUG` nicht definiert ist, werden die Aufrufe dieser Makros während der Vorabverarbeitung entfernt.  
  
 Die `_RPTW`- und `_RPTFW`-Makros sind Breitzeichenversionen dieser Makros. Sie verhalten sich wie `wprintf` und nehmen Argumente mit Breitzeichen entgegen.  
  
 Die `_RPT`-Makros rufen die [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)-Funktion auf, um einen Debugbericht mit einer Benutzermeldung zu erstellen. Die `_RPTW`-Makros rufen die `_CrtDbgReportW`-Funktion auf, um den gleichen Berichts mit Breitzeichen zu generieren. Die `_RPTF`- und `_RPTFW`-Makros erstellen einen Debugbericht mit der Quelldatei und der Zeilennummer, in denen das Berichtsmakro zusätzlich zur Benutzermeldung aufgerufen wurde. Die Benutzermeldung wird erstellt, indem die `arg`[*n*]-Argumente in der `format`-Zeichenfolge ersetzt werden und dabei die gleichen Regeln verwendet werden, die auch von der [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)-Funktion definiert sind.  
  
 `_CrtDbgReport` oder `_CrtDbgReportW` generiert den Debugbericht und bestimmt seine Ziele, basierend auf den aktuellen Berichtsmodi und der für `reportType` definierten Datei. Die Funktionen [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) und [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) werden verwendet, um die Ziele für jeden Berichtstyp zu definieren.  
  
 Wenn ein `_RPT`-Makro aufgerufen wird und weder `_CrtSetReportMode` noch `_CrtSetReportFile` aufgerufen wurden, werden Nachrichten wie folgt angezeigt.  
  
|Berichtstyp|Ausgabeziel|  
|-----------------|------------------------|  
|`_CRT_WARN`|Warnung wird nicht angezeigt.|  
|`_CRT_ERROR`|Ein Popupfenster. So als ob `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` angegeben worden wäre.|  
|`_CRT_ASSERT`|Wie in `_CRT_ERROR`.|  
  
 Wenn das Ziel ein Debugmeldungsfenster ist und der Benutzer die Schaltfläche **Wiederholen** auswählt, geben `_CrtDbgReport` oder `_CrtDbgReportW` 1 zurück, was dazu führt, dass diese Makros den Debugger starten, vorausgesetzt, dass JIT-Debuggen (Just-In-Time) aktiviert ist. Weitere Informationen zum Verwenden dieser Makros als Behandlungsmechanismus für Debugfehler finden Sie unter [Verwenden von Makros zur Überprüfung und Berichterstellung](/visualstudio/debugger/macros-for-reporting).  
  
 Zwei andere Makros sind vorhanden, die einen Debugbericht generieren. Das [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)-Makro generiert einen Bericht, jedoch nur, wenn das Ausdrucksargument zu FALSE ausgewertet wird. [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) ist genau wie `_ASSERT`, schließt jedoch den fehlgeschlagenen Ausdruck im generierten Bericht ein.  
  
## <a name="requirements"></a>Anforderungen  
  
|Makro|Erforderlicher Header|  
|-----------|---------------------|  
|`_RPT`-Makros|\<crtdbg.h>|  
|`_RPTF`-Makros|\<crtdbg.h>|  
|`_RPTW`-Makros|\<crtdbg.h>|  
|`_RPTFW`-Makros|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
 Obwohl sie Makros sind und durch Einschließen von <crtdbg.h> verfügbar gemacht werden, muss die Anwendung mit einer Debugversion der C-Laufzeitbibliothek verlinkt werden, da diese Makros andere Laufzeitfunktionen aufrufen.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie im Thema [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)

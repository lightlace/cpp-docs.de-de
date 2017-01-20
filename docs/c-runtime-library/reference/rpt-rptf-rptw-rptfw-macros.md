---
title: "_RPT-, _RPTF-, _RPTW- und _RPTFW-Makros"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "RPT3"
  - "RPTF4"
  - "_RPT4"
  - "RPT1"
  - "_RPTF0"
  - "RPTF3"
  - "_RPTF4"
  - "RPTF1"
  - "RPT4"
  - "_RPT1"
  - "_RPT0"
  - "RPT0"
  - "_RPTF2"
  - "RPTF0"
  - "_RPT3"
  - "_RPT2"
  - "_RPTF3"
  - "RPT2"
  - "_RPTF1"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Debuggen [CRT], Verwenden von Makros"
  - "_RPTW3-Makro"
  - "_RPT0-Makro"
  - "RPTW4-Makro"
  - "_RPTF3-Makro"
  - "_RPTW4-Makro"
  - "RPTF4-Makro"
  - "RPTFW2-Makro"
  - "RPTW-Makros"
  - "RPT1-Makro"
  - "_RPTF-Makros"
  - "RPTFW3-Makro"
  - "_RPTW0-Makro"
  - "_RPTF0-Makro"
  - "Makros, Debuggen mit"
  - "_RPTW2-Makro"
  - "RPTF3-Makro"
  - "RPT3-Makro"
  - "RPT0-Makro"
  - "_RPT-Makros"
  - "RPTW3-Makro"
  - "_RPTFW-Funktion"
  - "Debugberichterstellung von Makros"
  - "RPTF-Makros"
  - "RPT-Makros"
  - "_RPTW-Makros"
  - "RPTF2-Makro"
  - "_RPTF1-Makro"
  - "_RPT1-Makro"
  - "_RPT4-Makro"
  - "_RPTFW2-Makro"
  - "_RPTFW1-Makro"
  - "RPTF0-Makro"
  - "_RPT2-Makro"
  - "RPTFW-Makros"
  - "_RPTW1-Makro"
  - "_RPTFW0-Makro"
  - "RPT4-Makro"
  - "_RPT3-Makro"
  - "_RPTFW3-Makro"
  - "_RPTF4-Makro"
  - "_RPTFW4-Makro"
  - "_RPTF2-Makro"
  - "RPTW0-Makro"
  - "RPTFW4-Makro"
  - "RPTFW0-Makro"
  - "RPTW2-Makro"
  - "RPTF1-Makro"
  - "RPT2-Makro"
  - "RPTFW1-Makro"
  - "RPTW1-Makro"
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# _RPT-, _RPTF-, _RPTW- und _RPTFW-Makros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verfolgt den Status einer Anwendung durch Generieren eines Debugberichts Debugversion \(nur\).  Beachten Sie, dass *n* die Anzahl der Argumente in `args` angibt und 0, 1, 2, 3, 4 oder 5. sein kann.  
  
## Syntax  
  
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
  
#### Parameter  
 `reportType`  
 Berichtstyp: `_CRT_WARN`, `_CRT_ERROR` oder `_CRT_ASSERT`.  
  
 `format`  
 Formatsteuerzeichenfolge verwendet, um die Benutzermeldung zu erstellen.  
  
 `args`  
 Ersatzargumente von `format` verwendet.  
  
## Hinweise  
 Diese Makros nehmen die Parameter `reportType` und `format`.  Darüber hinaus nehmen sie auch für vier weitere Argumente auf, durch die Zahl, die dem Makronamen angefügt wird.  Angenommen `_RPT0` und `_RPTF0` keine zusätzlichen Argumente, `_RPT1` und `_RPTF1` nehmen `arg1`, `_RPT2` und `_RPTF2` nehmen `arg1` und `arg2`, z. B.  
  
 Die Makros `_RPT` und `_RPTF` sind für die [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\-Funktion ähnlich, da sie verwendet werden können, um den Fortschritt einer Anwendung während des Debuggingsprozesses nachzuverfolgen.  Dies sind jedoch Makros flexibler als `printf`, da sie nicht erforderlich ist, in `#ifdef`\-Anweisungen eingeschlossen werden, um sie in einem Releasebuild einer Anwendung aufgerufen werden.  Diese Flexibilität wird erreicht, indem das [\_DEBUG](../../c-runtime-library/debug.md)\-Makro verwendet; die Makros `_RPT` und `_RPTF` sind nur verfügbar, wenn das Flag `_DEBUG` definiert wird.  Ist `_DEBUG` nicht definiert wird, werden Aufrufe dieser Makros während des Präprozessorlaufs entfernt.  
  
 Die Makros `_RPTW` und `_RPTFW` sind Breitzeichenversionen dieser Makros.  Sie sind z `wprintf` und nehmen Breitzeichen\-Zeichenfolgen als Argumente.  
  
 Die Makros `_RPT` rufen die [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)\-Funktion auf, um ein Debugbericht mit einer Benutzermeldung zu generieren.  Die Makros `_RPTW` rufen die Funktion `_CrtDbgReportW` auf, um den Bericht mit Breitzeichen zu generieren.  Die Makros `_RPTF` und `_RPTFW` erstellen ein Debugbericht mit der Quelldatei sowie die Zeilennummer, in der das Berichtsmakro aufgerufen wurde, sowie die Benutzermeldung.  Die Benutzermeldung wird erstellt, indem die Argumente `arg`\[*n*\] `format` in die Zeichenfolge, mit der gleichen Regeln ersetzt, die durch die [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\-Funktion definiert werden.  
  
 `_CrtDbgReport` oder `_CrtDbgReportW` generiert den Debugbericht und bestimmt die Ziele auf Grundlage der aktuellen Berichtsmodi und die Regelsatzdatei, die für `reportType` definiert werden.  Die Funktionen [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) und [\_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) werden verwendet, um die Ziele für jeden Berichtstyp zu definieren.  
  
 Wenn ein `_RPT`\-Makro aufgerufen wird und weder `_CrtSetReportMode` noch `_CrtSetReportFile` aufgerufen wurde, werden Meldungen wie folgt angezeigt.  
  
|Berichtstyp|Ausgabeziel|  
|-----------------|-----------------|  
|`_CRT_WARN`|Warnungstext wird nicht angezeigt.|  
|`_CRT_ERROR`|Ein Popupfenster.  Gleiche, als ob `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` angegeben wurde.|  
|`_CRT_ASSERT`|Dieselbe Bedeutung wie `_CRT_ERROR`.|  
  
 Wenn das Ziel ein debuggensmeldungsfenster wird und der Benutzer die Schaltfläche auswählt **Wiederholen**, gibt `_CrtDbgReport``_CrtDbgReportW` oder 1 zurück und führt diese Makros, den Debugger starten, vorausgesetzt, dass ein Just\-In\-Time \(JIT\)\- \- Debuggen aktiviert ist.  Weitere Informationen zur Verwendung dieser Makros als Debuggingsfehlerbehandlungsmechanismus, finden Sie unter [Verwenden von Makros für Überprüfungen und Berichterstellung](../Topic/Macros%20for%20Reporting.md).  
  
 Zwei andere Makros vorhanden sind, die ein Debugbericht generieren.  [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) Das Makro generiert einen Bericht, jedoch nur, wenn sein Ausdrucksargument zu FALSE ergibt.  [\_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) entspricht genau wie `_ASSERT`, aber enthält der fehlgeschlagenen Ausdruck im generierten Bericht.  
  
## Anforderungen  
  
|Makro|Erforderlicher Header|  
|-----------|---------------------------|  
|Makros `_RPT`|\<crtdbg.h\>|  
|Makros `_RPTF`|\<crtdbg.h\>|  
|Makros `_RPTW`|\<crtdbg.h\>|  
|Makros `_RPTFW`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
 Obwohl diese Makros sind und erhalten werden, indem sie Crtdbg.h enthalten, muss die Anwendung mit einer der Debugbibliotheken verknüpfen, da diese Makros andere Laufzeitfunktionen aufrufen.  
  
## Beispiel  
 Siehe das Beispiel im Thema [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)
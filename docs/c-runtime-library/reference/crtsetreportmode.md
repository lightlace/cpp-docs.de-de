---
title: "_CrtSetReportMode"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_CrtSetReportMode"
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
  - "_CrtSetReportMode"
  - "CrtSetReportMode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtSetReportMode-Funktion"
  - "CrtSetReportMode-Funktion"
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetReportMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt das Ziel oder die Ziele für einen bestimmten Berichtstyp an, der von `_CrtDbgReport` generiert wird, sowie für alle Makros, die [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) aufrufen, z. B. [\_ASSERT\-, \_ASSERTE\-, \_ASSERT\_EXPR\-Makros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [\_ASSERT\-, \_ASSERTE\-, \_ASSERT\_EXPR\-Makros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [\_RPT\-, \_RPTF\-, \_RPTW\- und \_RPTFW\-Makros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) und [\_RPT\-, \_RPTF\-, \_RPTW\- und \_RPTFW\-Makros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) \(nur Debugversion\).  
  
## Syntax  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### Parameter  
 `reportType`  
 Berichtstyp: `_CRT_WARN`, `_CRT_ERROR` und `_CRT_ASSERT`.  
  
 `reportMode`  
 Neuer Berichtsmodus bzw. neue Berichtsmodi für `reportType`.  
  
## Rückgabewert  
 Nach erfolgreichem Abschluss gibt `_CrtSetReportMode` den vorherigen Berichtsmodus bzw. die Berichtsmodi für den Berichtstyp zurück, der in `reportType` angegeben ist.  Wenn ein ungültiger Wert als `reportType` übergeben oder ein ungültiger Modus für `reportMode` angegeben wird, ruft `_CrtSetReportMode` den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt "– 1" zurück.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 `_CrtSetReportMode` gibt das Ausgabeziel für `_CrtDbgReport` an.  Da die Makros `_ASSERT`, `_ASSERTE`, `_RPT` und `_RPTF` die `_CrtDbgReport`\-Funktion aufrufen, gibt `_CrtSetReportMode` das Ausgabeziel von Text an, der mit diesen Makros festgelegt wurde.  
  
 Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetReportMode` während der Vorverarbeitung entfernt.  
  
 Wenn Sie `_CrtSetReportMode` nicht zum Definieren des Ausgabeziels der Meldungen aufrufen, sind die folgenden Standardwerte gültig:  
  
-   Assertionsfehler werden an ein Debugmeldungsfenster weitergeleitet.  
  
-   Warnungen von Windows\-Anwendungen werden an das Ausgabefenster des Debuggers gesendet.  
  
-   Warnungen von Konsolenanwendungen werden nicht angezeigt.  
  
 In der folgenden Tabelle werden die Berichtstypen aufgeführt, die in "Crtdbg.h" definiert sind.  
  
|Berichtstyp|**Beschreibung**|  
|-----------------|----------------------|  
|`_CRT_WARN`|Warnungen, Meldungen und Informationen, die keine unmittelbare Aufmerksamkeit erfordern.|  
|`_CRT_ERROR`|Fehler, nicht behebbare Probleme sowie Probleme, die unmittelbare Aufmerksamkeit erfordern.|  
|`_CRT_ASSERT`|Assertionsfehler \(überwachte Ausdrücke, die `FALSE` ergeben\).|  
  
 Die `_CrtSetReportMode`\-Funktion weist den in `reportMode` angegebenen neuen Berichtsmodus dem Berichtsmodus zu, der in `reportType` angegeben ist, und gibt den zuvor definierten Berichtsmodus für `reportType` zurück.  In der folgenden Tabelle werden die verfügbaren Optionen für `reportMode` sowie das resultierende Verhalten von `_CrtDbgReport` aufgeführt.  Diese Optionen werden als Bitflags in Crtdbg.h definiert.  
  
|Berichtsmodus|\_CrtDbgReport\-Verhalten|  
|-------------------|-------------------------------|  
|`_CRTDBG_MODE_DEBUG`|Schreibt die Nachricht in das Ausgabefenster des Debuggers.|  
|`_CRTDBG_MODE_FILE`|Schreibt die Nachricht an ein vom Benutzer bereitgestelltes Dateihandle.  [\_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) sollte aufgerufen werden, um die als Ziel zu verwendende bestimmte Datei bzw. den bestimmten Stream zu definieren.|  
|`_CRTDBG_MODE_WNDW`|Erstellt ein Meldungsfeld, um die Meldung zusammen mit der `Abort`\-, `Retry`\- und `Ignore`\-Schaltfläche anzuzeigen.|  
|`_CRTDBG_REPORT_MODE`|Gibt `reportMode` für den angegebenen `reportType`\-Parameter zurück.<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 Jeder Berichtstyp kann mithilfe von einem, zwei oder drei Modi oder keinem Modus gemeldet werden.  Daher ist es möglich, mehrere Ziele festzulegen, die für einen einzelnen Berichtstyp definiert werden.  Beispielsweise führt das folgende Codefragment dazu, dass Assertionsfehler an einen Debugmeldungsfenster und an `stderr` gesendet werden:  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 Außerdem können die Berichterstellungsmodi für jeden Berichtstyp separat gesteuert werden.  Sie können beispielsweise angeben, dass ein `reportType`\-Parameter von `_CRT_WARN` an eine Ausgabedebugzeichenfolge gesendet wird, während `_CRT_ASSERT` mithilfe eines Debugmeldungsfensters angezeigt und an `stderr` gesendet wird, wie zuvor veranschaulicht wurde.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_CrtSetReportMode`|\<crtdbg.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** nur Debugversionen von [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)
---
title: _CrtSetReportMode | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
dev_langs: C++
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 75d71ae4df727df1dd82ff88a793dc4e9c462b76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetreportmode"></a>_CrtSetReportMode
Gibt das Ziel oder die Ziele für einen bestimmten Berichtstyp an, der von `_CrtDbgReport` generiert wird, und Makros, die von [_CrtDbgReport _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) aufgerufen werden, wie z.B. [_ASSERT-, _ASSERTE- und _ASSERT_EXPR-Makros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_ASSERT-, _ASSERTE- und _ASSERT_EXPR-Makros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_RPT-, _RPTF-, _RPTW- und _RPTFW-Makros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) sowie [_RPT-, _RPTF-, _RPTW- und _RPTFW-Makros](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _CrtSetReportMode(   
   int reportType,  
   int reportMode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `reportType`  
 Berichtstyp: `_CRT_WARN`, `_CRT_ERROR` und `_CRT_ASSERT`.  
  
 `reportMode`  
 Neuer Berichtsmodus bzw. neue Berichtsmodi für `reportType`.  
  
## <a name="return-value"></a>Rückgabewert  
 Nach erfolgreichem Abschluss gibt `_CrtSetReportMode` den vorherigen Berichtsmodus bzw. die Berichtsmodi für den Berichtstyp zurück, der in `reportType` angegeben ist. Wenn ein ungültiger Wert als `reportType` übergeben oder ein ungültiger Modus für `reportMode` angegeben wird, ruft `_CrtSetReportMode` den Handler für ungültigen Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, setzt diese Funktion `errno` auf `EINVAL` und gibt "-1" zurück. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 `_CrtSetReportMode` gibt das Ausgabeziel für `_CrtDbgReport` an. Da die Makros `_ASSERT`, `_ASSERTE`, `_RPT` und `_RPTF` die `_CrtDbgReport`-Funktion aufrufen, gibt `_CrtSetReportMode` das Ausgabeziel von Text an, der mit diesen Makros festgelegt wurde.  
  
 Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetReportMode` während der Vorverarbeitung entfernt.  
  
 Wenn Sie `_CrtSetReportMode` nicht zum Definieren des Ausgabeziels der Meldungen aufrufen, sind die folgenden Standardwerte gültig:  
  
-   Assertionsfehler werden an ein Debugmeldungsfenster weitergeleitet.  
  
-   Warnungen von Windows-Anwendungen werden an das Ausgabefenster des Debuggers gesendet.  
  
-   Warnungen von Konsolenanwendungen werden nicht angezeigt.  
  
 In der folgenden Tabelle werden die Berichtstypen aufgeführt, die in "Crtdbg.h" definiert sind.  
  
|Berichtstyp|Beschreibung|  
|-----------------|-----------------|  
|`_CRT_WARN`|Warnungen, Meldungen und Informationen, die keine unmittelbare Aufmerksamkeit erfordern.|  
|`_CRT_ERROR`|Fehler, nicht behebbare Probleme sowie Probleme, die unmittelbare Aufmerksamkeit erfordern.|  
|`_CRT_ASSERT`|Assertionsfehler (überwachte Ausdrücke, die `FALSE` ergeben).|  
  
 Die `_CrtSetReportMode`-Funktion weist den in `reportMode` angegebenen neuen Berichtsmodus dem Berichtsmodus zu, der in `reportType` angegeben ist, und gibt den zuvor definierten Berichtsmodus für `reportType` zurück. In der folgenden Tabelle werden die verfügbaren Optionen für `reportMode` sowie das resultierende Verhalten von `_CrtDbgReport` aufgeführt. Diese Optionen werden als Bitflags in Crtdbg.h definiert.  
  
|Berichtsmodus|_CrtDbgReport-Verhalten|  
|-----------------|-----------------------------|  
|`_CRTDBG_MODE_DEBUG`|Schreibt die Nachricht in das Ausgabefenster des Debuggers.|  
|`_CRTDBG_MODE_FILE`|Schreibt die Nachricht an ein vom Benutzer bereitgestelltes Dateihandle. [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) sollte aufgerufen werden, um die als Ziel zu verwendende bestimmte Datei bzw. den bestimmten Stream zu definieren.|  
|`_CRTDBG_MODE_WNDW`|Erstellt ein Meldungsfeld, um die Meldung zusammen mit der `Abort`-, `Retry`- und `Ignore`-Schaltfläche anzuzeigen.|  
|`_CRTDBG_REPORT_MODE`|Gibt `reportMode` für den angegebenen `reportType`-Parameter zurück.<br /><br /> 1   `_CRTDBG_MODE_FILE`<br /><br /> 2   `_CRTDBG_MODE_DEBUG`<br /><br /> 4   `_CRTDBG_MODE_WNDW`|  
  
 Jeder Berichtstyp kann mithilfe von einem, zwei oder drei Modi oder keinem Modus gemeldet werden. Daher ist es möglich, mehrere Ziele festzulegen, die für einen einzelnen Berichtstyp definiert werden. Beispielsweise führt das folgende Codefragment dazu, dass Assertionsfehler an einen Debugmeldungsfenster und an `stderr` gesendet werden:  
  
```  
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );  
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );  
```  
  
 Außerdem können die Berichterstellungsmodi für jeden Berichtstyp separat gesteuert werden. Sie können beispielsweise angeben, dass ein `reportType`-Parameter von `_CRT_WARN` an eine Ausgabedebugzeichenfolge gesendet wird, während `_CRT_ASSERT` mithilfe eines Debugmeldungsfensters angezeigt und an `stderr` gesendet wird, wie zuvor veranschaulicht wurde.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportMode`|\<crtdbg.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)
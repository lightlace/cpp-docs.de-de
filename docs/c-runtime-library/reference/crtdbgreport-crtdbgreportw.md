---
title: "_CrtDbgReport, _CrtDbgReportW | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDbgReport"
  - "_CrtDbgReportW"
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
  - "CrtDbgReport"
  - "CrtDbgReportW"
  - "_CrtDbgReportW"
  - "_CrtDbgReport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Debugberichterstellung"
  - "_CrtDbgReport-Funktion"
  - "CrtDbgReport-Funktion"
  - "CrtDbgReportW-Funktion"
  - "_CrtDbgReportW-Funktion"
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _CrtDbgReport, _CrtDbgReportW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generiert einen Bericht mit einer Debugmeldung und sendet den Bericht zu drei möglichen Zielen (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `reportType`  
 Berichtstyp: `_CRT_WARN`, `_CRT_ERROR` und `_CRT_ASSERT`.  
  
 `filename`  
 Zeiger auf den Namen der Quelldatei, in der Assert/Bericht oder `NULL` aufgetreten sind.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der Assert/Bericht oder `NULL` aufgetreten sind.  
  
 `moduleName`  
 Zeiger auf den Namen des Moduls (.exe oder .dll), in dem die Assertion oder der Bericht aufgetreten ist.  
  
 `format`  
 Zeiger auf die Formatsteuerelementzeichenfolge, mit der die Benutzermeldung erstellt wird.  
  
 `argument`  
 Von `format` verwendete optionale Ersatzargumente.  
  
## <a name="return-value"></a>Rückgabewert  
 Für alle Berichtsziele geben `_CrtDbgReport` und `_CrtDbgReportW` bei einem Fehler – 1 und bei keinem Fehler 0 zurück. Aber wenn das Berichtsziel Fenster einer Debugmeldung ist und der Benutzer klickt der **Wiederholen** Schaltfläche, diese Funktionen 1 zurück. Klickt der Benutzer auf die **Abbrechen** Schaltfläche im Fenster Debugmeldung diese Funktionen sofort abgebrochen und solchen, die keinen Wert zurück.  
  
 Die [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) Makros rufen `_CrtDbgReport` Berichte an ihre Debugberichte zu generieren. Die Breitzeichenversionen dieser Makros sowie [_ASSERT &#91; E &#93;](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), `_RPTW``n` und `_RPTFW``n`, verwenden `_CrtDbgReportW` Berichte an ihre Debugberichte zu generieren. Wenn `_CrtDbgReport` oder `_CrtDbgReportW` den Wert 1 zurückgeben, starten diese Makros den Debugger, vorausgesetzt, dass Just-In-Time(JIT)-Debugging aktiviert ist.  
  
## <a name="remarks"></a>Hinweise  
 `_CrtDbgReport` und `_CrtDbgReportW` können den Debugbericht an drei verschiedene Ziele senden: an eine Debugberichtsdatei, einen Debugmonitor (der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]-Debugger) oder an ein Debugmeldungsfenster. Zwei Konfigurationsfeatures [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) und [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md), können Sie das Ziel bzw. die Ziele für jeden Bericht angeben. Mithilfe dieser Funktionen können die Berichtsziele für die einzelnen Berichtstypen separat gesteuert werden. Es kann beispielsweise angegeben werden, dass ein `reportType` von `_CRT_WARN` nur zum Debugmonitor gesendet wird, wohingegen ein `reportType` von `_CRT_ASSERT` zu einem Debugmeldungsfenster und einer benutzerdefinierten Berichtsdatei gesendet wird.  
  
 `_CrtDbgReportW` ist die Breitzeichenversion von `_CrtDbgReport`. Alle seine Ausgabe- und Zeichenfolgenparameter sind in Zeichenfolgen mit Breitzeichen. Ansonsten sind sie mit der Einzelbytezeichenversion identisch.  
  
 `_CrtDbgReport` und `_CrtDbgReportW` erstellen die Benutzermeldung für den Debugbericht, indem sie die `argument`[`n`]-Argumente durch die `format`-Zeichenfolge ersetzen und dabei die gleichen Regeln verwenden, die auch für die Funktionen `printf` oder `wprintf` definiert sind. Diese Funktionen generieren dann den Debugbericht und bestimmen das Ziel bzw. die Ziele gemäß der der für `reportType` definierten aktuellen Berichtsmodi und Berichtsdatei. Wenn der Bericht an ein Debugmeldungsfenster gesendet wird, sind `filename`, `lineNumber` und `moduleName` in den im Fenster angezeigten Informationen enthalten.  
  
 In der folgenden Tabelle werden die verfügbaren Optionen für den Berichtsmodus (bzw. die Berichtsmodi) und die Berichtsdatei sowie das resultierende Verhalten von `_CrtDbgReport` und `_CrtDbgReportW` aufgeführt. Diese Optionen werden als Bitflags in \<crtdbg.h> definiert.  
  
|Berichtsmodus|Berichtsdatei|Verhalten von `_CrtDbgReport` und `_CrtDbgReportW`|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|Nicht zutreffend|Schreibt Nachrichten mithilfe von Windows [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API.|  
|`_CRTDBG_MODE_WNDW`|Nicht zutreffend|Ruft die Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) -API zum Erstellen eines Meldungsfelds, um die Nachricht zusammen mit anzuzeigen **Abort**, **Wiederholen**, und **ignorieren** Schaltflächen. Klickt ein Benutzer **Abbrechen**, `_CrtDbgReport` oder `_CrtDbgReport` sofort abgebrochen. Wenn ein Benutzer auf **Wiederholen**, wird 1 zurückgegeben. Wenn ein Benutzer auf **ignorieren**, wird die Ausführung fortgesetzt und `_CrtDbgReport` und `_CrtDbgReportW` geben 0 zurück. Beachten Sie, dass beim Klicken auf **ignorieren** wenn ein Fehlerzustand vorhanden ist oft zur Folge "undefinierten Verhalten".|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|Schreibt eine Meldung in benutzerdefinierten `HANDLE`, mit dem Windows [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) -API, jedoch nicht die Gültigkeit des Dateihandles, die Anwendung ist für das Öffnen der Berichtsdatei und übergeben eines gültigen Dateihandles verantwortlich.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|Schreibt eine Meldung in `stderr`.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|Schreibt eine Meldung in `stdout`.|  
  
 Der Bericht entweder an ein Ziel, an zwei oder drei Ziele oder an kein Ziel gesendet werden. Weitere Informationen zum Angeben der Berichtsmodus oder Modi und der Berichtsdatei finden Sie unter der [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) und [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) Funktionen. Weitere Informationen zum Verwenden der debugmakros und der Berichtsfunktionen finden Sie unter [Makros für die Berichterstattung](../Topic/Macros%20for%20Reporting.md).  
  
 Wenn Ihre Anwendung mehr Flexibilität als die `_CrtDbgReport` und `_CrtDbgReportW`, Sie können Ihre eigene Berichtsfunktion schreiben und sie in der C-Laufzeitbibliothek reporting Mechanismus mit den [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) Funktion.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` und `_CrtDbgReportW` sind Microsoft-Erweiterungen. Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md) nur.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_crtdbgreport.c  
#include <crtdbg.h>  
  
int main(int argc, char *argv[]) {  
#ifdef _DEBUG  
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);  
#endif  
}  
```  
  
 Finden Sie unter [crt_dbg2](assetId:///21e1346a-6a17-4f57-b275-c76813089167) ein Beispiel, wie Sie die Berichtsfunktion ändern.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
  
-   [System::Diagnostics::Debug::Write](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.write.aspx)  
  
-   [System::Diagnostics::Debug::WriteLine](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeline.aspx)  
  
-   [System::Diagnostics::Debug::WriteIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeif.aspx)  
  
-   [System::Diagnostics::Debug::WriteLineIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writelineif.aspx)  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)   
 [Printf, _printf_l, Wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../../c-runtime-library/debug.md)
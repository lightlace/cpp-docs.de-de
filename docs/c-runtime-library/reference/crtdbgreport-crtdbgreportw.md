---
title: _CrtDbgReport _CrtDbgReportW | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bdd8d1545445ea6a478e065dbc3bb5a713e1a602
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW
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
 Für alle berichtsziele `_CrtDbgReport` und `_CrtDbgReportW` 1, wenn ein Fehler auftritt und 0 zurückgeben, wenn keine Fehler auftreten. Wenn das Berichtsziel jedoch das Fenster einer Debugmeldung ist und der Benutzer auf die Schaltfläche **Wiederholen** klickt, dann geben diese Funktionen 1 zurück. Wenn der Benutzer im Fenster der Debugmeldung auf die Schaltfläche **Abbrechen** klickt, brechen diese Funktionen sofort ab und geben keinen Wert zurück.  
  
 Die Debugmakros [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) rufen `_CrtDbgReport` auf, um ihre Debugberichte zu generieren. Die Breitzeichenversionen dieser Makros sowie [_ASSERT&#91;E&#93;](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)`_RPTW n` und `_RPTFW n` verwenden `_CrtDbgReportW`, um ihre Debugberichte zu generieren. Wenn `_CrtDbgReport` oder `_CrtDbgReportW` den Wert 1 zurückgeben, starten diese Makros den Debugger, vorausgesetzt, dass Just-In-Time(JIT)-Debugging aktiviert ist.  
  
## <a name="remarks"></a>Hinweise  
 `_CrtDbgReport` und `_CrtDbgReportW` können den Debugbericht an drei verschiedene Ziele senden: an eine Debugberichtsdatei, einen Debugmonitor (der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]-Debugger) oder an ein Debugmeldungsfenster. Mit den zwei Konfigurationsfunktionen [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) und [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) werden die Ziele für die einzelnen Berichtstypen angegeben. Mithilfe dieser Funktionen können die Berichtsziele für die einzelnen Berichtstypen separat gesteuert werden. Es kann beispielsweise angegeben werden, dass ein `reportType` von `_CRT_WARN` nur zum Debugmonitor gesendet wird, wohingegen ein `reportType` von `_CRT_ASSERT` zu einem Debugmeldungsfenster und einer benutzerdefinierten Berichtsdatei gesendet wird.  
  
 `_CrtDbgReportW` ist die Breitzeichenversion von `_CrtDbgReport`. Alle seine Ausgabe- und Zeichenfolgenparameter sind in Zeichenfolgen mit Breitzeichen. Ansonsten sind sie mit der Einzelbytezeichenversion identisch.  
  
 `_CrtDbgReport` und `_CrtDbgReportW` erstellen die Benutzermeldung für den Debugbericht, indem sie die `argument`[`n`]-Argumente durch die `format`-Zeichenfolge ersetzen und dabei die gleichen Regeln verwenden, die auch für die Funktionen `printf` oder `wprintf` definiert sind. Diese Funktionen generieren dann den Debugbericht und bestimmen das Ziel bzw. die Ziele gemäß der der für `reportType` definierten aktuellen Berichtsmodi und Berichtsdatei. Wenn der Bericht an ein Debugmeldungsfenster gesendet wird, sind `filename`, `lineNumber` und `moduleName` in den im Fenster angezeigten Informationen enthalten.  
  
 In der folgenden Tabelle werden die verfügbaren Optionen für den Berichtsmodus (bzw. die Berichtsmodi) und die Berichtsdatei sowie das resultierende Verhalten von `_CrtDbgReport` und `_CrtDbgReportW` aufgeführt. Diese Optionen werden als Bitflags in \<crtdbg.h>. definiert.  
  
|Berichtsmodus|Berichtsdatei|Verhalten von `_CrtDbgReport` und `_CrtDbgReportW`|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|Nicht zutreffend|Schreibt die Meldung in die Windows-API[OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx)|  
|`_CRTDBG_MODE_WNDW`|Nicht zutreffend|Ruft die Windows-API [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) zum Erstellen eines Meldungsfelds auf, um die Meldung zusammen mit den Schaltflächen **Abbrechen**, **Wiederholen** und **Ignorieren** anzuzeigen Wenn ein Benutzer auf **Abbrechen** klickt, wird `_CrtDbgReport` oder `_CrtDbgReport` sofort abgebrochen. Wenn ein Benutzer auf **Wiederholen** klickt, wird 1 zurückgegeben. Wenn ein Benutzer auf **Ignorieren** klickt, wird die Ausführung fortgesetzt, und `_CrtDbgReport` und `_CrtDbgReportW` geben 0 zurück. Wenn ein Fehlerzustand vorliegt, führt das Klicken auf **Ignorieren** häufig zu einem „undefinierten Verhalten“.|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|Schreibt eine Meldung an ein benutzerdefiniertes `HANDLE` mithilfe der Windows [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx)-API, überprüft jedoch nicht Gültigkeit des Dateihandles. Die Anwendung ist für das Öffnen der Berichtsdatei und das Übergeben eines gültigen Dateihandles verantwortlich.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|Schreibt eine Meldung in `stderr`.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|Schreibt eine Meldung in `stdout`.|  
  
 Der Bericht entweder an ein Ziel, an zwei oder drei Ziele oder an kein Ziel gesendet werden. Weitere Informationen zum Angeben des Berichtsmodus bzw. der Berichtsmodi und der Berichtsdatei finden Sie unter den Funktionen [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) und [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md). Weitere Informationen zum Verwenden der Debugmakros und der Berichtsfunktionen finden Sie unter [Makros für die Berichterstellung](/visualstudio/debugger/macros-for-reporting).  
  
 Wenn Ihre Anwendung mehr Flexibilität benötigt, als von `_CrtDbgReport` und `_CrtDbgReportW` bereitgestellt wird, können Sie Ihre eigene Berichtsfunktion schreiben und sie in die Berichtsmechanismen der C-Laufzeitbibliothek integrieren, indem Sie die [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md)-Funktion verwenden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` und `_CrtDbgReportW` sind Microsoft-Erweiterungen. Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
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
  
 Unter [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167) finden Sie ein Beispiel, wie Sie die Berichtsfunktion ändern können.  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../../c-runtime-library/debug.md)
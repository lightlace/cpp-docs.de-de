---
title: Debugroutinen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- macros, debugging with
- debug routines
- debug macros
- debugging [CRT], run-time routines
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
caps.latest.revision: 11
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
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 41e3f6151dc3bec38cd672deee681c37e090507f
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="debug-routines"></a>Debugroutinen
Die Debugversion der C-Laufzeitbibliothek stellt viele Diagnosedienste bereit, die das Debuggen von Programmen vereinfachen und Entwicklern Folgendes ermöglichen:  
  
-   Ausführen von einzelnen Schritten direkt in die Laufzeitfunktionen während des Debuggens  
  
-   Beheben von Assertionen, Fehlern und Ausnahmen  
  
-   Nachverfolgen von Heapzuordnungen und Verhindern von Speicherverlusten  
  
-   Übermitteln von Debugmeldungen an den Benutzer  
  
 Um diese Routinen zu verwenden, muss das [_DEBUG](../c-runtime-library/debug.md)-Flag definiert werden. Alle diese Routinen führen in einer Verkaufsversion einer Anwendung keine Aktionen aus. Weitere Informationen zur Verwendung der neuen Debugroutinen finden Sie unter [CRT Debugging Techniques (CRT-Debugverfahren)](/visualstudio/debugger/crt-debugging-techniques).  
  
### <a name="debug-versions-of-the-c-run-time-library-routines"></a>Debugversionen der C-Laufzeitbibliotheksroutinen  
  
|Routine|Verwendung|  
|-------------|---------|  
|[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Wertet einen Ausdruck aus und erzeugt einen Debugbericht, wenn das Ergebnis "FALSE" lautet.|  
|[_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Ähnlich wie `_ASSERT`, schließt jedoch den fehlgeschlagenen Ausdruck im generierten Bericht ein.|  
|[_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|Bestätigt die Integrität der Speicherblöcke, die im Debugheap zugeordnet werden.|  
|[_CrtDbgBreak](../c-runtime-library/reference/crtdbgbreak.md)|Legt einen Haltepunkt fest.|  
|[_CrtDbgReport, _CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|Generiert einen Debugbericht mit einer Benutzermeldung und sendet den Bericht an drei mögliche Ziele.|  
|[_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|Ruft eine von der Anwendung bereitgestellte Funktion für alle `_CLIENT_BLOCK`-Typen auf dem Heap auf.|  
|[_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|Gibt alle Speicherblöcke im Debugheap aus, wenn ein bedeutender Speicherverlust aufgetreten ist.|  
|[_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|Überprüft, ob sich ein angegebener Speicherblock im lokalen Heap befindet und ob er einen gültigen Debugheap-Blocktypbezeichner hat.|  
|[_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|Überprüft, ob sich ein angegebener Zeiger im lokalen Heap befindet.|  
|[_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|Überprüft, ob ein bestimmter Speicherbereich für Lese- und Schreibvorgänge gültig ist.|  
|[_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|Ruft den aktuellen Zustand des Debugheaps ab und speichert ihn in einer von der Anwendung bereitgestellten `_CrtMemState`-Struktur.|  
|[_CrtMemDifference](../c-runtime-library/reference/crtmemdifference.md)|Vergleicht zwei Speicherzustände für wesentliche Unterschiede und gibt die Ergebnisse zurück.|  
|[_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md)|Gibt Informationen über Objekte auf dem Heap aus, seit ein angegebener Prüfpunkt übernommen wurde oder ab Beginn der Programmausführung.|  
|[_CrtMemDumpStatistics](../c-runtime-library/reference/crtmemdumpstatistics.md)|Gibt die Debugheaderinformationen für einen angegebenen Speicherzustand in einer für den Benutzer lesbaren Form aus.|  
|[_CrtReportBlockType](../c-runtime-library/reference/crtreportblocktype.md)|Gibt den Blocktyp/den Untertyp zurück, der einem angegebenen Debugheapblockzeiger zugeordnet ist.|  
|[_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md)|Installiert eine clientdefinierte Zuordnungsfunktion, indem sie mit dem Debug-Speicherbelegungsprozess der C-Laufzeit verknüpft wird.|  
|[_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|Legt einen Haltepunkt an einer angegebenen Befehlsnummer der Objektzuordnung fest.|  
|[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|Ruft den Zustand des `_crtDbgFlag`-Flags ab oder ändert ihn, um das Zuordnungsverhalten des Debugheapmanagers zu steuern.|  
|[_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|Installiert eine anwendungsdefinierte Funktion, die bei jedem Aufruf einer Debugdumpfunktion aufgerufen wird, um `_CLIENT_BLOCK`-Typspeicherblöcke auszugeben.|  
|[_CrtSetReportFile](../c-runtime-library/reference/crtsetreportfile.md)|Identifiziert die als Ziel für einen bestimmten Berichtstyp von `_CrtDbgReport` zu verwendende Datei bzw. Stream.|  
|[_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|Installiert eine clientdefinierte Berichtsfunktion, indem sie mit dem Debug-Berichterstellungsprozess der C-Laufzeit verknüpft wird.|  
|[_CrtSetReportHook2, _CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|Installiert bzw. deinstalliert eine clientdefinierte Berichtsfunktion, indem sie mit dem Debug-Berichterstellungsprozess der C-Laufzeit verknüpft wird.|  
|[_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|Gibt die allgemeinen Ziele für einen bestimmten Berichtstyp an, der von `_CrtDbgReport` generiert wird.|  
|[_RPT&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Verfolgt den Status der Anwendung durch Generieren eines Debugberichts, indem `_CrtDbgReport` mit einer Formatzeichenfolge und einer variablen Anzahl von Argumenten aufgerufen wird. Stellt keine Quelldatei und Zeilennummern bereit.|  
|[_RPTF&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Ähnlich den `_RPTn`-Makros, jedoch werden der Quelldateiname und die Zeilennummer bereitgestellt, aus denen die Berichtsanforderung stammt.|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Ordnet eine bestimmte Anzahl von Speicherblöcken auf dem Heap mit zusätzlichem Speicher für einen Debugheader und Überschreibungspuffer zu.|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Ändert die Größe eines angegebenen Speicherblocks auf dem Heap, indem der Block erweitert oder verkleinert wird.|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Gibt einen Speicherblock auf dem Heap frei.|  
|[_fullpath_dbg, _wfullpath_dbg](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)|Erstellt mithilfe von [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) einen absoluten oder vollständigen Pfadnamen für den angegebenen relativen Pfadnamen, um Speicher zu belegen.|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[_getcwd_dbg, _wgetcwd_dbg](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)|Ruft das aktuelle Arbeitsverzeichnis mithilfe von [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) ab, um Speicher zu belegen.|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Ordnet einen Speicherblock auf dem Heap mit zusätzlichem Speicher für einen Debugheader und Überschreibungspuffer zu.|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Berechnet die Größe eines Speicherblocks auf dem Heap.|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Ordnet einen angegebenen Speicherblock auf dem Heap neu zu, indem der Block verschoben und/oder seine Größe geändert wird.|  
|[_strdup_dbg, _wcsdup_dbg](../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)|Dupliziert eine Zeichenfolge mithilfe von [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md), um Speicher zu belegen.|  
|[_tempnam_dbg, _wtempnam_dbg](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)|Generiert Namen, die Sie mithilfe von [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) zum Erstellen von temporären Dateien verwenden können, um Speicher zu belegen.|  
  
 Die Debugroutinen können verwendet werden, um den Quellcode für die meisten der anderen C-Laufzeitroutinen während des Debugprozesses schrittweise auszuführen. Allerdings erachtet Microsoft einige Technologien als proprietär und stellt daher keinen Quellcode für diese Routinen bereit. Die meisten dieser Routinen gehören zur Ausnahmebehandlung oder zu den Gruppen der Gleitkommaverarbeitung, einige andere werden jedoch ebenfalls eingeschlossen. In der folgenden Tabelle sind diese Routinen aufgeführt.  
  
### <a name="c-run-time-routines-that-are-not-available-in-source-code-form"></a>C-Laufzeitroutinen, die nicht in Quellcodeform verfügbar sind  
  
||||  
|-|-|-|  
|[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|[_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|[_nextafter](../c-runtime-library/reference/nextafter-functions.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|  
|[atan, atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[_fpreset](../c-runtime-library/reference/fpreset.md)|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)*|  
|[_cabs](../c-runtime-library/reference/cabs.md)|[frexp](../c-runtime-library/reference/frexp.md)|[_scalb](../c-runtime-library/reference/scalb.md)|  
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|[_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)*|  
|[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|[_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|[setjmp](../c-runtime-library/reference/setjmp.md)|  
|[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|[_j0](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[_control87, _controlfp, \__control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)|[_j1](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|[_jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[ldexp](../c-runtime-library/reference/ldexp.md)|[_status87, _statusfp](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|  
|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[Exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|[_y0](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[_finite](../c-runtime-library/reference/finite-finitef.md)|[longjmp](../c-runtime-library/reference/longjmp.md)|[_y1](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|[_matherr](../c-runtime-library/reference/matherr.md)|[_yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[modf](../c-runtime-library/reference/modf-modff-modfl.md)||  
  
 \* Obwohl Quellcode für die meisten dieser Routinen verfügbar ist, ruft er intern eine andere Routine auf, für die kein Quellcode bereitgestellt wird.  
  
 Einige C-Laufzeitfunktionen und C++-Operatoren verhalten sich unterschiedlich, wenn sie von einem Debugbuild einer Anwendung aufgerufen werden. (Beachten Sie, dass ein Debugbuild einer Anwendung erfolgen kann, indem das `_DEBUG`-Flag definiert wird oder indem eine Verknüpfung mit einer Debugversion der C-Laufzeitbibliothek erstellt wird.) Die Verhaltensunterschiede bestehen normalerweise aus zusätzlichen Funktionen oder aus Informationen, die von der Routine zur Unterstützung des Debugprozesses bereitgestellt werden. In der folgenden Tabelle sind diese Routinen aufgeführt.  
  
### <a name="routines-that-behave-differently-in-a-debug-build-of-an-application"></a>Routinen, die sich in einem Debugbuild einer Anwendung unterschiedlich verhalten  
  
|||  
|-|-|  
|C-Routine [abort](../c-runtime-library/reference/abort.md)|C++-Operator [delete](../cpp/delete-operator-cpp.md)|  
|C-Routine [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|C++-Operator [new](../cpp/new-operator-cpp.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [Run-Time Routines by Category (Laufzeitroutinen nach Kategorie)](../c-runtime-library/run-time-routines-by-category.md)   
 [Run-Time Error Checking (Laufzeitfehlerüberprüfung)](../c-runtime-library/run-time-error-checking.md)

---
title: _CrtSetReportHook | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetReportHook
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
- _CrtSetReportHook
- CrtSetReportHook
dev_langs: C++
helpviewer_keywords:
- CrtSetReportHook function
- _CrtSetReportHook function
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c1fb85ab41c02bb9f604f024f86ebb42706eeda
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetreporthook"></a>_CrtSetReportHook
Installiert eine clientdefinierte Berichtsfunktion, indem sie mit dem Debug-Berichterstellungsprozess der C-Laufzeit verknüpft wird (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
_CRT_REPORT_HOOK _CrtSetReportHook(   
   _CRT_REPORT_HOOK reportHook   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `reportHook`  
 Die neue clientdefinierte Berichtsfunktion, die mit dem Debug-Berichterstellungsprozess der C-Laufzeit verknüpft werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die vorherige clientdefinierte Berichtsfunktion zurück.  
  
## <a name="remarks"></a>Hinweise  
 `_CrtSetReportHook` ermöglicht es einer Anwendung, eine eigene Berichtsfunktion im Debugbibliothek-Berichterstellungsprozess der C-Laufzeit zu verwenden. Folglich wird bei jedem Aufruf von [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) zum Generieren eines Debugberichts die Berichtsfunktion der Anwendung zuerst aufgerufen. Diese Funktionalität ermöglicht es einer Anwendung, Vorgänge wie das Filtern von Debugberichten auszuführen, sodass sie sich auf bestimmte Zuordnungstypen konzentrieren oder einen Bericht an nicht verfügbare Ziele senden kann, indem `_CrtDbgReport` verwendet wird. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetReportHook` während der Vorverarbeitung entfernt.  
  
 Eine stabilere Version von `_CrtSetReportHook` finden Sie unter [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md).  
  
 Die `_CrtSetReportHook`-Funktion installiert die neue clientdefinierte Berichtsfunktion, die in `reportHook` angegeben wird, und gibt die vorherige clientdefinierte Hookfunktion zurück. Das folgende Beispiel zeigt, wie ein Prototyp einer clientdefinierten Hookfunktion für Berichte entwickelt werden soll:  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 wobei Folgendes gilt: `reportType` ist der Debugberichtstyp (`_CRT_WARN`, `_CRT_ERROR` oder `_CRT_ASSERT`), `message` ist die vollständig assemblierte Debugbenutzermeldung, die im Bericht enthalten sein sollte, und `returnValue` ist der von der clientdefinierten Berichtsfunktion angegebene Wert, der von `_CrtDbgReport` zurückgegeben werden soll. Eine vollständige Beschreibung der verfügbaren Berichtstypen finden Sie in der [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)-Funktion.  
  
 Wenn die clientdefinierte Berichtsfunktion die Debugmeldung vollständig bearbeitet, sodass kein weiterer Bericht erforderlich ist, sollte die Funktion `TRUE` zurückgeben. Wenn die Funktion `FALSE` zurückgibt, wird `_CrtDbgReport` aufgerufen, um den Debugbericht mithilfe der aktuellen Einstellungen für den Berichtstyp, den Berichtsmodus und die Berichtsdatei zu generieren. Wenn darüber hinaus der `_CrtDbgReport`-Rückgabewert in `returnValue` angegeben wird, kann die Anwendung auch steuern, ob ein Debugabbruch auftritt. Eine vollständige Beschreibung der Konfiguration und Generierung des Debugberichts finden Sie unter `_CrtSetReportMode`, [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) und `_CrtDbgReport`.  
  
 Weitere Informationen zur Verwendung anderer hookfähiger Laufzeitfunktionen und zum Schreiben eigener clientdefinierter Hookfunktionen finden Sie unter [Debug Hook Function Writing (Schreiben von Hookfunktionen zum Debuggen)](/visualstudio/debugger/debug-hook-function-writing).  
  
> [!NOTE]
>  Wenn die Anwendung mit `/clr` kompiliert und die Berichtsfunktion nach dem Beenden der Anwendung "Main" aufgerufen wird, löst die CLR eine Ausnahme aus, wenn die Berichterstellungsfunktion eine CRT-Funktion aufruft.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtSetReportHook`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [_CrtGetReportHook](../../c-runtime-library/reference/crtgetreporthook.md)
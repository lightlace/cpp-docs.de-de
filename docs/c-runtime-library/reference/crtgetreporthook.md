---
title: _CrtGetReportHook | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtGetReportHook
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
- CrtGetReportHook
- _CrtGetReportHook
dev_langs: C++
helpviewer_keywords:
- CrtGetReportHook function
- _CrtGetReportHook function
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69c49895f50f18e96a1d673df3e80e6bb7d88824
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crtgetreporthook"></a>_CrtGetReportHook
Ruft die clientdefinierte Berichtsfunktion ab, um sie mit der C-Laufzeit für den Debug-Berichterstellungsprozess zu verknüpfen (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
_CRT_REPORT_HOOK _CrtGetReportHook( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die aktuelle clientdefinierte Berichtsfunktion zurück.  
  
## <a name="remarks"></a>Hinweise  
 `_CrtGetReportHook` ermöglicht es einer Anwendung, die aktuelle Berichtsfunktion für den Debugbibliothek-Berichterstellungsprozess der C-Laufzeit abzurufen.  
  
 Weitere Informationen zur Verwendung anderer hookfähiger Laufzeitfunktionen und zum Schreiben eigener clientdefinierter Hookfunktionen finden Sie unter [Debug Hook Function Writing (Schreiben von Hookfunktionen zum Debuggen)](/visualstudio/debugger/debug-hook-function-writing).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtGetReportHook`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von `_CrtSetReportHook` finden Sie unter [report](http://msdn.microsoft.com/en-us/f6e08c30-6bd9-459a-830a-56deec0d2051).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md)
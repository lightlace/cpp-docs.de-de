---
title: _CrtSetDumpClient | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 035851454e2f163ea013a7240d6699db402565d3
ms.lasthandoff: 02/24/2017

---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient
Installiert eine anwendungsdefinierte Funktion, zum Ausgeben von `_CLIENT_BLOCK`-Typspeicherblöcken (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dumpClient`  
 Die neue clientdefinierte Speicherabbildfunktion, die mit dem Debug-Speicherabbildprozess der C-Laufzeit verknüpft werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die zuvor definierte Client-Blockdumpfunktion zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_CrtSetDumpClient`-Funktion ermöglicht es der Anwendung, eine eigene Funktion für Dumpobjekte, die in `_CLIENT_BLOCK`-Speicherblöcken gespeichert sind, mit dem Debug-Speicherabbildprozess der C-Laufzeit zu verknüpfen. Wenn eine Debugdumpfunktion wie [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) oder [_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) einen `_CLIENT_BLOCK`-Speicherblock ausgibt, wird die Dumpfunktion der Anwendung ebenfalls aufgerufen. `_CrtSetDumpClient` stellt für eine Anwendung eine einfache Methode zum Erkennen von Speicherverlusten und zum Überprüfen oder Übermitteln des Inhalts der Daten bereit, die in `_CLIENT_BLOCK`-Blöcken gespeichert sind. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetDumpClient` während der Vorverarbeitung entfernt.  
  
 Die `_CrtSetDumpClient`-Funktion installiert die neue anwendungsdefinierte Dumpfunktion, die in `dumpClient` angegeben ist, und gibt die zuvor definierte Dumpfunktion zurück. Beispiel einer Client-Blockdumpfunktion:  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 Das `userPortion`-Argument ist ein Zeiger auf den Anfang des Benutzerdatenteils des Speicherblocks, und `blockSize` gibt die Größe des belegten Speicherblocks in Bytes an. Die Client-Blockdumpfunktion muss `void` zurückgeben. Der Zeiger zur Clientdumpfunktion, der an `_CrtSetDumpClient` übergeben wird, ist vom Typ `_CRT_DUMP_CLIENT`, wie in "Crtdbg.h" definiert:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 Weitere Informationen zu Funktionen, die `_CLIENT_BLOCK`-Typspeicherblöcke verarbeiten, finden Sie unter [Hookfunktionen für Clientblöcke](/visualstudio/debugger/client-block-hook-functions). Die [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)-Funktion kann zum Zurückgeben von Informationen zu Blocktypen und -untertypen verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtSetDumpClient`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md)  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)

---
title: "_CrtSetDumpClient | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetDumpClient"
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
  - "_CrtSetDumpClient"
  - "CrtSetDumpClient"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetDumpClient-Funktion"
  - "CrtSetDumpClient-Funktion"
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtSetDumpClient
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installiert eine anwendungsdefinierte Funktion, zum Ausgeben von `_CLIENT_BLOCK`\-Typspeicherblöcken \(nur Debugversion\).  
  
## Syntax  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### Parameter  
 `dumpClient`  
 Die neue clientdefinierte Speicherabbildfunktion, die mit dem Debug\-Speicherabbildprozess der C\-Laufzeit verknüpft werden soll.  
  
## Rückgabewert  
 Gibt die zuvor definierte Client\-Blockdumpfunktion zurück.  
  
## Hinweise  
 Die `_CrtSetDumpClient`\-Funktion ermöglicht es der Anwendung, eine eigene Funktion für Dumpobjekte, die in `_CLIENT_BLOCK`\-Speicherblöcken gespeichert sind, mit dem Debug\-Speicherabbildprozess der C\-Laufzeit zu verknüpfen.  Wenn eine Debugdumpfunktion wie [\_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) oder [\_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) einen `_CLIENT_BLOCK`\-Speicherblock ausgibt, wird die Dumpfunktion der Anwendung daher ebenfalls aufgerufen.  `_CrtSetDumpClient` stellt für eine Anwendung eine einfache Methode zum Erkennen von Speicherverlusten und zum Überprüfen oder Übermitteln des Inhalts der Daten bereit, die in `_CLIENT_BLOCK`\-Blöcken gespeichert sind.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetDumpClient` während der Vorverarbeitung entfernt.  
  
 Die `_CrtSetDumpClient`\-Funktion installiert die neue anwendungsdefinierte Dumpfunktion, die in `dumpClient` angegeben ist, und gibt die zuvor definierte Dumpfunktion zurück.  Beispiel einer Client\-Blockdumpfunktion:  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 Das `userPortion`\-Argument ist ein Zeiger auf den Anfang des Benutzerdatenteils des Speicherblocks, und `blockSize` gibt die Größe des belegten Speicherblocks in Bytes an.  Die Client\-Blockdumpfunktion muss `void` zurückgeben.  Der Zeiger zur Clientdumpfunktion, der an `_CrtSetDumpClient` übergeben wird, ist vom Typ `_CRT_DUMP_CLIENT`, wie in "Crtdbg.h" definiert:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 Weitere Informationen zu Funktionen, die `_CLIENT_BLOCK`\-Typspeicherblöcke verarbeiten, finden Sie unter [Hookfunktionen für Clientblöcke](../Topic/Client%20Block%20Hook%20Functions.md).  Die [\_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)\-Funktion kann zum Zurückgeben von Informationen zu Blocktypen und \-untertypen verwendet werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_CrtSetDumpClient`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [\_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)
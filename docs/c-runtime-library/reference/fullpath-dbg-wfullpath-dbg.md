---
title: "_fullpath_dbg, _wfullpath_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wfullpath_dbg"
  - "_fullpath_dbg"
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
  - "wfullpath_dbg"
  - "_wfullpath_dbg"
  - "_fullpath_dbg"
  - "fullpath_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fullpath_dbg-Funktion"
  - "_wfullpath_dbg-Funktion"
  - "Absolute Pfade"
  - "fullpath_dbg-Funktion"
  - "Relative Dateipfade"
  - "wfullpath_dbg-Funktion"
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _fullpath_dbg, _wfullpath_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versionen von [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md), die die Debugversion von `malloc` zur Speicherbelegung verwenden.  
  
## Syntax  
  
```  
char *_fullpath_dbg(     char *absPath,    const char *relPath,    size_t maxLength,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wfullpath_dbg(     wchar_t *absPath,    const wchar_t *relPath,    size_t maxLength,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Parameter  
 `absPath`  
 Zeiger auf einen Puffer, der den absoluten oder vollständigen Pfadnamen enthält, oder `NULL`.  
  
 `relPath`  
 Relativer Pfadname.  
  
 `maxLength`  
 Maximale Länge des Puffers des absoluten Pfadnamens \(`absPath`\).  Die Länge wird für `_fullpath` in Bytes ausgedrückt, aber für `_wfullpath` in Breitzeichen \(`wchar_t`\).  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger zum Namen der Quelldatei, die die Zuordnung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder `NULL`.  
  
## Rückgabewert  
 Jede Funktion gibt einen Zeiger auf einen Puffer zurück, der den absoluten Pfadnamen \(`absPath`\) enthält.  Wenn ein Fehler auftritt \(z. B, wenn der in `relPath` übergebene Wert einen Laufwerksbuchstaben enthält, der nicht gültig ist oder nicht gefunden werden kann oder wenn der erstellte absolute Pfadname \(`absPath`\) länger ist als `maxLength`\), gibt die Funktion `NULL` zurück.  
  
## Hinweise  
 Die Funktionen `_fullpath_dbg` und `_wfullpath_dbg` sind identisch mit `_fullpath` und `_wfullpath`, außer dass bei Definition von **\_**`DEBUG` diese Funktionen die Debugversion von `malloc`, `_malloc_dbg` verwenden, wenn NULL als erster Parameter übergeben wird.  Weitere Informationen zu den Debugfunktionen von `_malloc_dbg` finden Sie unter [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen.  Stattdessen können Sie das Flag `_CRTDBG_MAP_ALLOC` definieren.  Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_fullpath` und `_wfullpath` neu zu `_fullpath_dbg` bzw. `_wfullpath_dbg` zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` gesetzt wird.  Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren.  Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tfullpath_dbg`|`_fullpath_dbg`|`_fullpath_dbg`|`_wfullpath_dbg`|  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fullpath_dbg`|\<crtdbg.h\>|  
|`_wfullpath_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 <xref:System.IO.File.Create*>  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)
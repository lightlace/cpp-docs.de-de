---
title: "_tempnam_dbg, _wtempnam_dbg"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_wtempnam_dbg"
  - "_tempnam_dbg"
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
  - "wtempnam_dbg"
  - "tempnam_dbg"
  - "_tempnam_dbg"
  - "_wtempnam_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tempnam_dbg-Funktion"
  - "_wtempnam_dbg-Funktion"
  - "Dateinamen [C++], Erstellen temporärer"
  - "Dateinamen [C++], Temporär"
  - "tempnam_dbg-Funktion"
  - "Temporäre Dateien, Erstellen"
  - "wtempnam_dbg-Funktion"
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# _tempnam_dbg, _wtempnam_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Funktionsversionen von [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md), die die Debugversion von `malloc, _malloc_dbg` verwenden.  
  
## Syntax  
  
```  
char *_tempnam_dbg(    const char *dir,    const char *prefix,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wtempnam_dbg(    const wchar_t *dir,    const wchar_t *prefix,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Parameter  
 `dir`  
 Der im Dateinamen verwendete Pfad, wenn es keine TMP\-Umgebungsvariable gibt oder wenn TMP kein gültiges Verzeichnis ist.  
  
 `prefix`  
 Die Zeichenfolge, die den von `_tempnam` zurückgegebenen Namen vorangestellt wird.  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK`oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger auf den Namen der Quelldatei, die die Zuordnung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder `NULL`.  
  
## Rückgabewert  
 Jede Funktion gibt einen Zeiger auf den erzeugten Namen oder auf `NULL` zurück, falls eine Störung vorliegt.  Störungen können auftreten, wenn in der TMP\-Umgebungsvariable und im `dir`\-Parameter ein ungültiger Verzeichnisname angegeben wurde.  
  
> [!NOTE]
>  `free` \(oder `free_dbg`\) muss für von `_tempnam_dbg` und `_wtempnam_dbg` belegte Zeiger nicht aufgerufen werden.  
  
## Hinweise  
 Die Funktionen `_tempnam_dbg`und `_wtempnam_dbg` sind identisch mit `_tempnam`und `_wtempnam`, außer dass bei Definition von `_DEBUG`diese Funktionen die Debugversion von `malloc`, `_malloc_dbg` verwenden, wenn `NULL` als erster Parameter übergeben wird.  Weitere Informationen finden Sie unter [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen.  Stattdessen können Sie das `_CRTDBG_MAP_ALLOC`\-Flag definieren.  Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_tempnam` und `_wtempnam` zu  `_tempnam_dbg` bzw. `_wtempnam_dbg` neu zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` festgelegt wird.  Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren.  Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)
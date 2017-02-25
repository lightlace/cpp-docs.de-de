---
title: "_strdup_dbg, _wcsdup_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strdup_dbg"
  - "_wcsdup_dbg"
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
  - "_wcsdup_dbg"
  - "strdup_dbg"
  - "_strdup_dbg"
  - "wcsdup_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strdup_dbg-Funktion"
  - "_wcsdup_dbg-Funktion"
  - "Kopieren von Zeichenfolgen"
  - "Verdoppeln von Zeichenfolgen"
  - "stdup_dbg-Funktion"
  - "Zeichenfolgen [C++], Kopieren"
  - "Zeichenfolgen [C++], Duplizieren"
  - "wcsdup_dbg-Funktion"
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _strdup_dbg, _wcsdup_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Versionen von [\_strdup and \_wcsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md), die die Debugversion von `malloc` verwenden.  
  
## Syntax  
  
```  
char *_strdup_dbg(    const char *strSource,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wcsdup_dbg(    const wchar_t *strSource,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Parameter  
 `strSource`  
 Mit NULL endende Quellzeichenfolge.  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger auf den Namen der Quelldatei, die die Zuordnung angefordert hat, oder NULL.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder NULL.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf den Speicherort für die kopierte Zeichenfolge oder `NULL` zurück, wenn der Speicher nicht belegt werden kann.  
  
## Hinweise  
 Die Funktionen `_strdup_dbg` und `_wcsdup_dbg` sind identisch mit `_strdup` und `_wcsdup`, außer dass bei Definition von `_DEBUG` diese Funktionen die Debugversion von `malloc` und `_malloc_dbg` verwenden, um Speicher für die duplizierte Zeichenfolge zu belegen.  Weitere Informationen zu den Debugfunktionen von `_malloc_dbg` finden Sie unter [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen.  Stattdessen können Sie das `_CRTDBG_MAP_ALLOC`\-Flag definieren.  Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_strdup` und `_wcsdup` zu `_strdup_dbg` bzw. `_wcsdup_dbg` neu zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` festgelegt wird.  Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren.  Weitere Informationen zu Blocktypen finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tcsdup_dbg`|`_strdup_dbg`|`_mbsdup`|`_wcsdup_dbg`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_strdup_dbg`, `_wcsdup_dbg`|\<crtdbg.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Debugversionen der [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 [System::String::Clone](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strdup, \_wcsdup, \_mbsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)   
 [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)
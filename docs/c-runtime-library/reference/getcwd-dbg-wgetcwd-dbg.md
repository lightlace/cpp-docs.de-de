---
title: "_getcwd_dbg, _wgetcwd_dbg"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_wgetcwd_dbg"
  - "_getcwd_dbg"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getcwd_dbg"
  - "_wgetcwd_dbg"
  - "getcwd_dbg"
  - "wgetcwd_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getcwd_dbg-Funktion"
  - "_wgetcwd_dbg-Funktion"
  - "Aktuelles Arbeitsverzeichnis"
  - "Verzeichnisse [C++], Aktuell arbeiten"
  - "getcwd_dbg-Funktion"
  - "wgetcwd_dbg-Funktion"
  - "Arbeitsverzeichnis"
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _getcwd_dbg, _wgetcwd_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Debugversionen der Funktionen [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md) \(nur während des Debuggens verfügbar\).  
  
## Syntax  
  
```  
char *_getcwd_dbg(     char *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wgetcwd_dbg(     wchar_t *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für den Pfad.  
  
 `maxlen`  
 Maximale Länge des Pfads in Zeichen: `char` für `_getcwd_dbg` und `wchar_t` für `_wgetcwd_dbg`.  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger auf den Namen der Quelldatei, die die Belegung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder `NULL`.  
  
## Rückgabewert  
 Gibt einen Zeiger auf `buffer` zurück.  Ein `NULL`\-Rückgabewert zeigt einen Fehler an, und `errno` wird entweder auf `ENOMEM` festgelegt, um anzugeben, dass nicht genügend Arbeitsspeicher zum Zuordnen von `maxlen` Bytes vorhanden ist \(wenn ein `NULL`\-Argument als `buffer` angegeben wird\), oder auf `ERANGE`, um anzugeben, dass der Pfad länger als `maxlen` Zeichen ist.  
  
 Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die Funktionen `_getcwd_dbg` und `_wgetcwd_dbg` sind identisch mit `_getcwd` und `_wgetcwd`, außer dass bei Definition von `DEBUG` diese Funktionen die Debugversion von `malloc`, `_malloc_dbg` verwenden, wenn `NULL` als erster Parameter übergeben wird.  Weitere Informationen finden Sie unter [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen.  Stattdessen können Sie das Flag `_CRTDBG_MAP_ALLOC` definieren.  Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_getcwd` und `_wgetcwd` zu `_getcwd_dbg`bzw. `_wgetcwd_dbg` neu zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` gesetzt wird.  Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren.  Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
## Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tgetcwd_dbg`|`_getcwd_dbg`|`_getcwd_dbg`|`_wgetcwd_dbg`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_getcwd_dbg`|\<crtdbg.h\>|  
|`_wgetcwd_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 <xref:System.Environment.CurrentDirectory*>  
  
## Siehe auch  
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)
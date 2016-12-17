---
title: "_getdcwd_dbg, _wgetdcwd_dbg"
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
  - "_getdcwd_dbg"
  - "_wgetdcwd_dbg"
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
  - "_getdcwd_dbg"
  - "getdcwd_dbg"
  - "_wgetdcwd_dbg"
  - "wgetdcwd_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getdcwd_dbg-Funktion"
  - "_wgetdcwd_dbg-Funktion"
  - "Aktuelles Arbeitsverzeichnis"
  - "Verzeichnisse [C++], Aktuell arbeiten"
  - "getdcwd_dbg-Funktion"
  - "wgetdcwd_dbg-Funktion"
  - "Arbeitsverzeichnis"
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# _getdcwd_dbg, _wgetdcwd_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Debugversionen der [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)\-Funktionen \(nur während des Debuggens verfügbar\).  
  
## Syntax  
  
```  
char *_getdcwd_dbg(    int drive,    char *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wgetdcwd_dbg(    int drive,    wchar_t *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Parameter  
 `drive`  
 Name des Laufwerks.  
  
 `buffer`  
 Speicherort für den Pfad.  
  
 `maxlen`  
 Maximale Länge des Pfads in Zeichen: `char` für `_getdcwd_dbg`und `wchar_t`für `_wgetdcwd_dbg`.  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK`oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger zum Namen der Quelldatei, der die Belegung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Zuordnung angefordert wurde, oder `NULL`.  
  
## Rückgabewert  
 Gibt einen Zeiger auf `buffer` zurück.  Ein `NULL`\-Rückgabewert zeigt einen Fehler an, und `errno` wird entweder auf `ENOMEM` festgelegt, um anzugeben, dass nicht genügend Arbeitsspeicher zum Zuordnen von `maxlen` Bytes vorhanden ist \(wenn ein `NULL`\-Argument als `buffer` angegeben wird\), oder auf `ERANGE`, um anzugeben, dass der Pfad länger als `maxlen` Zeichen ist.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_getdcwd_dbg`\- und `_wgetdcwd_dbg`\-Funktionen sind identisch mit `_getdcwd` und `_wgetdcwd`, außer dass bei Definition von `_DEBUG` diese Funktionen die Debugversion von `malloc` und `_malloc_dbg` verwenden, um Speicher zuzuordnen, wenn `NULL` als `buffer`\-Parameter übergeben wird.  Weitere Informationen finden Sie unter [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 In den meisten Fällen müssen Sie diese Funktionen nicht explizit aufrufen.  Stattdessen können Sie das `_CRTDBG_MAP_ALLOC`\-Flag definieren.  Wenn `_CRTDBG_MAP_ALLOC` definiert ist, werden Aufrufe von `_getdcwd` und `_wgetdcwd` zu `_getdcwd_dbg` bzw. `_wgetdcwd_dbg` neu zugeordnet, wobei `blockType` auf `_NORMAL_BLOCK` festgelegt wird.  Daher müssen Sie diese Funktionen nicht explizit aufrufen, es sei denn, Sie möchten die Heapblöcke als `_CLIENT_BLOCK` markieren.  Weitere Informationen finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tgetdcwd_dbg`|`_getdcwd_dbg`|`_getdcwd_dbg`|`_wgetdcwd_dbg`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_getdcwd_dbg`|\<crtdbg.h\>|  
|`_wgetdcwd_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 <xref:System.Environment.CurrentDirectory*?displayProperty=fullName>  
  
## Siehe auch  
 [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)
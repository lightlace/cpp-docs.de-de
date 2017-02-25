---
title: "_aligned_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_recalloc"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "aligned_recalloc"
  - "_aligned_recalloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_recalloc-Funktion"
  - "_aligned_recalloc-Funktion"
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde und initialisiert den Arbeitsspeicher von 0.  
  
## Syntax  
  
```  
void * _aligned_recalloc(  
   void *memblock,   
   size_t num,  
   size_t size,   
   size_t alignment  
);  
```  
  
#### Parameter  
 \[in\] `memblock`  
 Der aktuelle Speicherblockzeiger.  
  
 \[in\] `num`  
 Die Anzahl der Elemente.  
  
 \[in\] `size`  
 Die Größe in Bytes der einzelnen Elemente.  
  
 \[in\] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
## Rückgabewert  
 `_aligned_recalloc` gibt ein void\-Zeiger zum neu zugeordnete \(und möglicherweise bewegt\) Speicherblock zurück.  Der Rückgabewert ist `NULL`, wenn die Größe \(null und das Pufferargument nicht `NULL` ist oder wenn nicht genügend verfügbarer Speicher gibt, z des Blocks der angegebenen Größe zu erweitern.  Im ersten Fall wird der erste Block freigegeben.  Im zweiten Fall ist der erste Block unverändert.  Der Rückgabewert zeigt auf einem Speicherplatz, der garantiert wird, zum Speichern eines beliebigen Typs Objekt ordnungsgemäß ausgerichtet sind.  Um einen Zeiger auf einen anderen Typ als void abzurufen, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
 Es ist ein Fehler, um den Arbeitsspeicher neu belegen und der Ausrichtung eines Blocks zu ändern.  
  
## Hinweise  
 `_aligned_recalloc` basiert auf `malloc`.  Weitere Informationen zum Verwenden von `_aligned_offset_malloc`, finden Sie unter [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Diese Funktion legt `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlgeschlagen ist oder die angeforderte Größe größer als `_HEAP_MAXREQ` war.  Weitere Informationen zu `errno` finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Darüber hinaus überprüft `_aligned_recalloc` auch die eigenen Parameter.  Wenn `alignment` keine Potenz von 2 ist, Aufrufe dieser Funktion Parameterhandler der ungültige, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `EINVAL` ein.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_aligned_recalloc`|\<malloc.h\>|  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenausrichtung](../../c-runtime-library/data-alignment.md)   
 [\_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)
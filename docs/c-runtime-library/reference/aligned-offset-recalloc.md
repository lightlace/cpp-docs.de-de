---
title: "_aligned_offset_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_offset_recalloc"
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
  - "aligned_offset_recalloc"
  - "_aligned_offset_recalloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_offset_recalloc-Funktion"
  - "_aligned_offset_recalloc-Funktion"
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_offset_recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde und initialisiert den Arbeitsspeicher von 0.  
  
## Syntax  
  
```  
void * _aligned_offset_recalloc(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### Parameter  
 `memblock`  
 Der aktuelle Speicherblockzeiger.  
  
 `num`  
 Anzahl der Elemente.  
  
 `size`  
 Länge in Bytes jedes Elements.  
  
 `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 `offset`  
 Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.  
  
## Rückgabewert  
 `_aligned_offset_recalloc` gibt ein void\-Zeiger zum neu zugeordnete \(und möglicherweise bewegt\) Speicherblock zurück.  Der Rückgabewert ist `NULL`, wenn die Größe \(null und das Pufferargument nicht `NULL` ist oder wenn nicht genügend verfügbarer Speicher gibt, z des Blocks der angegebenen Größe zu erweitern.  Im ersten Fall wird der erste Block freigegeben.  Im zweiten Fall ist der erste Block unverändert.  Der Rückgabewert zeigt auf einem Speicherplatz, der garantiert wird, zum Speichern eines beliebigen Typs Objekt ordnungsgemäß ausgerichtet sind.  Um einen Zeiger auf einen anderen Typ als void abzurufen, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
 `_aligned_offset_recalloc` ist als `__declspec(noalias)` gekennzeichnet und `__declspec(restrict)` heißt, dass die Funktion, die gewährleistet sind globale Variablen nicht zu ändern und der zurückgegebene Zeiger nicht von Alias\-.  Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [Einschränken ein](../../cpp/restrict.md).  
  
## Hinweise  
 Wie [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) können eine `_aligned_offset_recalloc` mit einem Offset innerhalb der Struktur ausgerichtet sind, Struktur.  
  
 `_aligned_offset_recalloc` basiert auf `malloc`.  Weitere Informationen zum Verwenden von `_aligned_offset_malloc`, finden Sie unter [malloc](../../c-runtime-library/reference/malloc.md).  Wenn `memblock``NULL` ist, die Funktionsaufrufe `_aligned_offset_malloc` intern.  
  
 Diese Funktion legt `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlgeschlagen ist, oder wenn die angeforderte Größe \(`num` \* `size`\) ist größer als `_HEAP_MAXREQ` ist.  Weitere Informationen zu `errno` finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Darüber hinaus überprüft `_aligned_offset_recalloc` auch die eigenen Parameter.  Wenn `alignment` keine Potenz von 2 ist, oder wenn `offset` größer oder gleich die angeforderte Größe und den Wert ungleich 0 ist, Aufrufe dieser Funktion Parameterhandler der ungültige, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `EINVAL` ein.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_aligned_offset_recalloc`|\<malloc.h\>|  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenausrichtung](../../c-runtime-library/data-alignment.md)   
 [\_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [\_aligned\_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)
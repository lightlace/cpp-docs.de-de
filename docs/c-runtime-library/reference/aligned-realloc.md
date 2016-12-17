---
title: "_aligned_realloc"
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
  - "_aligned_realloc"
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
  - "_aligned_realloc"
  - "aligned_realloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "aligned_realloc-Funktion"
  - "_aligned_realloc-Funktion"
ms.assetid: 80ce96e8-6087-416f-88aa-4dbb8cb1d218
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde.  
  
## Syntax  
  
```  
void * _aligned_realloc(  
   void *memblock,   
   size_t size,   
   size_t alignment  
);  
```  
  
#### Parameter  
 \[in\] `memblock`  
 Der aktuelle Speicherblockzeiger.  
  
 \[in\] `size`  
 Die Größe der angeforderten Speicherbelegung.  
  
 \[in\] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
## Rückgabewert  
 `_aligned_realloc` gibt ein void\-Zeiger zum neu zugeordnete \(und möglicherweise bewegt\) Speicherblock zurück.  Der Rückgabewert ist `NULL`, wenn die Größe \(null und das Pufferargument nicht `NULL` ist oder wenn nicht genügend verfügbarer Speicher gibt, z des Blocks der angegebenen Größe zu erweitern.  Im ersten Fall wird der erste Block freigegeben.  In das zweite ist der erste Block unverändert.  Der Rückgabewert zeigt auf einem Speicherplatz, der garantiert wird, zum Speichern eines beliebigen Typs Objekt ordnungsgemäß ausgerichtet sind.  Um einen Zeiger auf einen anderen Typ als void abzurufen, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
 Es ist ein Fehler, um den Arbeitsspeicher neu belegen und der Ausrichtung eines Blocks zu ändern.  
  
## Hinweise  
 `_aligned_realloc` basiert auf `malloc`.  Weitere Informationen zum Verwenden von `_aligned_offset_malloc`, finden Sie unter [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Diese Funktion legt `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlgeschlagen ist oder die angeforderte Größe größer als `_HEAP_MAXREQ` war.  Weitere Informationen zu `errno` finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Darüber hinaus überprüft `_aligned_realloc` auch die eigenen Parameter.  Wenn `alignment` keine Potenz von 2 ist, Aufrufe dieser Funktion Parameterhandler der ungültige, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `EINVAL` ein.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_aligned_realloc`|\<malloc.h\>|  
  
## Beispiel  
 Weitere Informationen finden Sie unter [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## Siehe auch  
 [Datenausrichtung](../../c-runtime-library/data-alignment.md)
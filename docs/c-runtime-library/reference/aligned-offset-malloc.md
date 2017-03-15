---
title: "_aligned_offset_malloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_offset_malloc"
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
  - "_aligned_offset_malloc"
  - "aligned_offset_malloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_offset_malloc-Funktion"
  - "aligned_offset_malloc-Funktion"
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _aligned_offset_malloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Belegt in einer angegebenen Grenze integralen Speicher.  
  
## Syntax  
  
```  
void * _aligned_offset_malloc(  
   size_t size,   
   size_t alignment,   
   size_t offset  
);  
```  
  
#### Parameter  
 \[in\] `size`  
 Die Größe der angeforderten Speicherbelegung.  
  
 \[in\] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 \[in\] `offset`  
 Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.  
  
## Rückgabewert  
 Ein Zeiger zum Speicherblock, der belegt wurde, oder `NULL` bei fehlgeschlagenem Vorgang.  
  
## Hinweise  
 `_aligned_offset_malloc` ist nützlich in Situationen, in denen eine Ausrichtung für ein geschachteltes Element erforderlich ist, beispielsweise wenn eine Ausrichtung für eine geschachtelte Klasse erforderlich war.  
  
 `_aligned_offset_malloc` basiert auf `malloc`. Weitere Informationen finden Sie unter [malloc](../../c-runtime-library/reference/malloc.md).  
  
 `_aligned_offset_malloc` ist als `__declspec(noalias)` gekennzeichnet und `__declspec(restrict)` heißt, dass die Funktion, die gewährleistet sind globale Variablen nicht zu ändern und der zurückgegebene Zeiger nicht von Alias\-.  Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [Einschränken ein](../../cpp/restrict.md).  
  
 Diese Funktion legt `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlgeschlagen ist oder die angeforderte Größe größer als `_HEAP_MAXREQ` war.  Weitere Informationen zu `errno` finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Darüber hinaus überprüft `_aligned_offset_malloc` auch die eigenen Parameter.  Wenn `alignment` keine Potenz von 2 ist oder `offset` größer als oder gleich `size` und ungleich 0 ist, ruft diese Funktion den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `EINVAL` ein.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_aligned_offset_malloc`|\<malloc.h\>|  
  
## Beispiel  
 Weitere Informationen finden Sie unter [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## Siehe auch  
 [Datenausrichtung](../../c-runtime-library/data-alignment.md)
---
title: "memcpy, wmemcpy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "memcpy"
  - "wmemcpy"
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
  - "wmemcpy"
  - "memcpy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memcpy-Funktion"
  - "wmemcpy-Funktion"
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# memcpy, wmemcpy
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kopiert Bytes zwischen Puffern.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [memcpy\_s, wmemcpy\_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md).  
  
## Syntax  
  
```  
void *memcpy(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemcpy(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### Parameter  
 `dest`  
 Neuer Puffer.  
  
 `src`  
 Der Puffer, aus dem kopiert werden soll.  
  
 `count`  
 Anzahl der zu kopierenden Zeichen.  
  
## Rückgabewert  
 Der Wert von `dest`.  
  
## Hinweise  
 `memcpy` kopiert `count` Bytes von `src` nach `dest`; `wmemcpy` kopiert `count` Breitzeichen \(zwei Bytes\).  Wenn sich Quell und Ziel überlappen, ist das Verhalten von `memcpy` undefiniert.  Verwendung `memmove` um überlappende Bereiche zu behandeln.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass der Zielpuffer dieselbe Größe wie der Quellpuffer aufweist bzw. größer ist.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!IMPORTANT]
>  Da so viele Pufferüberläufe, und damit einhergehend potenzielle Sicherheitslücken, auf eine falsche Verwendung von `memcpy` zurückzuführen sind, befindet sich diese Funktion unter den von Security Development Lifecycle \(SDL\) "gesperrten" Funktionen.  Möglicherweise stellen Sie fest, dass einige VC\+\+\-Bibliotheksklassen weiterhin `memcpy` verwenden.  Darüber hinaus werden Sie feststellen, dass der VC\+\+\-Compileroptimierer manchmal Aufrufe von `memcpy` ausgibt.  Das Visual C\+\+\-Produkt wird gemäß des SDL\-Prozesses entwickelt; die Verwendung dieser gesperrten Funktion wurde daher sorgfältig geprüft.  Bei Verwendung in der Bibliothek wurden die Aufrufe sorgfältig geprüft, um sicherzustellen, dass Pufferüberläufe über diese Aufrufe nicht zulässig sind.  Im Falle des Compilers werden manchmal bestimmte Codemuster als identisch mit dem Muster von `memcpy` erkannt und daher mit einem Aufruf der Funktion ersetzt.  In solchen Fällen ist die Verwendung von `memcpy` nicht unsicherer als die ursprünglichen Anweisungen; sie wurden einfach für einen Aufruf der leistungsoptimierten `memcpy`\-Funktion optimiert.  Genau wie die Verwendung „sicherer“ CRT\-Funktionen keine Sicherheit garantiert, bedeutet die Verwendung von „gesperrten“ Funktionen keine unmittelbare Gefahr \(diese müssen nur sorgfältig überprüft werden, damit die Sicherheit gewährleistet ist\).  
>   
>  Da die Verwendung von `memcpy` durch den VC\+\+\-Compiler und Bibliotheken so sorgfältig geprüft wurde, sind diese Aufrufe innerhalb des Codes, der ansonsten SDL kompatibel ist, zulässig.  `memcpy`\-Aufrufe, die in den Anwendungsquellcode eingeführt wurden, sind nur kompatibel mit SDL, wenn diese Verwendung von Sicherheitsfachleuten überprüft wurde.  
  
 Die funktionen `memcpy` und `wmemcpy` sind nur veraltet, wenn die Konstante `_CRT_SECURE_DEPRECATE_MEMORY` vor der Einschlussanweisung definiert wird, damit die Funktionen als veraltet markiert werden können, wie zum Beispiel im folgenden Beispiel:  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <memory.h>  
```  
  
 oder  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`memcpy`|\<memory.h\> oder \<string.h\>|  
|`wmemcpy`|\<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Unter [memmove](../../c-runtime-library/reference/memmove-wmemmove.md) finden Sie ein Beispiel zur Verwendung von `memcpy`.  
  
## Siehe auch  
 [Pufferbearbeitung](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)
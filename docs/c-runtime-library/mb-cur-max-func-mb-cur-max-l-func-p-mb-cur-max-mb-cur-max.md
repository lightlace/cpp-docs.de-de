---
title: "___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___mb_cur_max_l_func"
  - "__p___mb_cur_max"
  - "___mb_cur_max_func"
  - "__mb_cur_max"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___mb_cur_max_func"
  - "___mb_cur_max_l_func"
  - "__p___mb_cur_max"
  - "__mb_cur_max"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___mb_cur_max_func"
  - "___mb_cur_max_l_func"
  - "__mb_cur_max"
  - "__p___mb_cur_max"
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Interne CRT\-Funktion.  Ruft die maximale Anzahl von Bytes in einem Multibyte\-Zeichen für das aktuelle oder ein angegebenes Gebietsschema ab.  
  
## Syntax  
  
```cpp  
int ___mb_cur_max_func(void); int ___mb_cur_max_l_func(_locale_t locale); int * __p___mb_cur_max(void); #define __mb_cur_max (___mb_cur_max_func())  
```  
  
#### Parameter  
 Gebietsschema  
 Die Struktur des Gebietsschemas, aus dem das Ergebnis abgerufen werden soll.  Wenn dieser Wert null ist, wird das Gebietsschema des aktuellen Threads verwendet.  
  
## Rückgabewert  
 Die maximale Anzahl von Bytes in einem Multibyte\-Zeichen für das Gebietsschema des aktuelles Threads oder das angegebene Gebietsschema.  
  
## Hinweise  
 Dies ist eine interne Funktion, die die CRT nutzt, um den aktuellen Wert des Makros [MB\_CUR\_MAX](../c-runtime-library/mb-cur-max.md) aus dem lokalen Threadspeicher abzurufen.  Wir empfehlen, das Makro `MB_CUR_MAX` in Ihrem Code für Übertragbarkeit zu nutzen.  
  
 Das Makro `__mb_cur_max` ist ein bequemer Weg zum Aufrufen der Funktion `___mb_cur_max_func()`.  Die Funktion `__p___mb_cur_max` ist für eine Kompatibilität mit Visual C\+\+ 5.0 und früheren Versionen definiert.  
  
 Interne CRT\-Funktionen sind implementierungsspezifisch und mit jeder neuen Veröffentlichung Änderungen unterworfen.  Ihre Verwendung in einem Code wird nicht empfohlen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h\>, \<stdlib.h\>|  
  
## Siehe auch  
 [MB\_CUR\_MAX](../c-runtime-library/mb-cur-max.md)
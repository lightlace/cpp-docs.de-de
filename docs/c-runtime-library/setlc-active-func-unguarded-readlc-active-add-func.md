---
title: "___setlc_active_func, ___unguarded_readlc_active_add_func"
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
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___unguarded_readlc_active_add_func"
  - "___setlc_active_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# ___setlc_active_func, ___unguarded_readlc_active_add_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

VERALTET.  Die CRT exportiert diese internen Funktionen nur zur Aufrechterhaltung der Binärkompatibilität.  
  
## Syntax  
  
```cpp  
int ___setlc_active_func(void); int * ___unguarded_readlc_active_add_func(void);  
```  
  
## Rückgabewert  
 Der zurückgegebene Wert ist nicht signifikant.  
  
## Hinweise  
 Obwohl die internen CRT\-Funktionen `___setlc_active_func` und `___unguarded_readlc_active_add_func` veraltet sind und nicht mehr verwendet werden, werden sie von der CRT\-Bibliothek exportiert, um die Binärkompatibilität aufrechtzuerhalten.  Der ursprüngliche Zweck von `___setlc_active_func` war, die Anzahl der aktuell aktiven Rufe an die Funktion `setlocale` zurückzugeben.  Der ursprüngliche Zweck von `___unguarded_readlc_active_add_func` war, die Anzahl der Funktionen auszugeben, die auf das Gebietsschema verwiesen, ohne es zu sperren.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|Keine|  
  
## Siehe auch  
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
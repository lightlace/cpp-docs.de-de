---
title: "___lc_locale_name_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___lc_locale_name_func"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___lc_locale_name_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_locale_name_func"
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# ___lc_locale_name_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Interne CRT\-Funktion.  Ruft die aktuellen Gebietsschemanamen des Threads ab.  
  
## Syntax  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge, die den aktuellen Gebietsschemanamen des Threads enthält.  
  
## Hinweise  
 `___lc_locale_name_func` ist eine interne CRT\-Funktion, die von anderen CRT\-Funktionen verwendet wird, um den aktuellen Gebietsschemanamen aus dem lokalen Threadspeicher für CRT\-Daten abzurufen.  Diese Information kann auch durch Verwendung der Funktion [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md) oder der [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)\-Funktionen gewonnen werden.  
  
 Interne CRT\-Funktionen sind implementierungsspezifisch und mit jeder neuen Veröffentlichung Änderungen unterworfen.  Ihre Verwendung in einem Code wird nicht empfohlen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`___lc_locale_name_func`|crt\\src\\setlocal.h|  
  
## Siehe auch  
 [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)
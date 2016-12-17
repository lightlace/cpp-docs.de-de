---
title: "___lc_collate_cp_func"
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
  - "___lc_collate_cp_func"
apilocation: 
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___lc_collate_cp_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_collate_cp_func"
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# ___lc_collate_cp_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Interne CRT\-Funktion.  Ruft die aktuelle Sortierungscodeseite des Threads ab.  
  
## Syntax  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## Rückgabewert  
 Die aktuelle Sortierungscodeseite des Threads.  
  
## Hinweise  
 `___lc_collate_cp_func` ist eine interne CRT\-Funktion, die von anderen CRT\-Funktionen verwendet wird, um die aktuelle Sortierungscodeseite aus dem lokalen Threadspeicher für CRT\-Daten abzurufen.  Diese Informationen sind auch über die Funktion [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md) verfügbar.  
  
 Interne CRT\-Funktionen sind implementierungsspezifisch, Änderungen in jeder Version sind vorbehalten.  Die Verwendung dieser Funktionen in Ihrem Code wird nicht empfohlen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`___lc_collate_cp_func`|crt\\src\\setlocal.h|  
  
## Siehe auch  
 [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)
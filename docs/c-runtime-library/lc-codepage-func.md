---
title: "___lc_codepage_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___lc_codepage_func"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lc_codepage_func"
  - "___lc_codepage_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_codepage_func"
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# ___lc_codepage_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Interne CRT\-Funktion.  Ruft die aktuelle Codepage des Threads ab.  
  
## Syntax  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## Rückgabewert  
 Die aktuelle Codepage des Threads.  
  
## Hinweise  
 `___lc_codepage_func` ist eine interne CRT\-Funktion, die von anderen CRT\-Funktionen verwendet wird, um die aktuelle Codepage aus dem lokalen Threadspeicher für CRT\-Daten abzurufen.  Diese Information kann auch durch Verwendung der [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md)\-.Funktion gewonnen werden.  
  
 Eine *Codepage* ist eine Zuordnung von Einzelbyte\- oder Doppelbytecodes zu einzelnen Zeichen.  Zu verschiedenen Codepages gehören verschiedene spezielle Zeichen, die normalerweise für eine Sprache oder eine Gruppe von Sprachen angepasst sind.  Weitere Informationen zu Codepages finden Sie unter [Codepages](../c-runtime-library/code-pages.md).  
  
 Interne CRT\-Funktionen sind implementierungsspezifisch und mit jeder neuen Veröffentlichung Änderungen unterworfen.  Ihre Verwendung in einem Code wird nicht empfohlen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`___lc_codepage_func`|crt\\src\\setlocal.h|  
  
## Siehe auch  
 [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)
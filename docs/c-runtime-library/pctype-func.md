---
title: "__pctype_func"
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
  - "__pctype_func"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__pctype_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__pctype_func"
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# __pctype_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft einen Zeiger auf ein Array Zeichenklassifizierungsinformationen ab.  
  
## Syntax  
  
```cpp  
const unsigned short *__pctype_func(  
   )  
```  
  
## Rückgabewert  
 Ein Zeiger auf ein Array Zeichenklassifizierungsinformationen.  
  
## Hinweise  
 Die Informationen in der ZeichenKlassifikationstabelle sind nur für die interne Verwendung gedacht und werden durch unterschiedliche Funktionen verwendet, die Zeichen vom Typ `char`\- Klasse.  Weitere Informationen finden Sie im Abschnitt `Remarks` von [\_pctype, \_pwctype, \_wctype, \_mbctype, \_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_\_pctype\_func|ctype.h|  
  
## Siehe auch  
 [\_pctype, \_pwctype, \_wctype, \_mbctype, \_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
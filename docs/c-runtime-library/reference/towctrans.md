---
title: "towctrans | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "towctrans"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "towctrans"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "towctrans-Funktion"
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# towctrans
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Transformiert ein Zeichen.  
  
## Syntax  
  
```  
wint_t towctrans(  
   wint_t c,  
   wctrans_t category   
);  
```  
  
#### Parameter  
 `c`  
 Das Zeichen, das Sie transformieren möchten.  
  
 `category`  
 Ein Bezeichner, dem der Rückgabewert von [wctrans](../../c-runtime-library/reference/wctrans.md) enthält.  
  
## Rückgabewert  
 Das Zeichen `c`, nach `towctrans` verwendet die Transformationsregel in `category`.  
  
## Hinweise  
 Der Wert `category` muss einen früheren erfolgreichen Aufruf von [wctrans](../../c-runtime-library/reference/wctrans.md) zurückgegeben werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`towctrans`|\<wctype.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Siehe `wctrans` für ein Beispiel, das `towctrans` verwendet.  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)
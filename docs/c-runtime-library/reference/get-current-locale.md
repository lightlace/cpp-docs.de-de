---
title: "_get_current_locale"
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
  - "_get_current_locale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_current_locale"
  - "__get_current_locale"
  - "_get_current_locale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__get_current_locale-Funktion"
  - "_get_current_locale-Funktion"
  - "get_current_locale-Funktion"
  - "Gebietsschemas, Abrufen von Informationen zu"
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# _get_current_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft ein Gebietsschemaobjekt ab, der das aktuelle Gebietsschema darstellt.  
  
## Syntax  
  
```  
_locale_t _get_current_locale(void);  
```  
  
## Rückgabewert  
 Ein Gebietsschemaobjekt, welches das aktuelle Gebietsschema darstellt.  
  
## Hinweise  
 Die Funktion `_get_current_locale` ruft das derzeit festgelegte Gebietsschema für den Thread ab und gibt einen Gebietsschemaobjekt zurück, das dieses Gebietsschema darstellt.  
  
 Der vorherige Name dieser Funktion, `__get_current_locale` \(mit zwei führenden Unterstrichen\) ist veraltet.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_current_locale`|\<locale.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Keine Entsprechung.  
  
## Siehe auch  
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)
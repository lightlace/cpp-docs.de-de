---
title: "wctype | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wctype"
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
  - "wctype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wctype-Funktion"
  - "Breitzeichen"
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# wctype
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt eine Klassifizierungsregel für Zeichenkodes.  
  
## Syntax  
  
```  
wctype_t wctype(  
   const char * property   
);  
```  
  
#### Parameter  
 `property`  
 Eigenschaftenzeichenfolge.  
  
## Rückgabewert  
 Wenn die Kategorie `LC_CTYPE` des aktuellen Gebietsschemas keine Klassifizierungsregel definiert, deren Name mit der Eigenschaftenzeichenfolge `property` übereinstimmt, Funktionsrückgaben null.  Andernfalls wird ein Wert ungleich 0 \(null\) zurück, der für die Verwendung als zweites Argument für einen nachfolgenden Aufruf für [towctrans](../../c-runtime-library/reference/towctrans.md) erstellen.  
  
## Hinweise  
 Die Funktion bestimmt eine Klassifizierungsregel für Zeichenkodes.  Die folgenden Paare von Aufrufen noch das gleiche Verhalten in allen Gebietsschemas \(jedoch eine Implementierung kann zusätzliche Klassifizierungsregeln sogar im "C " \- Gebietsschema definieren\):  
  
|Funktion|Entspricht|  
|--------------|----------------|  
|`iswalnum(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alnum" ) )`|  
|`iswalpha(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alpha" ) )`|  
|`iswcntrl(`  `c`  `)`|`iswctype(`  `c` `, wctype( "cntrl" ) )`|  
|`iswdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "digit" ) )`|  
|`iswgraph(`  `c`  `)`|`iswctype(`  `c` `, wctype( "graph" ) )`|  
|`iswlower(`  `c`  `)`|`iswctype(`  `c` `, wctype( "lower" ) )`|  
|`iswprint(`  `c`  `)`|`iswctype(`  `c` `, wctype( "print" ) )`|  
|`iswpunct(`  `c`  `)`|`iswctype(`  `c` `, wctype( "punct" ) )`|  
|`iswspace(`  `c`  `)`|`iswctype(`  `c` `, wctype( "space" ) )`|  
|`iswupper(`  `c`  `)`|`iswctype(`  `c` `, wctype( "upper" ) )`|  
|`iswxdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "xdigit" ) )`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wctype`|\<wctype.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)
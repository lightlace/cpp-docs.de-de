---
title: "c16rtomb c32rtomb1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "c16rtomb"
  - "c32rtomb"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c16rtomb"
  - "c32rtomb"
  - "uchar/c16rtomb"
  - "uchar/c32rtomb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "c16rtomb-Funktion"
  - "c32rtomb-Funktion"
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# c16rtomb, c32rtomb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert ein UTF\-16\- oder UTF\-32\-Breitzeichen in ein Multibytezeichen im aktuellen Gebietsschema.  
  
## Syntax  
  
```  
size_t c16rtomb(  
    char *mbchar,   
    char16_t wchar,  
    mbstate_t *state  
);  
size_t c32rtomb(  
    char *mbchar,   
    char32_t wchar,  
    mbstate_t *state  
);  
```  
  
#### Parameter  
 \[out\] `mbchar`  
 Zeiger auf ein Array zum Speichern des in Multibyte konvertierten Zeichens.  
  
 \[in\] `wchar`  
 Ein zu konvertierendes Breitzeichen.  
  
 \[in, out\] `state`  
 Ein Zeiger auf ein `mbstate_t`\-Objekt.  
  
## Rückgabewert  
 Die Anzahl der im Arrayobjekt `mbchar` gespeicherten Bytes, einschließlich eventueller UMSCHALT\-Sequenzen. Wenn `wchar` kein gültiges Breitzeichen ist, wird der Wert \(`size_t`\)\(\-1\) zurückgegeben, `errno` wird auf `EILSEQ` festgelegt und der Wert von `state` ist nicht angegeben.  
  
## Hinweise  
 Die `c16rtomb`\-Funktion konvertiert das UTF\-16\-Zeichen `wchar` in die äquivalente Multibytesequenz aus halbbreiten Zeichen im aktuellen Gebietsschema. Wenn `mbchar` kein Nullzeiger ist, speichert die Funktion die konvertierte Sequenz im Arrayobjekt, auf das `mbchar` verweist. Bis zu `MB_CUR_MAX` Bytes werden in `mbchar` gespeichert, und `state` wird auf den resultierenden Multibyte\-UMSCHALT\-Status festgelegt.    Wenn `wchar` ein breites NULL\-Zeichen ist, wird eine Sequenz gespeichert, die zum Wiederherstellen des ursprünglichen UMSCHALT\-Status erforderlich ist, ggf. gefolgt vom NULL\-Zeichen, und `state` wird auf den ursprünglichen Konvertierungsstatus festgelegt. Die `c32rtomb`\-Funktion ist identisch, konvertiert aber ein UTF\-32\-Zeichen.  
  
 Wenn `mbchar` ein Nullzeiger ist, ist das Verhalten gleichbedeutend mit einem Aufruf der Funktion, die `mbchar` durch einen internen Puffer und `wchar` durch ein breites NULL\-Zeichen ersetzt.  
  
 Das `state`\-Konvertierungsstatusobjekt ermöglicht Ihnen, aufeinander folgende Aufrufe dieser Funktion und anderer erneut startbarer Funktionen vorzunehmen, bei denen der UMSCHALT\-Status der Multibyteausgabezeichen erhalten bleibt. Wenn Sie erneut startbare und nicht erneut startbare Funktionen gemischt verwenden oder zwischen zwei Aufrufen von neu startbaren Funktionen ein Aufruf von `setlocale` erfolgt, sind die Ergebnisse undefiniert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`c16rtomb`, `c32rtomb`|C, C\+\+: \<uchar.h\>|  
  
 Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtoc16, mbrtoc32](../../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)
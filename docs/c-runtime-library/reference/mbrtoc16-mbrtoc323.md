---
title: "mbrtoc16, mbrtoc32"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "mbrtoc16"
  - "mbrtoc32"
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
  - "mbrtoc16"
  - "mbrtoc32"
  - "uchar/mbrtoc16"
  - "uchar/mbrtoc32"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "mbrtoc16-Funktion"
  - "mbrtoc32-Funktion"
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# mbrtoc16, mbrtoc32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Übersetzt das erste Multibytezeichen in einer schmalen Zeichenfolge in das entsprechende UTF\-16\- oder UTF\-32\-Zeichen.  
  
## Syntax  
  
```  
size_t mbrtoc16(   
   char16_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
size_t mbrtoc32(  
   char32_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
```  
  
#### Parameter  
 `destination`  
 Zeiger auf die `char16_t`\- oder `char32_t`\-Entsprechung des zu konvertierenden Multibytezeichens. Wenn der Wert NULL ist, speichert die Funktion keinen Wert.  
  
 `source`  
 Zeiger auf die zu konvertierende Multibyte\-Zeichenfolge.  
  
 `max_bytes`  
 Die maximale Anzahl Bytes in `source`, die für ein zu konvertierendes Zeichen untersucht werden sollen. Dabei sollte es sich um einen Wert zwischen 1 und der Anzahl Bytes handeln, die in `source` verbleiben, einschließlich eines eventuellen Nullterminators.  
  
 `state`  
 Zeiger auf ein `mbstate_t`\-Konvertierungsstatusobjekt, das verwendet wird, um die Multibyte\-Zeichenfolge in Form von einem oder mehreren Ausgabezeichen zu interpretieren.  
  
## Rückgabewert  
 Im Erfolgsfall wird der Wert der ersten erfüllten Bedingung zurückgegeben, auf der Grundlage des aktuellen `state`\-Werts:  
  
|Wert|Bedingung|  
|----------|---------------|  
|0|Die nächsten `max_bytes` oder weniger Zeichen, die aus `source` konvertiert werden, entsprechen dem breiten Nullzeichen, das den gespeicherten Wert darstellt, wenn `destination` nicht NULL ist.<br /><br /> `state` enthält den UMSCHALT\-Status zu Anfang.|  
|Zwischen 1 und `max_bytes` einschließlich|Der zurückgegebene Wert ist die Anzahl Bytes von `source`, die ein gültiges Multibytezeichen bilden. Das konvertierte Breitzeichen wird gespeichert, wenn `destination` nicht NULL ist.|  
|\-3|Das nächste Breitzeichen, das sich aus einem vorhergehenden Aufruf der Funktion ergab, wurde in `destination` gespeichert, falls `destination` nicht NULL ist. Keine Bytes von `source` werden von diesem Aufruf der Funktion verbraucht.<br /><br /> Wenn `source` auf ein Multibytezeichen verweist, für dessen Darstellung mehr als ein Breitzeichen erforderlich ist \(z. B. ein Ersatzzeichenpaar\), wird der `state`\-Wert aktualisiert, sodass der nächste Funktionsaufruf das zusätzliche Zeichen ausgibt.|  
|\-2|Die nächsten `max_bytes`\-Bytes stellen ein unvollständiges, aber möglicherweise gültiges Multibytezeichen dar. Es wird kein Wert in `destination` gespeichert. Dieses Ergebnis kann auftreten, wenn `max_bytes` 0 \(null\) ist.|  
|\-1|Es ist ein Codierungsfehler aufgetreten. Die nächsten `max_bytes` oder weniger Bytes tragen nicht zu einem vollständigen und gültigen Multibytezeichen bei. Es wird kein Wert in `destination` gespeichert.<br /><br /> `EILSEQ` ist in `errno` gespeichert, und der Konvertierungsstatus `state` ist nicht angegeben.|  
  
## Hinweise  
 Die `mbrtoc16`\-Funktion liest bis zu `max_bytes` Bytes aus `source`, um das erste vollständige gültige Multibytezeichen zu finden, und speichert dann das entsprechende UTF\-16\-Zeichen in `destination`. Die Quellbytes werden gemäß dem Multibyte\-Gebietsschema des aktuellen Threads interpretiert. Wenn für das Multibytezeichen mehr als ein UTF\-16\-Ausgabezeichen erforderlich ist, wie etwa bei einem Ersatzzeichenpaar, wird der `state`\-Wert so festgelegt, dass beim nächsten Aufruf von `mbrtoc16` das nächste UTF\-16\-Zeichen in `destination` gespeichert wird. Die `mbrtoc32`\-Funktion ist identisch, jedoch wird die Ausgabe als UTF\-32\-Zeichen gespeichert.  
  
 Wenn `source` NULL ist, geben diese Funktionen das Äquivalent eines Aufrufs mit den Argumenten `NULL` für `destination`, `""` für `source` und `1` für `max_bytes` zurück. Die übergebenen Werte von `destination` und `max_bytes` werden ignoriert.  
  
 Wenn `source` nicht NULL ist, beginnt die Funktion am Anfang der Zeichenfolge und untersucht bis zu `max_bytes` Bytes, um die erforderliche Anzahl Bytes zum Abschließen des nächsten Multibytezeichens zu bestimmen, einschließlich eventueller Umschaltsequenzen. Wenn die untersuchten Bytes ein gültiges und vollständiges Multibytezeichen enthalten, konvertiert die Funktion das Zeichen in das bzw. die entsprechende\(n\) 16 Bit oder 32 Bit breite\(n\) Zeichen. Wenn `destination` nicht NULL ist, speichert die Funktion das erste \(und möglicherweise einzige\) Ergebniszeichen im Ziel. Wenn weitere Ausgabezeichen erforderlich sind, wird ein Wert in `state` festgelegt, damit nachfolgende Aufrufe der Funktion die zusätzlichen Zeichen ausgeben und den Wert \-3 zurückgeben. Wenn keine weiteren Ausgabezeichen erforderlich sind, wird `state` auf den ursprünglichen Umschaltzustand zurückgesetzt.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`mbrtoc16`, `mbrtoc32`|\<uchar.h\>|\<cuchar\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [c16rtomb, c32rtomb](../../c-runtime-library/reference/c16rtomb-c32rtomb1.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md)   
 [mbsrtowcs\_s](../../c-runtime-library/reference/mbsrtowcs-s.md)
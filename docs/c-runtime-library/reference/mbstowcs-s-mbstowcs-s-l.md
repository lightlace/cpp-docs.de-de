---
title: "mbstowcs_s, _mbstowcs_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
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
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbstowcs_s_l-Funktion"
  - "mbstowcs_s-Funktion"
  - "mbstowcs_s_l-Funktion"
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# mbstowcs_s, _mbstowcs_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Sequenz von Mehrbytezeichen zu der entsprechenden Reihenfolge von Breitzeichen.  Versionen von [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count   
);  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `pReturnValue`  
 Die Anzahl der Zeichen konvertiert.  
  
 \[out\] `wcstr`  
 Adresse des Puffers für Zurückhalten konvertierte Zeichenfolge mit Breitzeichen.  
  
 \[in\] `sizeInWords`  
 Die Größe des Puffers `wcstr` mit den Wörtern.  
  
 \[in\]`mbstr`  
 Die Adresse einer Sequenz NULL beendete Mehrbytezeichen.  
  
 \[in\] `count`  
 Die maximale Anzahl im `wcstr` Puffer, ohne das abschließende NULL\-Zeichen zu lagern den Breitzeichen, oder [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 \[in\] `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler.  
  
|Fehlerstatus|Rückgabewert und `errno`|  
|------------------|------------------------------|  
|`wcstr` ist `NULL` und `sizeInWords` \> 0|`EINVAL`|  
|`mbstr` ist `NULL`|`EINVAL`|  
|Der Zielpuffer ist zu klein, die konvertierte Zeichenfolge zu enthalten \(es sei denn, `count` ; `_TRUNCATE` ist siehe Hinweise\) unten|`ERANGE`|  
|`wcstr` ist nicht `NULL` und `sizeInWords` \=\= 0|`EINVAL`|  
  
 Wenn diese Bedingungen auftritt, wird die ungültige Parameterausnahme aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, gibt die Funktion einen Fehlercode zurück und legt `errno` fest, wie in der Tabelle angegeben.  
  
## Hinweise  
 Die `mbstowcs_s`\-Funktion konvertiert eine Zeichenfolge aus den Mehrbytezeichen, auf die `mbstr` der Breitzeichen dargestellt werden, die im Puffer gespeichert werden, auf den durch `wcstr` gezeigt wird.  Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine dieser Bedingungen erfüllt ist:  
  
-   Ein Mehrbytenull\-zeichen auftritt  
  
-   Ein NULL\-Makro Mehrbytezeichen auftritt  
  
-   Die Anzahl der Breitzeichen, die im `wcstr` Puffer gespeichert werden, entspricht `count`.  
  
 Die Zielzeichenfolge ist immer auf NULL enden \(selbst im Falle eines Fehlers.\)  
  
 Wenn `count` den speziellen Wert [\_TRUNCATE](../../c-runtime-library/truncate.md) ist, konvertiert `mbstowcs_s` so weit der Zeichenfolge, wie in den Zielpuffer passt, wobei Platz für einen Nullterminator weiterhin beibehalten.  
  
 Wenn `mbstowcs_s` erfolgreich die Quellzeichenfolge konvertiert, wird die Größe in Breitzeichen der konvertierten Zeichenfolge, einschließlich das NULL\-Zeichen, in `*`\(ein `pReturnValue` bereit gestelltes `pReturnValue` nicht `NULL` ist\).  Dies tritt auf, `wcstr`, wenn das Argument `NULL` und bietet eine Möglichkeit, die erforderliche Puffergröße zu ermitteln.  Beachten Sie, dass, wenn `wcstr``NULL` ist, die `count` ignoriert wird, und `sizeInWords` muss 0 sein.  
  
 Wenn `mbstowcs_s` ein ungültiges Mehrbytezeichen stößt, gibt es 0 in `*``pReturnValue`, legt den Zielpuffer auf eine leere Zeichenfolge fest, wird `errno` auf `EILSEQ` festgelegt und `EILSEQ` zurückgegeben.  
  
 Wenn die Sequenzen, die von `mbstr` und `wcstr` Überlappung, das Verhalten von `mbstowcs_s` dargestellt werden, die definiert.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `wcstr` und `mbstr` nicht überschneiden und dass `count` richtig die Anzahl Mehrbytezeichen an verschiedenen mitgeteilt.  
  
 `mbstowcs_s` verwendet das aktuelle Gebietsschema jedes gebietsschemaabhängigen Verhalten; `_mbstowcs_s_l` ist identisch, es verwendet das Gebietsschema, das ein\- stattdessen übergeben wird.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`mbstowcs_s`|\<stdlib.h\>|  
|`_mbstowcs_s_l`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)
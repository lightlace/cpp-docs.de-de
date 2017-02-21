---
title: "_ultoa_s, _ultow_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ultow_s"
  - "_ultoa_s"
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
  - "_ultow_s"
  - "ultoa_s"
  - "ultow_s"
  - "_ultoa_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ultoa_s-Funktion"
  - "_ultow_s-Funktion"
  - "Konvertieren von ganzen Zahlen"
  - "Konvertieren von Zahlen, zu Zeichenfolgen"
  - "Ganze Zahlen, Konvertieren"
  - "ultoa_s-Funktion"
  - "ultow_s-Funktion"
ms.assetid: 606ce905-6752-46ac-a15a-bdc22920e1d4
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _ultoa_s, _ultow_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine lange ganze Zahl ohne Vorzeichen in eine Zeichenfolge.  Diese Versionen von [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _ultoa_s(  
    unsigned long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ultow_s(  
    unsigned long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ultoa_s(  
    unsigned long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ultow_s(  
    unsigned long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### Parameter  
 `value`  
 Zu konvertierende Zahl.  
  
 `str`  
 Zeichenfolgenergebnis.  
  
 `sizeOfstr`  
 Die Größe `str` in Bytes für `_ultoa_s` oder in Worten für `_ultow_s`.  
  
 `radix`  
 Basis für `value`.  
  
## Rückgabewert  
 Null wenn die Funktion erfolgreich oder ein Fehlercode war.  
  
## Hinweise  
 Die `_ultoa_s`\-Funktion konvertiert die Ziffern von `value` zu einer auf NULL endende Zeichenfolge und speichert das Ergebnis \(bis zu 33 Bytes\) in `str`.  Das Argument `radix` gibt der Basis von `value`, die im Bereich 2 \- 36 sein muss.  `_ultow_s` ist eine Breitzeichen\-Version von `_ultoa_s`; das zweite Argument `_ultow_s` ist Zeichenfolgen mit Breitzeichen.  
  
 Wenn `str` ein `NULL` Zeiger ist oder wenn `sizeOfstr` kleiner oder gleich null ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, geben diese Funktionen festgelegtem \-1 und `errno` auf `EINVAL`  ergibt oder, wenn `value` oder `str` aus Bereich eine lange ganze Zahl out, diese Funktionen \-1 zurückgeben und `errno` auf `ERANGE` festlegen.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_ultot_s`|`_ultoa_s`|`_ultoa_s`|`_ultow_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ultoa_s`|\<stdlib.h\>|  
|`_ultow_s`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [\_ltoa, \_ltow](../../c-runtime-library/reference/ltoa-ltow.md)   
 [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)   
 [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)
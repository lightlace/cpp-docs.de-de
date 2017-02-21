---
title: "_ltoa_s, _ltow_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ltoa_s"
  - "_ltow_s"
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
  - "_ltow_s"
  - "_ltoa_s"
  - "ltoa_s"
  - "ltow_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ltoa_s-Funktion"
  - "_ltow_s-Funktion"
  - "Konvertieren von ganzen Zahlen"
  - "Konvertieren von Zahlen, zu Zeichenfolgen"
  - "Konvertierung einer langen ganzen Zahl in eine Zeichenfolge"
  - "ltoa_s-Funktion"
  - "ltow_s-Funktion"
ms.assetid: d7dc61ea-1ccd-412d-b262-555a58647386
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _ltoa_s, _ltow_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine lange ganze Zahl in eine Zeichenfolge.  Diese Versionen von [\_ltoa, \_ltow](../../c-runtime-library/reference/ltoa-ltow.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _ltoa_s(  
    long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ltow_s(  
    long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ltoa_s(  
    long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ltow_s(  
    long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### Parameter  
 `value`  
 Zu konvertierende Zahl.  
  
 `str`  
 Puffer für die Ergebniszeichenfolge.  
  
 `sizeOfstr`  
 Größe `str` in Bytes für `_ltoa_s` oder in Worten für `_ltow_s`.  
  
 `radix`  
 Basis für `value`.  
  
## Rückgabewert  
 Null wenn die Funktion erfolgreich oder ein Fehlercode war.  
  
## Hinweise  
 Die `_ltoa_s`\-Funktion konvertiert die Ziffern von `value` zu einer auf NULL endende Zeichenfolge und speichert das Ergebnis \(bis zu 33 Bytes\) in `str`.  Das Argument `radix` gibt der Basis von `value`, die im Bereich 2 \- 36 sein muss.  Wenn `radix` entspricht 10 und `value` negativ ist, wird das erste Zeichen der gespeicherten Zeichenfolge das Minuszeichen \(\-\).  `_ltow_s` ist eine Breitzeichen\-Version von `_ltoa_s`; das zweite Argument `_ltow_s` ist Zeichenfolgen mit Breitzeichen.  
  
 Wenn `str` ein Zeiger ist, `NULL` oder `sizeOfstr` kleiner oder gleich null ist, rufen diese Funktionen einen ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, geben diese Funktionen festgelegtem \-1 und `errno` auf `EINVAL`  ergibt oder, wenn `value` oder `str` aus Bereich eine lange ganze Zahl out, diese Funktionen \-1 zurückgeben und `errno` auf `ERANGE` festlegen.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_ltot_s`|`_ltoa_s`|`_ltoa_s`|`_ltow_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ltoa_s`|\<stdlib.h\>|  
|`_ltow_s`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [\_ultoa\_s, \_ultow\_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md)
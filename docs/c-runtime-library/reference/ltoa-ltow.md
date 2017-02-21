---
title: "_ltoa, _ltow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ltoa"
  - "_ltow"
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
  - "ltow"
  - "_ltot"
  - "_ltoa"
  - "_ltow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ltoa-Funktion"
  - "_ltow-Funktion"
  - "Konvertieren von ganzen Zahlen"
  - "Konvertieren von Zahlen, zu Zeichenfolgen"
  - "Konvertierung einer langen ganzen Zahl in eine Zeichenfolge"
  - "ltoa-Funktion"
  - "ltow-Funktion"
ms.assetid: 14036104-2c25-4759-87c0-918ed8521e47
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _ltoa, _ltow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine lange ganze Zahl in eine Zeichenfolge.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_ltoa\_s, \_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md).  
  
## Syntax  
  
```  
char *_ltoa(  
   long value,  
   char *str,  
   int radix   
);  
wchar_t *_ltow(  
   long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ltoa(  
   long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ltow(  
   long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### Parameter  
 `value`  
 Zu konvertierende Zahl.  
  
 `str`  
 Zeichenfolgenergebnis.  
  
 `radix`  
 Basis für `value`.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf `str` zurück.  Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Die `_ltoa`\-Funktion konvertiert die Ziffern von `value` zu einer auf NULL endende Zeichenfolge und speichert das Ergebnis \(bis zu 33 Bytes\) in `str`.  Das Argument `radix` gibt der Basis von `value`, die im Bereich 2 \- 36 sein muss.  Wenn `radix` entspricht 10 und `value` negativ ist, wird das erste Zeichen der gespeicherten Zeichenfolge das Minuszeichen \(\-\).  `_ltow` ist eine Breitzeichen\-Version von `_ltoa`; das zweite Argument und der Rückgabewert von `_ltow` sind Zeichenfolgen mit Breitzeichen.  Jede dieser Funktionen ist Microsoft\-spezifische.  
  
> [!IMPORTANT]
>  Um Pufferüberläufe zu verhindern, muss der `str`\-Puffer groß genug für die konvertierten Ziffern, das abschließende NULL\-Zeichen sowie ein Zeichen sein.  
  
 In C\+\+ gibt es für diese Funktionen Vorlagenüberladungen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ltoa`|\<stdlib.h\>|  
|`_ltow`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [\_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md).  
  
## .NET Framework-Entsprechung  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [\_ultoa, \_ultow](../../c-runtime-library/reference/ultoa-ultow.md)
---
title: "tolower, _tolower, towlower, _tolower_l, _towlower_l"
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
  - "_tolower_l"
  - "towlower"
  - "tolower"
  - "_tolower"
  - "_towlower_l"
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
  - "_totlower"
  - "tolower"
  - "_tolower"
  - "towlower"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tolower-Funktion"
  - "_tolower_l-Funktion"
  - "_totlower-Funktion"
  - "_towlower_l-Funktion"
  - "Groß- und Kleinschreibung, Konvertieren"
  - "Zeichen, Konvertieren"
  - "Kleinbuchstaben, Konvertieren in"
  - "Zeichenfolgenkonvertierung, Groß- und Kleinschreibung"
  - "Zeichenfolgenkonvertierung, in verschiedene Zeichen"
  - "tolower-Funktion"
  - "tolower_l-Funktion"
  - "totlower-Funktion"
  - "towlower-Funktion"
  - "towlower_l-Funktion"
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# tolower, _tolower, towlower, _tolower_l, _towlower_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert ein Zeichen in Kleinbuchstaben.  
  
## Syntax  
  
```  
int tolower(  
   int c   
);  
int _tolower(  
   int c   
);  
int towlower(  
   wint_t c   
);  
int _tolower_l(  
   int c,  
   _locale_t locale   
);  
int _towlower_l(  
   wint_t c,  
   _locale_t locale   
);  
```  
  
#### Parameter  
 \[in\] `c`  
 Zu konvertierendes Zeichen.  
  
 \[in\] `locale`  
 Für gebietsschemaspezifische Übersetzung zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Routinen konvertiert eine Kopie von `c` in Kleinbuchstaben, wenn die Konvertierung möglich ist, und gibt das Ergebnis zurück.  Es gibt keinen Rückgabewert, der reserviert wird, um einen Fehler anzugeben.  
  
## Hinweise  
 Jede dieser Routinen konvertiert einen angegebenen Großbuchstaben in einen Kleinbuchstaben, sofern möglich und relevant ist.  Die Unterscheidung der Groß\-\/Kleinschreibung von `towlower` ist gebietsschemaspezifisch.  Nur die Zeichen, die dem aktuellen Gebietsschema relevant sind, werden ggf. geändert.  Die Features ohne das Suffix `_l` verwenden das gerade angegebene Gebietsschema.  Die Versionen dieser Funktionen, die das `_l` \- Suffix das Gebietsschema als Parameter akzeptieren und das statt des momentan festgelegten Gebietsschema verwenden.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Damit `_tolower` erwarteten Ergebnisse gibt, [\_\_isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) und [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) muss jeweils Rückholwert ungleich 0.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_totlower`|`tolower`|`_mbctolower`|`towlower`|  
|`_totlower_l`|`_tolower_l`|`_mbctolower_l`|`_towlower_l`|  
  
> [!NOTE]
>  `_tolower_l` und `_towlower_l` haben keine Gebietsschemaabhängigkeit und sind nicht für den direkten Aufruf vorgesehen.  Sie werden zur internen Verwendung von `_totlower_l` bereitgestellt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`tolower`|\<ctype.h\>|  
|`_tolower`|\<ctype.h\>|  
|`towlower`|\<ctype.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Siehe das Beispiel in [auf Funktionen](../../c-runtime-library/to-functions.md).  
  
## .NET Framework-Entsprechung  
 [System::Char::ToLower](https://msdn.microsoft.com/en-us/library/system.char.tolower.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [to\-Funktionen](../../c-runtime-library/to-functions.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
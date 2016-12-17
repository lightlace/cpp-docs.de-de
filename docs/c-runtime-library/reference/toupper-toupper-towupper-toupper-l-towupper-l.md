---
title: "toupper, _toupper, towupper, _toupper_l, _towupper_l"
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
  - "_toupper_l"
  - "towupper"
  - "toupper"
  - "_towupper_l"
  - "_toupper"
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
  - "towupper"
  - "_toupper"
  - "_totupper"
  - "toupper"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_totupper-Funktion"
  - "_toupper-Funktion"
  - "_toupper_l-Funktion"
  - "_towupper_l-Funktion"
  - "Groß- und Kleinschreibung, Konvertieren"
  - "Zeichen, Konvertieren"
  - "Zeichenfolgenkonvertierung, Groß- und Kleinschreibung"
  - "Zeichenfolgenkonvertierung, in verschiedene Zeichen"
  - "totupper-Funktion"
  - "toupper-Funktion"
  - "toupper_l-Funktion"
  - "towupper-Funktion"
  - "towupper_l-Funktion"
  - "Großbuchstaben, Konvertieren von Zeichenfolgen in"
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# toupper, _toupper, towupper, _toupper_l, _towupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertieren Sie Zeichen in Großbuchstaben.  
  
## Syntax  
  
```  
int toupper(  
   int c   
);  
int _toupper(  
   int c   
);  
int towupper(  
   wint_t c   
);  
int _toupper_l(  
   int c ,  
   _locale_t locale  
);  
int _towupper_l(  
   wint_t c ,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu konvertierendes Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Routinen konvertiert eine Kopie von `c`, wenn möglich, und gibt das Ergebnis aus.  
  
 Wenn `c` für das ein Breitzeichen `iswlower` ist nicht 0 ist und es ist ein entsprechendes Breitzeichen, für das ein `iswupper` ungleich 0 ist, `towupper` den entsprechenden Breitzeichen zurückgibt; andernfalls `towupper` zurückgibt `c` unverändert.  
  
 Es gibt keinen Rückgabewert, der reserviert wird, um einen Fehler anzugeben.  
  
 Damit `toupper` erwarteten Ergebnisse gibt, [\_\_isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) und [islower](../../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md) muss jeweils Rückholwert ungleich 0.  
  
## Hinweise  
 Jede dieser Routinen konvertiert einen angegebenen Kleinbuchstaben zu einem Großbuchstaben, wenn möglich und entsprechend.  Die Unterscheidung der Groß\-\/Kleinschreibung von `towupper` ist gebietsschemaspezifisch.  Nur die Zeichen, die dem aktuellen Gebietsschema relevant sind, werden ggf. geändert.  Die Features ohne das Suffix `_l`  verwenden das gerade angegebene Gebietsschema.  Die Versionen dieser Funktionen mit dem Suffix `_l`  nehmen das Gebietsschema als Parameter verwenden und die aktuell festgelegten anstelle des Gebietsschemas.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Damit `toupper` erwarteten Ergebnisse gibt, [\_\_isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) und [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) muss jeweils Rückholwert ungleich 0.  
  
 [Datenkonvertierungs\-Routinen](../../c-runtime-library/data-conversion.md)  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`_toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
> [!NOTE]
>  `_toupper_l` und `_towupper_l` haben keine Gebietsschemaabhängigkeit und sind nicht für den direkten Aufruf vorgesehen.  Sie werden zur internen Verwendung von `_totupper_l` bereitgestellt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`toupper`|\<ctype.h\>|  
|`_toupper`|\<ctype.h\>|  
|`towupper`|\<ctype.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Siehe das Beispiel in [auf Funktionen](../../c-runtime-library/to-functions.md).  
  
## .NET Framework-Entsprechung  
 [System::Char::ToUpper](https://msdn.microsoft.com/en-us/library/system.char.toupper.aspx)  
  
## Siehe auch  
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [to\-Funktionen](../../c-runtime-library/to-functions.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
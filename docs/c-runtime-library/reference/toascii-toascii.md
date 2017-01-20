---
title: "ToAscii __toascii"
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
  - "__toascii"
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
  - "__toascii"
  - "toascii"
  - "ctype/toascii"
  - "ctype/__toascii"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "toascii-Funktion"
  - "zeichenfolgenkonvertierung in ASCII-Zeichen"
  - "__toascii-Funktion"
  - "ASCII-Zeichen konvertieren in"
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# ToAscii __toascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert Zeichen in 7\-Bit\-ASCII durch Abschneiden.  
  
## Syntax  
  
```  
int __toascii(  
   int c   
);  
#define toascii __toascii  
```  
  
#### Parameter  
 `c`  
 Zu konvertierendes Zeichen.  
  
## Rückgabewert  
 `__toascii` Konvertiert den Wert der `c` und den 7\-Bit\-ASCII liegen, und das Ergebnis zurückgibt. Es ist kein Rückgabewert reserviert einen Fehler an.  
  
## Hinweise  
 Die `__toascii` Routine konvertiert das angegebene Zeichen in ASCII\-Zeichen mit den 7 niederwertigen Bits abgeschnitten. Keine anderen Transformation angewendet wird.  
  
 Die `__toascii` Routine als ein Makro definiert ist, es sei denn, die \_CTYPE\_DISABLE\_MACROS Präprozessormakro definiert ist. Für die Abwärtskompatibilität `toascii` wird als Makro definiert nur, wenn [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) ist nicht definiert oder wird definiert als 0; andernfalls ist es nicht definiert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`toascii`, `__toascii`|C: \< ctype.h \><br /><br /> C\+\+: \< Cctype \> oder \< ctype.h \>|  
  
 Die `toascii` \-Makro ist eine Erweiterung POSIX und `__toascii` ist eine Microsoft\-spezifische Implementierung der POSIX\-Erweiterung. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [to\-Funktionen](../../c-runtime-library/to-functions.md)
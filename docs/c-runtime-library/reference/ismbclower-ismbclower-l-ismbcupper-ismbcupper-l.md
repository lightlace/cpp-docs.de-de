---
title: "_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l"
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
  - "_ismbclower"
  - "_ismbclower_l"
  - "_ismbcupper_l"
  - "_ismbcupper"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ismbcupper"
  - "_ismbclower"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbclower-Funktion"
  - "_ismbclower_l-Funktion"
  - "_ismbcupper-Funktion"
  - "_ismbcupper_l-Funktion"
  - "ismbclower-Funktion"
  - "ismbclower_l-Funktion"
  - "ismbcupper-Funktion"
  - "ismbcupper_l-Funktion"
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überprüft, ob ein Multibytezeichen in Klein\- oder Großschreibung vorliegt.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _ismbclower(  
   unsigned int c   
);  
int _ismbclower_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcupper(  
   unsigned int c   
);  
int _ismbcupper_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu testende Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich 0 zurück, wenn das Zeichen die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt.  Wenn `c`\<\= 255 und gibt eine entsprechende `_ismbb` Routine \(beispielsweise, entspricht `_ismbcalnum` in `_ismbbalnum`\), ist, ist das Ergebnis der Rückgabewert der entsprechenden `_ismbb` Routine.  
  
## Hinweise  
 Jede dieser Funktionen testet ein angegebenes Mehrbytezeichen auf eine angegebene Bedingung.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch das ihnen übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
|Routine|Testbedingung|Beispiel für Codepage 932|  
|-------------|-------------------|-------------------------------|  
|`_ismbclower`|Kleinbuchstaben alphabetisch|Gibt nur dann einen Wert ungleich Null zurück, wenn `c` eine Einzelbytedarstellung eines englischen ASCII\-Kleinbuchstabens ist: 0x61\=\<`c`\<\=0x7A.|  
|`_ismbclower_l`|Kleinbuchstaben alphabetisch|Gibt nur dann einen Wert ungleich Null zurück, wenn `c` eine Einzelbytedarstellung eines englischen ASCII\-Kleinbuchstabens ist: 0x61\=\<`c`\<\=0x7A.|  
|`_ismbcupper`|Großbuchstaben alphabetisch|Gibt nur dann einen Wert ungleich Null zurück, wenn `c` eine Einzelbytedarstellung eines englischen ASCII\-Großbuchstabens ist: 0x41\<\=`c`\<\=0x5A.|  
|`_ismbcupper_l`|Großbuchstaben alphabetisch|Gibt nur dann einen Wert ungleich Null zurück, wenn `c` eine Einzelbytedarstellung eines englischen ASCII\-Großbuchstabens ist: 0x41\<\=`c`\<\=0x5A.|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ismbclower`|\<mbstring.h\>|  
|`_ismbclower_l`|\<mbstring.h\>|  
|`_ismbcupper`|\<mbstring.h\>|  
|`_ismbcupper_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
  
-   [System::Char::IsLower](https://msdn.microsoft.com/en-us/library/system.char.islower.aspx)  
  
-   [System::Char::IsUpper](https://msdn.microsoft.com/en-us/library/system.char.isupper.aspx)  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [\_ismbc\-Routinen](../../c-runtime-library/ismbc-routines.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)
---
title: "_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_ismbcalpha"
  - "_ismbcalnum"
  - "_ismbcdigit"
  - "_ismbcalnum_l"
  - "_ismbcdigit_l"
  - "_ismbcalpha_l"
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
  - "_ismbcdigit"
  - "ismbcalnum_l"
  - "_ismbcdigit_l"
  - "_ismbcalpha"
  - "ismbcalnum"
  - "ismbcdigit"
  - "ismbcalpha"
  - "_ismbcalnum_l"
  - "_ismbcalnum"
  - "ismbcdigit_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcalnum-Funktion"
  - "_ismbcalnum_l-Funktion"
  - "_ismbcalpha-Funktion"
  - "_ismbcalpha_l-Funktion"
  - "_ismbcdigit-Funktion"
  - "_ismbcdigit_l-Funktion"
  - "ismbcalnum-Funktion"
  - "ismbcalnum_l-Funktion"
  - "ismbcalpha-Funktion"
  - "ismbcalpha_l-Funktion"
  - "ismbcdigit-Funktion"
  - "ismbcdigit_l-Funktion"
ms.assetid: 12d57925-aebe-46e0-80b0-82b84c4c31ec
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überprüft, ob ein Multibytezeichen ein alphanumerisches Zeichen ist oder aus einem Buchstaben oder einer Ziffer besteht.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _ismbcalnum  
(  
   unsigned int c   
);  
int _ismbcalnum_l  
(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcalpha  
(  
   unsigned int c   
);  
int _ismbcalpha_l  
(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcdigit  
(  
   unsigned int c   
);  
int _ismbcdigit_l  
(  
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
 Jede dieser Routinen testet ein angegebenes Multibytezeichen auf eine angegebene Bedingung.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch das ihnen übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
|Routine|Testbedingung|Beispiel für Codepage 932|  
|-------------|-------------------|-------------------------------|  
|`_ismbcalnum,_ismbcalnum_l`|Alphanumerisches Zeichen|Gibt nur dann einen Wert ungleich Null zurück, wenn `c` eine Einzelbytedarstellung eines englischen ASCII\-Buchstabens ist: siehe Beispiele für `_ismbcdigit` und `_ismbcalpha`.|  
|`_ismbcalpha,_ismbcalpha_l`|Alphabetisch|Gibt nur dann einen Wert ungleich Null zurück, wenn `c` eine Einzelbytedarstellung eines englischen ASCII\-Buchstabens ist: 0x41\=\<`c`\<\=0x5A oder 0x61\=\<`c`\<\=0x7A; oder ein Katakana\-Buchstabe: 0xA6\=\<`c`\<\=0xDF.|  
|`_ismbcdigit,_ismbcdigit`|Ziffer|Gibt nur dann einen Wert ungleich Null zurück, wenn `c` eine Einzelbytedarstellung einer ASCII\-Ziffer ist: 0x30\=\<`c`\<\=0x39.|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_ismbcalnum,_ismbcalnum_l`|\<mbstring.h\>|  
|`_ismbcalpha,_ismbcalpha_l`|\<mbstring.h\>|  
|`_ismbcdigit,_ismbcdigit_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
  
-   [System::Char::IsLetter](https://msdn.microsoft.com/en-us/library/system.char.isletter.aspx)  
  
-   [System::Char::IsDigit](https://msdn.microsoft.com/en-us/library/system.char.isdigit.aspx)  
  
-   Für `_ismbcalnum`: Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [\_ismbc\-Routinen](../../c-runtime-library/ismbc-routines.md)   
 [is\- und isw\-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)
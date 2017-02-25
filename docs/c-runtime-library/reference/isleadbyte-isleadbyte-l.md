---
title: "isleadbyte, _isleadbyte_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isleadbyte_l"
  - "isleadbyte"
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
  - "_istleadbyte"
  - "_isleadbyte_l"
  - "isleadbyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Führende Bytes"
  - "_isleadbyte_l-Funktion"
  - "_istleadbyte-Funktion"
  - "istleadbyte-Funktion"
  - "isleadbyte-Funktion"
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# isleadbyte, _isleadbyte_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob ein Zeichen das führende Byte eines Multibytezeichens ist.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In \/ZW nicht unterstützte CRT\-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
## Rückgabewert  
 `isleadbyte` gibt einen Wert ungleich 0 zurück, wenn das Argument die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt. Im Gebietsschema "C" und in Einzelbyte\-Zeichensatz\(SBCS\)\-Gebietsschemas, gibt `isleadbyte` immer 0 zurück.  
  
## Hinweise  
 Das Makro `isleadbyte` gibt einen Wert ungleich 0 \(null\) zurück, wenn dessen Argument das erste Byte eines Multibytezeichens ist.`isleadbyte` erzeugt ein aussagekräftiges Ergebnis für ein Ganzzahlargument von – 1 \(`EOF`\) bis einschließlich `UCHAR_MAX` \(0xFF\).  
  
 Der erwartete Argumenttyp von `isleadbyte` ist `int`. Ein mit Vorzeichen übergebenes Zeichen wird vom Compiler möglicherweise durch Vorzeichenerweiterung in eine ganze Zahl konvertiert, was zu unvorhersehbaren Ergebnissen führt.  
  
 Die Version dieser Funktion mit dem `_l`\-Suffix ist beinahe identisch, verwendet jedoch das an sie übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_istleadbyte`|Gibt immer "false" zurück|**\_** `isleadbyte`|Gibt immer "false" zurück|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`isleadbyte`|\<ctype.h\>|  
|`_isleadbyte_l`|\<ctype.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Siehe jedoch [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).  
  
## Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)
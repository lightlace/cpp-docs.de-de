---
title: "_mbsbtype, _mbsbtype_l"
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
  - "_mbsbtype_l"
  - "_mbsbtype"
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
  - "mbsbtype"
  - "mbsbtype_l"
  - "_mbsbtype_l"
  - "_mbsbtype"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsbtype-Funktion"
  - "_mbsbtype_l-Funktion"
  - "mbsbtype-Funktion"
  - "mbsbtype_l-Funktion"
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# _mbsbtype, _mbsbtype_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Bytetyp in einer Zeichenfolge zurück.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _mbsbtype(  
   const unsigned char *mbstr,  
   size_t count   
);  
int _mbsbtype_l(  
   const unsigned char *mbstr,  
   size_t count,  
   _locale_t locale   
);  
```  
  
#### Parameter  
 `mbstr`  
 Adresse einer Sequenz von Multibytezeichen.  
  
 `count`  
 Byte\-Offset vom Anfang der Zeichenfolge.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 `_mbsbtype` und `_mbsbtype_l` gibt einen ganzzahligen Wert zurück, der das Ergebnis des Tests auf dem angegebenen Bytes angibt.  Die Manifestkonstanten in der folgenden Tabelle sind in Mbctype.h definiert.  
  
|Rückgabewert|Bytetyp|  
|------------------|-------------|  
|`_MBC_SINGLE` \(0\)|Einzelbytezeichen.  In Codepage 932 gibt `_mbsbtype` beispielsweise 0 zurück, wenn das angegebene Byte im Bereich 0x20\-0x7E oder 0xA1\-0xDF liegt.|  
|`_MBC_LEAD` \(1\)|Führendes Byte des Multibytezeichens.  In Codepage 932 gibt `_mbsbtype` beispielsweise 1 zurück, wenn das angegebene Byte im Bereich 0x81\-0x9F oder 0xE0\-0xFC liegt.|  
|`_MBC_TRAIL` \(2\)|Nachfolgendes Byte des Multibytezeichens.  In Codepage 932 gibt `_mbsbtype` beispielsweise 2 zurück, wenn das angegebene Byte im Bereich 0x40\-0x7E oder 0x80\-0xFC liegt.|  
|`_MBC_ILLEGAL` \(–1\)|`NULL`\-Zeichenfolge, ungültiges Zeichen oder `NULL`\-Byte, gefunden vor dem Byte am Offset `count` in `mbstr`.|  
  
## Hinweise  
 Die `_mbsbtype`\-Funktion bestimmt den Typ eines Bytes in einer Multibyte\-Zeichenfolge.  Die Funktion überprüft nur das Byte am Offset `count` in `mbstr` und ignoriert ungültige Zeichen vor dem angegebenen Byte.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Version dieser Funktion ohne das `_l`\-Suffix verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Version mit dem `_l`\-Suffix ist beinahe identisch, verwendet jedoch stattdessen den ihr übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Wenn die Eingabezeichenfolge `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `_MBC_ILLEGAL` zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_mbsbtype`|\<mbstring.h\>|\<mbctype.h\>\*|  
|`_mbsbtype_l`|\<mbstring.h\>|\<mbctype.h\>\*|  
  
 \* Für Manifestkonstanten, die als Rückgabewerte verwendet werden.  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Siehe jedoch [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).  
  
## Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)
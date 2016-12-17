---
title: "_mbbtype, _mbbtype_l"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_mbbtype"
  - "_mbbtype_l"
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
  - "_mbbtype_l"
  - "mbbtype"
  - "mbbtype_l"
  - "_mbbtype"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbbtype-Funktion"
  - "_mbbtype_l-Funktion"
  - "mbbtype-Funktion"
  - "mbbtype_l-Funktion"
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# _mbbtype, _mbbtype_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Bytetyp basierend auf dem vorherigen Byte zurück.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die im [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _mbbtype(  
   unsigned char c,  
   int type   
);  
int _mbbtype_l(  
   unsigned char c,  
   int type,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Das zu überprüfende Zeichen.  
  
 `type`  
 Der Typ des zu prüfenden Bytes.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 `_mbbtype` gibt den Bytetyp in einer Zeichenfolge zurück.  Diese Entscheidung ist kontextabhängig, wie durch den Wert von `type` angegeben, der die Steuerelement\-Testbedingung bereitstellt.  `type` ist der Typ des vorherigen Byte in der Zeichenfolge.  Die Manifestkonstanten in der folgenden Tabelle sind in Mbctype.h definiert.  
  
|Wert von `type`|`_mbbtype` testet auf|Rückgabewert|`c`|  
|---------------------|---------------------------|------------------|---------|  
|Einen beliebiger Wert außer 1|Gültiges Einzelbyte oder führendes Byte|`_MBC_SINGLE` \(0\)|Einzelvyte \(0 x 20 – 0x7E, 0xA1 – 0xDF\)|  
|Einen beliebiger Wert außer 1|Gültiges Einzelbyte oder führendes Byte|`_MBC_LEAD` \(1\)|Führendes Byte des Multibytezeichens \(0x81 – 0x9F, 0xE0 – 0xFC\)|  
|Einen beliebiger Wert außer 1|Gültiges Einzelbyte oder führendes Byte|`_MBC_ILLEGAL`<br /><br /> \( –1\)|Ungültiges Zeichen \(jeder Wert außer 0x20 – 0x7E, 0xA1 – 0xDF, 0x81 – 0x9F, 0xE0 – 0xFC|  
|1|Gültiges nachfolgendes Byte|`_MBC_TRAIL` \(2\)|Nachfolgendes Byte des Multibytezeichens  \(0x40 – 0x7E, 0x80 – 0xFC\)|  
|1|Gültiges nachfolgendes Byte|`_MBC_ILLEGAL`<br /><br /> \( –1\)|Ungültiges Zeichen \(jeder Wert außer 0x20 – 0x7E, 0xA1 – 0xDF, 0x81 – 0x9F, 0xE0 – 0xFC|  
  
## Hinweise  
 Die `_mbbtype`\-Funktion bestimmt den Typ eines Bytes in einem Multibytezeichen.  Wenn der Wert von `type` ein beliebiger Wert außer 1 ist, testet `_mbbtype` auf ein gültiges Einzelbyte oder führendes Byte eines Multibytezeichens.  Wenn der Wert von `type` 1 lautet, testet `_mbbtype` auf ein gültiges nachfolgendes Byte eines Multibytezeichens.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die `_mbbtype`\-Version dieser Funktion verwendet das aktuelle Gebietsschema auf dieses vom Gebietsschema abhängige Verhalten. Die `_mbbtype_l`\-Version ist beinahe identisch, abgesehen davon, dass es stattdessen den ihr übergebenen Gebietsschemaparameter verwendet.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In früheren Versionen hieß `_mbbtype` `chkctype`.  Verwenden Sie bei neuem Code stattdessen `_mbbtype`.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_mbbtype`|\<mbstring.h\>|\<mbctype.h\>\*|  
|`_mbbtype_l`|\<mbstring.h\>|\<mbctype.h\>\*|  
  
 \* Für Definitionen von Manifestkonstanten, die als Rückgabewerte verwendet werden.  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Siehe jedoch [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).  
  
## Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)
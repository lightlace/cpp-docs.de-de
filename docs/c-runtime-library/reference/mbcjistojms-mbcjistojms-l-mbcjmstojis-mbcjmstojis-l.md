---
title: "_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l"
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
  - "_mbcjistojms"
  - "_mbcjmstojis"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
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
  - "mbcjistojms"
  - "_mbcjistojms"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
  - "_mbcjmstojis"
  - "mbcjmstojis_l"
  - "mbcjistojms_l"
  - "mbcjmstojis"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbcjistojms-Funktion"
  - "_mbcjistojms_l-Funktion"
  - "_mbcjmstojis-Funktion"
  - "_mbcjmstojis_l-Funktion"
  - "mbcjistojms-Funktion"
  - "mbcjistojms_l-Funktion"
  - "mbcjmstojis-Funktion"
  - "mbcjmstojis_l-Funktion"
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert zwischen Zeichen aus den Zeichensätzen Japan Industry Standard \(JIS\) und Japan Microsoft \(JMS\).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
unsigned int _mbcjistojms(  
   unsigned int c   
);  
unsigned int _mbcjistojms_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbcjmstojis(  
   unsigned int c   
);  
unsigned int _mbcjmstojis_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Zu konvertierendes Zeichen.  
  
 `local`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Bei einem japanischen Gebietsschema geben diese Funktionen ein konvertiertes Zeichen zurück. Wenn keine Konvertierung möglich ist, wir 0 \(null\) zurückgegeben.  Bei einem nicht japanischen Gebietsschema geben diese Funktionen das Zeichen zurück, das übergeben wurde.  
  
## Hinweise  
 Die `_mbcjistojms` \-Funktion konvertiert ein JIS\-Zeichen \(Japan Industry Standard\) in ein Shift JIS\-Zeichen \(Microsoft Kanji\).  Das Zeichen wird nur konvertiert, wenn die anführenden und die nachfolgenden Bytes im Bereich 0x21–0x7E liegen.  Wenn das anführende oder das nachfolgende Byte außerhalb dieses Bereichs liegt, wird `errno` auf `EILSEQ` festgelegt.  Weitere Informationen über diesen und andere Fehlercodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Die `_mbcjmstojis`\- Funktion konvertiert ein Zeichen der UMSCHALTTASTE JIS zu einem JIS\-Zeichen.  Das Zeichen wird nur konvertiert, wenn das führende Byte im Bereich 0x81–0x9F oder 0xE0–0xFC liegt und das nachfolgende Byte im Bereich 0x40–0x7E oder 0x80–0xFC.  Beachten Sie, dass einigen Codepunkten in diesem Bereich kein Zeichen zugewiesen ist und sie daher nicht konvertiert werden können.  
  
 Der Wert `c` muss ein 16\-Bit\-Wert sein, dessen obere 8 Bits das führende Byte des zu konvertierenden Zeichens darstellen und dessen untere 8 Bits das nachfolgende Byte darstellen.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In früheren Versionen wurden `_mbcjistojms` und `_mbcjmstojis` noch `jistojms` bzw. `jmstojis` genannt.  `_mbcjistojms`,`_mbcjistojms_l`,`_mbcjmstojis` und `_mbcjmstojis_l` sollten stattdessen verwendet werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbcjistojms`|\<mbstring.h\>|  
|`_mbcjistojms_l`|\<mbstring.h\>|  
|`_mbcjmstojis`|\<mbstring.h\>|  
|`_mbcjmstojis_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [\_ismbb\-Routinen](../../c-runtime-library/ismbb-routines.md)
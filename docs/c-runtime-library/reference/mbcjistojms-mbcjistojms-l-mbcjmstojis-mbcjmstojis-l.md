---
title: _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
dev_langs:
- C++
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 60a870b9c0beff704511ab788d621b0f9697ed5d
ms.lasthandoff: 02/24/2017

---
# <a name="mbcjistojms-mbcjistojmsl-mbcjmstojis-mbcjmstojisl"></a>_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
Konvertiert zwischen Zeichen aus den Zeichensätzen Japan Industry Standard (JIS) und Japan Microsoft (JMS).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu konvertierendes Zeichen.  
  
 `local`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei einem japanischen Gebietsschema geben diese Funktionen ein konvertiertes Zeichen zurück. Wenn keine Konvertierung möglich ist, wir 0 (null) zurückgegeben. Bei einem nicht japanischen Gebietsschema geben diese Funktionen das Zeichen zurück, das übergeben wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die `_mbcjistojms`-Funktion konvertiert ein JIS-Zeichen (Japan Industry Standard) in ein Shift JIS-Zeichen (Microsoft Kanji). Das Zeichen wird nur konvertiert, wenn die anführenden und die nachfolgenden Bytes im Bereich 0x21–0x7E liegen. Wenn das anführende oder das nachfolgende Byte außerhalb dieses Bereichs liegt, wird `errno` auf `EILSEQ` festgelegt. Weitere Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Die `_mbcjmstojis`-Funktion konvertiert ein Shift JIS-Zeichen in ein JIS-Zeichen. Das Zeichen wird nur konvertiert, wenn das führende Byte im Bereich 0x81–0x9F oder 0xE0–0xFC liegt und das nachfolgende Byte im Bereich 0x40–0x7E oder 0x80–0xFC. Beachten Sie, dass einigen Codepunkten in diesem Bereich kein Zeichen zugewiesen ist und sie daher nicht konvertiert werden können.  
  
 Der Wert `c` muss ein 16-Bit-Wert sein, dessen obere 8 Bits das führende Byte des zu konvertierenden Zeichens darstellen und dessen untere 8 Bits das nachfolgende Byte darstellen.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das `_l`-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In früheren Versionen wurden `_mbcjistojms` und `_mbcjmstojis` noch `jistojms` bzw. `jmstojis` genannt. Stattdessen sollten `_mbcjistojms`, `_mbcjistojms_l`, `_mbcjmstojis` und `_mbcjmstojis_l` verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_mbcjistojms`|\<mbstring.h>|  
|`_mbcjistojms_l`|\<mbstring.h>|  
|`_mbcjmstojis`|\<mbstring.h>|  
|`_mbcjmstojis_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)

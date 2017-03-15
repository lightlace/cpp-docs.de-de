---
title: _mbctombb, _mbctombb_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbctombb_l
- _mbctombb
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
- _mbctombb_l
- _mbctombb
- mbctombb_l
- mbctombb
dev_langs:
- C++
helpviewer_keywords:
- _mbctombb function
- mbctombb_l function
- mbctombb function
- _mbctombb_l function
ms.assetid: d90970b8-71ff-4586-b6a2-f9ceb811f776
caps.latest.revision: 17
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
ms.openlocfilehash: d1831c28a8aab99478fb362d46db352674a360df
ms.lasthandoff: 02/24/2017

---
# <a name="mbctombb-mbctombbl"></a>_mbctombb, _mbctombb_l
Konvertiert ein Doppelbyte-Multibytezeichen in ein entsprechendes Einzelbyte-Multibytezeichen.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned int _mbctombb(  
   unsigned int c   
);  
unsigned int _mbctombb_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu konvertierendes Multibytezeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg geben `_mbctombb` und `_mbctombb_l` das Einzelbytezeichen zurück, das `c` entspricht; andernfalls wird `c` zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen `_mbctombb` und `_mbctombb_l` konvertieren ein angegebenes Multibytezeichen in ein entsprechendes Einzelbyte-Multibytezeichen. Die Zeichen müssen den Einzelbytezeichen innerhalb des Bereichs 0x20–0x7E oder 0xA1–0xDF entsprechen, um konvertiert zu werden.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Version dieser Funktion ohne das `_l`-Suffix verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Version mit dem `_l`-Suffix ist beinahe identisch, verwendet jedoch stattdessen den ihr übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In früheren Versionen wurde `_mbctombb` `zentohan` genannt. Verwenden Sie stattdessen _`mbctombb`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_mbctombb`|\<mbstring.h>|  
|`_mbctombb_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [_mbbtombc, _mbbtombc_l](../../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)   
 [_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)   
 [_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)   
 [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)

---
title: _mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbctohira
- _mbctohira_l
- _mbctokata
- _mbctokata_l
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
- _mbctokata
- mbctohira
- _mbctohira
- _mbctohira_l
- mbctokata
- mbctokata_l
- mbctohira_l
- _mbctokata_l
dev_langs: C++
helpviewer_keywords:
- _mbctokata function
- _mbctokata_l function
- _mbctohira_l function
- mbctohira_l function
- mbctohira function
- mbctokata_l function
- _mbctohira function
- mbctokata function
ms.assetid: f949afd7-44d4-4f08-ac8f-1fef2c915a1c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0a398e2d0b55a8c3292a77ba957982fa5a5e21f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="mbctohira-mbctohiral-mbctokata-mbctokatal"></a>_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l
Konvertiert zwischen Hiragana- und Katakana-Zeichen.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned int _mbctohira(  
   unsigned int c   
);  
unsigned int _mbctohira_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbctokata(  
   unsigned int c   
);  
unsigned int _mbctokata_l(  
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
 Jede dieser Funktionen gibt das konvertierte Zeichen `c` zurück, sofern dies möglich ist. Andernfalls wird das Zeichen `c` unverändert zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die `_mbctohira`- und `_mbctokata`-Funktionen testen ein Zeichen `c` und geben, falls möglich, eine der folgenden Konvertierungen zurück.  
  
|Routinen|Konvertiert|  
|--------------|--------------|  
|`_mbctohira,_mbctohira_l`|Multibyte-Katakana in Multibyte-Hiragana.|  
|`_mbctokata,_mbctokata_l`|Multibyte-Hiragana in Multibyte-Katakana.|  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen ohne das `_l`-Suffix für dieses Gebietsschema-abhängige Verhalten das aktuelle Gebietsschema verwenden, und diejenigen mit `_l`-Suffix den übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In früheren Versionen hieß `_mbctohira` `jtohira` und `_mbctokata` `jtokata`. Verwenden Sie bei neuem Code die neuen Namen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_mbctohira`|\<mbstring.h>|  
|`_mbctohira_l`|\<mbstring.h>|  
|`_mbctokata`|\<mbstring.h>|  
|`_mbctokata_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)   
 [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)   
 [_mbctombb, _mbctombb_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)
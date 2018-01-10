---
title: _mbbtombc, _mbbtombc_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbbtombc_l
- _mbbtombc
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
- _mbbtombc_l
- _mbbtombc
- mbbtombc_l
- mbbtombc
dev_langs: C++
helpviewer_keywords:
- mbbtombc_l function
- mbbtombc function
- _mbbtombc_l function
- _mbbtombc function
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aeb470a34fd6c00557cfe452503e8bf299c49182
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mbbtombc-mbbtombcl"></a>_mbbtombc, _mbbtombc_l
Konvertiert ein Einzelbyte-Multibytezeichen in ein entsprechendes Doppelbyte-Multibytezeichen.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned int _mbbtombc(  
   unsigned int c   
);  
unsigned int _mbbtombc_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu konvertierendes Einzelbytezeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn `c` erfolgreich von `_mbbtombc` konvertiert wird, wird ein Multibytezeichen zurückgegeben, andernfalls wird `c` zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die `_mbbtombc`-Funktion konvertiert ein angegebenes Einzelbyte-Multibytezeichen in ein entsprechendes Doppelbyte-Multibytezeichen. Zeichen muss innerhalb des Bereichs 0 x 20 – 0x7E oder 0xA1 - 0xDF konvertiert werden.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieeinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktion sind identisch, außer, dass diese `_mbbtombc`-Version das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten verwendet und die `_mbbtombc_l`-Version stattdessen den ihr übergebenen Gebietsschemaparameter verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In früheren Versionen hieß `_mbbtombc`  `hantozen`. Verwenden Sie bei neuem Code `_mbbtombc`.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_mbbtombc`|\<mbstring.h>|  
|`_mbbtombc_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [_mbctombb, _mbctombb_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)
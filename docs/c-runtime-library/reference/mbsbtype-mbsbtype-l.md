---
title: _mbsbtype, _mbsbtype_ | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsbtype_l
- _mbsbtype
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
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 81223356f5dac86fcc161e1c7fd1bc5eb80dcfbf
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="mbsbtype-mbsbtypel"></a>_mbsbtype, _mbsbtype_l
Gibt den Bytetyp in einer Zeichenfolge zurück.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `mbstr`  
 Adresse einer Sequenz von Multibytezeichen.  
  
 `count`  
 Byte-Offset vom Anfang der Zeichenfolge.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 `_mbsbtype`und `_mbsbtype_l` gibt einen ganzzahligen Wert, der angibt, des Ergebnis des Tests auf dem angegebenen Byte. Die Manifestkonstanten in der folgenden Tabelle sind in Mbctype.h definiert.  
  
|Rückgabewert|Bytetyp|  
|------------------|---------------|  
|`_MBC_SINGLE` (0)|Einzelbytezeichen. Beispielsweise ist in Codepage 932 `_mbsbtype` gibt 0 zurück, wenn das angegebene Byte im Bereich 0 x 20 – 0x7E oder 0xA1 - 0xDF liegt.|  
|`_MBC_LEAD` (1)|Führendes Byte des Multibytezeichens. Beispielsweise ist in Codepage 932 `_mbsbtype` gibt 1 zurück, wenn das angegebene Byte im Bereich 0 x 81-0x9F oder 0xE0 - 0xFC liegt.|  
|`_MBC_TRAIL` (2)|Nachfolgendes Byte des Multibytezeichens. Beispielsweise ist in Codepage 932 `_mbsbtype` gibt 2 zurück, wenn das angegebene Byte im Bereich 0 x 40-0x7E oder 0 x 80 - 0xFC liegt.|  
|`_MBC_ILLEGAL` (-1)|`NULL`-Zeichenfolge, ungültiges Zeichen oder `NULL`-Byte, gefunden vor dem Byte am Offset `count` in `mbstr`.|  
  
## <a name="remarks"></a>Hinweise  
 Die `_mbsbtype`-Funktion bestimmt den Typ eines Bytes in einer Multibyte-Zeichenfolge. Die Funktion überprüft nur das Byte am Offset `count` in `mbstr` und ignoriert ungültige Zeichen vor dem angegebenen Byte.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Version dieser Funktion ohne das `_l`-Suffix verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Version mit dem `_l`-Suffix ist beinahe identisch, verwendet jedoch stattdessen den ihr übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Wenn die Eingabezeichenfolge `NULL` ist, wird der ungültige Parameterhandler wie in [Parameter Validation](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `_MBC_ILLEGAL` zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_mbsbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbsbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* Für Manifestkonstanten, die als Rückgabewerte verwendet werden.  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)

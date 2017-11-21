---
title: _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbcalpha
- _ismbcalnum
- _ismbcdigit
- _ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha_l
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
- _ismbcdigit
- ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha
- ismbcalnum
- ismbcdigit
- ismbcalpha
- _ismbcalnum_l
- _ismbcalnum
- ismbcdigit_l
dev_langs: C++
helpviewer_keywords:
- ismbcalpha function
- _ismbcalnum function
- ismbcdigit_l function
- _ismbcalnum_l function
- _ismbcdigit function
- ismbcalnum function
- _ismbcalpha_l function
- ismbcdigit function
- _ismbcalpha function
- _ismbcdigit_l function
- ismbcalnum_l function
- ismbcalpha_l function
ms.assetid: 12d57925-aebe-46e0-80b0-82b84c4c31ec
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ad428851bd89dd2e9efd49a900ccdc28066b246
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ismbcalnum-ismbcalnuml-ismbcalpha-ismbcalphal-ismbcdigit-ismbcdigitl"></a>_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
Überprüft, ob ein Multibytezeichen ein alphanumerisches Zeichen ist oder aus einem Buchstaben oder einer Ziffer besteht.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu testende Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich 0 zurück, wenn das Zeichen die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt. Wenn `c`<= 255 ist und es eine entsprechende `_ismbb`-Routine gibt (beispielsweise `_ismbcalnum` entspricht `_ismbbalnum`), ist das Ergebnis der Rückgabewert der entsprechenden `_ismbb`-Routine.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Routinen testet ein angegebenes Multibytezeichen auf eine angegebene Bedingung.  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch das ihnen übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
|Routine|Testbedingung|Beispiel für Codepage 932|  
|-------------|--------------------|---------------------------|  
|`_ismbcalnum,_ismbcalnum_l`|Alphanumerisches Zeichen|Gibt nur dann einen Wert ungleich Null zurück, wenn `c` eine Einzelbytedarstellung eines englischen ASCII-Buchstabens ist: siehe Beispiele für `_ismbcdigit` und `_ismbcalpha`.|  
|`_ismbcalpha,_ismbcalpha_l`|Alphabetisch|Gibt nur dann einen Wert ungleich null zurück, wenn `c` eine Einzelbytedarstellung eines englischen ASCII-Buchstabens ist: 0x41<=`c`<=0x5A oder 0x61<=`c`<=0x7A, oder ein Katakana-Buchstabe: 0xA6<=`c`<=0xDF.|  
|`_ismbcdigit,_ismbcdigit`|Ziffer|Gibt nur dann einen Wert ungleich null zurück, wenn `c` eine Einzelbytedarstellung einer ASCII-Ziffer ist: 0x30=<`c`<=0x39.|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_ismbcalnum,_ismbcalnum_l`|\<mbstring.h>|  
|`_ismbcalpha,_ismbcalpha_l`|\<mbstring.h>|  
|`_ismbcdigit,_ismbcdigit_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [_ismbc-Routinen](../../c-runtime-library/ismbc-routines.md)   
 [is- und isw-Routinen](../../c-runtime-library/is-isw-routines.md)   
 [_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)
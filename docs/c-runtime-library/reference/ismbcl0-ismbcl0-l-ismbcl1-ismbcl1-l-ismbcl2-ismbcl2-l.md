---
title: _ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbcl2
- _ismbcl1
- _ismbcl0
- _ismbcl2_l
- _ismbcl1_l
- _ismbcl0_l
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
- ismbcl0
- _ismbcl1_l
- _ismbcl0
- ismbcl1
- ismbcl0_l
- _ismbcl2_l
- ismbcl2
- ismbcl1_l
- _ismbcl1
- _ismbcl0_l
- _ismbcl2
- ismbcl2_l
dev_langs:
- C++
helpviewer_keywords:
- _ismbcl0_l function
- _ismbcl2 function
- _ismbcl1_l function
- ismbcl2 function
- _ismbcl1 function
- ismbcl0_l function
- ismbcl2_l function
- ismbcl1_l function
- ismbcl0 function
- ismbcl1 function
- _ismbcl2_l function
- _ismbcl0 function
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 23ae0c873ef956499c46800abebba62cb656557b
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="ismbcl0-ismbcl0l-ismbcl1-ismbcl1l-ismbcl2-ismbcl2l"></a>_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l
**Spezifische Funktionen der Codepage 932**, die das aktuelle Gebietsschema oder eine angegebene Kategorie für den LC_CTYPE-Konvertierungszustand verwenden.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _ismbcl0(  
   unsigned int c   
);  
int _ismbcl0_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcl1(  
   unsigned int c   
);  
int _ismbcl1_l(  
   unsigned int c ,  
   _locale_t locale  
);  
int _ismbcl2(  
   unsigned int c   
);  
int _ismbcl2_l(  
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
 Jede dieser Routinen gibt einen Wert ungleich 0 zurück, wenn das Zeichen die Testbedingung erfüllt, bzw. 0, wenn es sie nicht erfüllt. Wenn `c` <= 255 ist und es eine entsprechende `_ismbb`-Routine gibt (beispielsweise `_ismbcalnum` entspricht `_ismbbalnum`), ist das Ergebnis der Rückgabewert der entsprechenden `_ismbb`-Routine.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen testet ein angegebenes Mehrbytezeichen auf eine angegebene Bedingung.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieneinstellung des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das `_l`-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
|Routine|Testbedingung (nur Codepage 932)|  
|-------------|-------------------------------------------|  
|`_ismbcl0`|JIS, nicht Kanji: 0x8140<=`c`<= 0x889E.|  
|`_ismbcl0_l`|JIS, nicht Kanji: 0x8140<=`c`<= 0x889E.|  
|`_ismbcl1`|JIS, Ebene 1: 0x889F<=`c`<= 0x9872.|  
|`_ismbcl1_l`|JIS, Ebene 1: 0x889F<=`c`<= 0x9872.|  
|`_ismbcl2`|JIS, Ebene 2: 0x989F<=`c`<= 0xEAA4.|  
|`_ismbcl2_l`|JIS, Ebene 2: 0x989F<=`c`<= 0xEAA4.|  
  
 Die Funktionen überprüfen, ob der angegebene Wert `c` den oben beschriebenen Testbedingungen entspricht. Es wird jedoch nicht überprüft, ob `c` ein gültiges Multibytezeichen ist. Wenn das untere Byte in den Bereichen 0x00–0x3F, 0x7F oder 0xFD–0xFF liegt, geben diese Funktionen einen Wert ungleich 0 (null) zurück. Dies gibt an, dass das Zeichen die Testbedingung erfüllt. Verwenden Sie [_ismbbtrail](../../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md), um zu prüfen, ob das Multibytezeichen definiert ist.  
  
 **Ende der Codepage 932 (spezifisch)**  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_ismbcl0`|\<mbstring.h>|  
|`_ismbcl0_l`|\<mbstring.h>|  
|`_ismbcl1`|\<mbstring.h>|  
|`_ismbcl1_l`|\<mbstring.h>|  
|`_ismbcl2`|\<mbstring.h>|  
|`_ismbcl2_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [_ismbc-Routinen](../../c-runtime-library/ismbc-routines.md)   
 [is- und isw-Routinen](../../c-runtime-library/is-isw-routines.md)

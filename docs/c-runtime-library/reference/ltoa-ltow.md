---
title: _ltoa, _ltow | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ltoa
- _ltow
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
apitype: DLLExport
f1_keywords:
- ltow
- _ltot
- _ltoa
- _ltow
dev_langs: C++
helpviewer_keywords:
- converting integers
- _ltoa function
- _ltow function
- ltow function
- ltoa function
- long integer conversion to string
- converting numbers, to strings
ms.assetid: 14036104-2c25-4759-87c0-918ed8521e47
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7e7ae79ed3505e4570b453e7fd56b68730010388
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ltoa-ltow"></a>_ltoa, _ltow
Konvertiert eine lange ganze Zahl in eine Zeichenfolge Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_ltoa_s, _ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_ltoa(  
   long value,  
   char *str,  
   int radix   
);  
wchar_t *_ltow(  
   long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ltoa(  
   long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ltow(  
   long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `value`  
 Zu konvertierende Zahl.  
  
 `str`  
 Zeichenfolgenergebnis.  
  
 `radix`  
 Basis von `value`.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf `str` zurück. Es gibt keine Fehlerrückgabe.  
  
## <a name="remarks"></a>Hinweise  
 Die `_ltoa`-Funktion konvertiert die Ziffern von `value` in eine auf NULL endende Zeichenfolge und speichert das Ergebnis (bis zu 33 Bytes) in `str`. Die `radix` -Argument gibt die Basis des `value`, die im Bereich 2 – 36 sein muss. Wenn `radix` gleich 10 und `value` ist negativ ist, wird das erste Zeichen von der gespeicherten Zeichenfolge das Minuszeichen (-). `_ltow` ist eine Breitzeichenversion von `_ltoa`. Das zweite Argument und der Rückgabewert von `_ltow` sind Zeichenfolgen für Breitzeichen. Jede dieser Funktionen ist Microsoft-spezifisch.  
  
> [!IMPORTANT]
>  Um Pufferüberläufe zu verhindern, muss der `str`-Puffer groß genug für die konvertierten Ziffern, das abschließende NULL-Zeichen sowie ein Zeichen sein.  
  
 In C++ gibt es für diese Funktionen Vorlagenüberladungen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_ltoa`|\<stdlib.h>|  
|`_ltow`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)
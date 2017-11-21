---
title: _ltoa_s, _ltow_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ltoa_s
- _ltow_s
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
- _ltow_s
- _ltoa_s
- ltoa_s
- ltow_s
dev_langs: C++
helpviewer_keywords:
- converting integers
- _ltoa_s function
- ltow_s function
- long integer conversion to string
- converting numbers, to strings
- ltoa_s function
- _ltow_s function
ms.assetid: d7dc61ea-1ccd-412d-b262-555a58647386
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a9a6bc0bc74463ad38cc43a0adb514d9eb722783
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ltoas-ltows"></a>_ltoa_s, _ltow_s
Konvertiert eine lange ganze Zahl in eine Zeichenfolge. Dies sind Versionen von [_ltoa, _ltow](../../c-runtime-library/reference/ltoa-ltow.md) mit Sicherheitsverbesserungen wie in den [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _ltoa_s(  
    long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ltow_s(  
    long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ltoa_s(  
    long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ltow_s(  
    long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `value`  
 Zu konvertierende Zahl.  
  
 `str`  
 Puffer für die resultierende Zeichenfolge  
  
 `sizeOfstr`  
 Größe von `str` in Bytes für `_ltoa_s` oder Wörter für `_ltow_s`.  
  
 `radix`  
 Basis von `value`  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn die Funktion erfolgreich ausgeführt wurde oder ein Fehlercode war.  
  
## <a name="remarks"></a>Hinweise  
 Die `_ltoa_s`-Funktion konvertiert die Ziffern von `value` in eine auf NULL endende Zeichenfolge und speichert das Ergebnis (bis zu 33 Bytes) in `str`. Die `radix` -Argument gibt die Basis des `value`, die im Bereich 2 – 36 sein muss. Wenn `radix` gleich 10 und `value` ist negativ ist, wird das erste Zeichen von der gespeicherten Zeichenfolge das Minuszeichen (-). `_ltow_s` ist eine Breitzeichenversion von `_ltoa_s`. Das zweite Argument für `_ltow_s` ist eine Breitzeichen-Zeichenfolge.  
  
 Wenn `str` ein `NULL`-Zeiger oder wenn `sizeOfstr` kleiner oder gleich 0 ist, rufen diese Funktionen einen Handler für ungültige Parameter auf, so wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen -1 zurück und legen `errno` auf `EINVAL` fest. Wenn `value` oder `str` außerhalb des Bereichs einer langen ganzen Zahl liegen, geben diese Funktionen -1 zurück und legen `errno` auf `ERANGE` fest.  
  
 In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot_s`|`_ltoa_s`|`_ltoa_s`|`_ltow_s`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_ltoa_s`|\<stdlib.h>|  
|`_ltow_s`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [_ultoa_s, _ultow_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md)
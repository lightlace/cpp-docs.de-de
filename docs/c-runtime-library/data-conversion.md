---
title: Datenkonvertierung | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.conversions
dev_langs: C++
helpviewer_keywords:
- data conversion routines [C++]
- converting data
ms.assetid: b15b5268-7467-49f1-bf95-5299b598f94c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a711a8087fef7978eceaadece317d4aac95d6340
ms.sourcegitcommit: 2a5d0e9e6829150cbc22c6de3395ec13008e3266
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="data-conversion"></a>Datenkonvertierung
Diese Routinen konvertieren Daten aus einer Form in eine andere. Im Allgemeinen konvertieren diese Routinen die Daten schneller als Konvertierungen, die Sie selbst schreiben. Jede Routine, die mit einem `to`-Präfix beginnt, wird als Funktion und als Makro implementiert. Informationen zum Auswählen einer Implementierung finden Sie unter [Auswählen zwischen Funktionen und Makros](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).  
  
### <a name="data-conversion-routines"></a>Datenkonvertierungsroutinen  
  
|Routine|Verwendung|  
|-------------|---------|  
|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Suchen des absoluten Werts einer ganzen Zahl|  
|[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Konvertieren von Zeichenfolge in `float`|  
|[atoi, _atoi_l, _wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Konvertieren von Zeichenfolge in `int`|  
|[_atoi64, _atoi64_l, _wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Konvertieren von Zeichenfolge in `__int64`|  
|[atol, _atol_l, _wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Konvertieren von Zeichenfolge in `long`|  
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|Konvertieren von UTF-16- oder UTF-32-Zeichen in entsprechende Multibytezeichen|  
|[_ecvt](../c-runtime-library/reference/ecvt.md), [_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Konvertieren von `double` in Zeichenfolge der angegebenen Länge|  
|[_fcvt](../c-runtime-library/reference/fcvt.md), [_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Konvertieren von `double` mit einer angegebenen Anzahl von Ziffern hinter dem Dezimaltrennzeichen|  
|[_gcvt](../c-runtime-library/reference/gcvt.md), [_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Konvertieren von `double`-Zahl in in Zeichenfolge; Speichern der Zeichenfolge im Puffer|  
|[_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md), [_itoa_s, _i64toa_s, _ui64toa_s, _itow_s, _i64tow_s, _ui64tow_s](../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)|Konvertieren von `int` oder `__int64` in Zeichenfolge|  
|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Suchen des absoluten Werts einer `long`-Ganzzahl|  
|[llabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Suchen des absoluten Werts einer `long long`-Ganzzahl|  
|[_ltoa, _ltow](../c-runtime-library/reference/ltoa-ltow.md), [_ltoa_s, _ltow_s](../c-runtime-library/reference/ltoa-s-ltow-s.md)|Konvertieren von `long` in Zeichenfolge|  
|[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|Konvertieren von 1-Byte-Multibytezeichen in entsprechendes 2-Byte-Multibytezeichen|  
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|Konvertieren von JIS(Japan Industry Standard)-Zeichen in japanische Microsoft-Zeichen (JMS)|  
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|Konvertieren von JMS-Zeichen in JIS-Zeichen|  
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|Konvertieren von Multibytezeichen zu 1-Byte-Hiragana-Code|  
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|Konvertieren von Multibytezeichen zu 1-Byte-Katakana-Code|  
|[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|Konvertieren von 2-Byte-Multibytezeichen in entsprechendes 1-Byte-Multibytezeichen|  
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Konvertieren von Multibytezeichen in entsprechende UTF-16- oder UTF-32-Zeichen|  
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Konvertieren von Multibytezeichensequenz in entsprechende Breitzeichensequenz|  
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Konvertieren von Multibytezeichen in entsprechendes Breitzeichen|  
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Konvertieren von Zeichenfolge in `double`|  
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Konvertieren von Zeichenfolge in `long`-Ganzzahl|  
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Konvertieren von Zeichenfolge in `unsigned long`-Ganzzahl|  
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Transformieren der Zeichenfolge in sortierte Form nach gebietsschemaspezifischen Informationen|  
|[toascii, __toascii](../c-runtime-library/reference/toascii-toascii.md)|Konvertieren von Zeichen in ASCII-Code||  
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Testen von Zeichen und Konvertieren in Kleinbuchstaben falls derzeit Großbuchstabe|  
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)|Bedingungsloses Konvertieren in Kleinbuchstaben|[System::String::ToLower](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)|  
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Testen von Zeichen und Konvertieren in Großbuchstaben falls derzeit Kleinbuchstabe|  
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|Bedingungsloses Konvertieren in Großbuchstaben|  
|[_ultoa, _ultow](../c-runtime-library/reference/ultoa-ultow.md), [_ultoa_s, _ultow_s](../c-runtime-library/reference/ultoa-s-ultow-s.md)|Konvertieren von `unsigned long` in Zeichenfolge|  
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Konvertieren von Breitzeichensequenz in entsprechende Multibytezeichensequenz|  
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Konvertieren von Breitzeichen in entsprechendes Multibytezeichen|  
|[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Konvertieren von Zeichenfolge mit Breitzeichen in `double`|   
|[atoi, _atoi_l, _wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Konvertieren von Zeichenfolge mit Breitzeichen in `int`|  
|[_atoi64, _atoi64_l, _wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Konvertieren von Zeichenfolge mit Breitzeichen in `__int64`|  
|[atol, _atol_l, _wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Konvertieren von Zeichenfolge mit Breitzeichen in `long`|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
dev_langs:
- C++
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
caps.latest.revision: 18
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
ms.openlocfilehash: b05ec00ae2144670844cd54de0900aa1412128ff
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
Transformieren einer Zeichenfolge auf der Grundlage von gebietsschemaspezifischen Informationen  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t strxfrm(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
size_t wcsxfrm(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
size_t _strxfrm_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
size_t wcsxfrm_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `strDest`  
 Zielzeichenfolge.  
  
 `strSource`  
 Quellzeichenfolge.  
  
 `count`  
 Maximale Anzahl von Zeichen, die in platziert `strDest`.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Länge der transformierten Zeichenfolge ohne Berücksichtigung des beendenden Null-Zeichens zurück. Wenn der Rückgabewert größer als oder gleich `count` ist, wird der Inhalt von `strDest` unvorhersehbar. Bei einem Fehler legt jede Funktion `errno` fest und gibt `INT_MAX` zurück. Für ein ungültiges Zeichen wird `errno` auf `EILSEQ` festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die `strxfrm`-Funktion transformiert die Zeichenfolge, auf die `strSource` zeigt, in eine neue sortierte Form, die in `strDest` gespeichert ist. Höchstens `count` Zeichen, einschließlich des NULL-Zeichens, werden transformiert und in die Ergebniszeichenfolge eingefügt. Die Transformation erfolgt mit dem `LC_COLLATE`-Kategorieeinstellung des Gebietsschemas. Weitere Informationen zu `LC_COLLATE` finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). `strxfrm` verwendet das aktuelle Gebietsschema für das Verhalten, das vom Gebietsschema abhängig ist; `_strxfrm_l` ist identisch, verwendet jedoch stattdessen das übergebene Gebietsschema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Nach der Transformation ergibt ein Aufruf von `strcmp` mit den beiden transformierten Zeichenfolgen Ergebnisse, die mit den Ergebnissen eines Aufrufs von `strcoll` identisch sind, der auf die ursprünglichen beiden Zeichenfolgen angewendet wurde. Wie bei `strcoll` und `stricoll`, behandelt `strxfrm` Multibyte-Zeichenfolgen nach Bedarf automatisch.  
  
 `wcsxfrm` ist eine Breitzeichenversion von `strxfrm`. Die Zeichenfolgenargumente von `wcsxfrm` sind Zeichenfolgen mit Breitzeichen. Für `wcsxfrm` ergibt nach der Transformation ein Aufruf von `wcscmp` mit den beiden transformierten Zeichenfolgen Ergebnisse, die mit den Ergebnissen eines Aufrufs von `wcscoll` identisch sind, der auf die ursprünglichen beiden Zeichenfolgen angewendet wurde. `wcsxfrm` und `strxfrm` verhalten sich andernfalls identisch. `wcsxfrm` verwendet das aktuelle Gebietsschema für das Verhalten, das vom Gebietsschema abhängig ist; `_wcsxfrm_l` verwendet stattdessen das übergebene Gebietsschema.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `strSource` ein Null-Zeiger ist oder `strDest` ein NULL-Zeiger (sofern der Zähler nicht 0 ist) ist, oder wenn `count` größer als `INT_MAX` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung) beschrieben](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `INT_MAX` zurück.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsxfrm`|`strxfrm`|`strxfrm`|`wcsxfrm`|  
|`_tcsxfrm_l`|`_strxfrm_l`|`_strxfrm_l`|`_wcsxfrm_l`|  
  
 Im Gebietsschema „C“ ist die Reihenfolge der Zeichen im Zeichensatz (ASCII-Zeichensatz) die gleiche wie die lexikografische Reihenfolge von Zeichen. In anderen Gebietsschemata kann die Reihenfolge der Zeichen im Zeichensatz jedoch von der lexikografischen Reihenfolge der Zeichen abweichen. In bestimmten europäischen Gebietsschemata beispielsweise steht im Zeichensatz das Zeichen „a“ (Wert 0x61) vor dem Zeichen „&\#x00E4;“ (Wert 0xE4), das Zeichen „ä“ steht lexikografisch gesehen jedoch vor dem Zeichen „a“.  
  
 In Gebietsschemata, für die sich der Zeichensatz und die lexikografische Zeichenreihenfolge unterscheiden, verwenden Sie `strxfrm` für die ursprünglichen Zeichenfolgen und anschließend `strcmp` für die resultierenden Zeichenfolgen, um einen lexikografischen Zeichenfolgenvergleich gemäß der `LC_COLLATE`-Kategorieeinstellung des aktuellen Gebietsschemas zu erstellen. Verwenden Sie daher zum lexikografischen Vergleich von zwei Zeichenfolgen im obigen Gebietsschema `strxfrm` für die ursprünglichen Zeichenfolgen und dann `strcmp` für die resultierenden Zeichenfolgen. Alternativ können Sie `strcoll` anstelle von `strcmp` für die ursprünglichen Zeichenfolgen verwenden.  
  
 `strxfrm` ist im Grunde ein Wrapper um [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) mit `LCMAP_SORTKEY`.  
  
 Der Wert des folgenden Ausdrucks ist die Größe des Arrays zum Speichern der `strxfrm`-Transformation der Quellzeichenfolge:  
  
```  
1 + strxfrm( NULL, string, 0 )  
```  
  
 Nur im Gebietsschema „C“ entspricht `strxfrm` Folgendem:  
  
```  
strncpy( _string1, _string2, _count );  
return( strlen( _string1 ) );  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`strxfrm`|\<string.h>|  
|`wcsxfrm`|\<string.h> oder \<wchar.h>|  
|`_strxfrm_l`|\<string.h>|  
|`_wcsxfrm_l`|\<string.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)

---
title: mbstowcs_s, _mbstowcs_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstowcs_s_l
- mbstowcs_s
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 8858827e65ad342f2c48dba26b3be7f7f9dd2ca3
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s, _mbstowcs_s_l
Konvertiert eine Multibyte-Zeichensequenz in eine entsprechende Breitzeichensequenz. Versionen von [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) mit Sicherheitsverbesserungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count   
);  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pReturnValue`  
 Die Anzahl von konvertierten Zeichen.  
  
 [out] `wcstr`  
 Pufferadresse zum Speichern der resultierenden konvertierten Breitzeichenfolge.  
  
 [in] `sizeInWords`  
 Größe des Puffers `wcstr` in Worten.  
  
 [in]`mbstr`  
 Adresse einer Multibyte-Zeichensequenz.  
  
 [in] `count`  
 Die maximale Anzahl von Breitzeichen, die im `wcstr`-Puffer gespeichert werden können, wobei das abschließende NULL-Zeichen nicht eingeschlossen ist, oder [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in] `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler.  
  
|Fehlerbedingung|Rückgabewert und `errno`|  
|---------------------|------------------------------|  
|`wcstr` ist gleich `NULL` und `sizeInWords` > 0|`EINVAL`|  
|`mbstr` ist gleich `NULL`.|`EINVAL`|  
|Der Zielpuffer ist für die konvertierte Zeichenfolge zu klein (es sei denn, `count` ist gleich `_TRUNCATE`; siehe Abschnitt „Hinweise“)|`ERANGE`|  
|`wcstr` ist ungleich `NULL` und `sizeInWords` == 0|`EINVAL`|  
  
 Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die Ausführung fortgesetzt werden kann, gibt die Funktion einen Fehlercode zurück und legt `errno` wie in der Tabelle angegeben fest.  
  
## <a name="remarks"></a>Hinweise  
 Die `mbstowcs_s`-Funktion konvertiert eine Zeichenfolge mit Multibytezeichen, auf die von `mbstr` verwiesen wird, in im Puffer gespeicherte Breitzeichen, auf die von `wcstr` verwiesen wird. Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine der folgenden Bedingungen eintritt:  
  
-   Ein Multibyte-Nullzeichen wird erkannt.  
  
-   Ein ungültiges Multibytezeichen wird erkannt.  
  
-   Die Anzahl der Breitzeichen, die im `wcstr`-Puffer gespeichert sind, ist gleich `count`.  
  
 Die Zielzeichenfolge endet immer mit NULL, selbst bei einem Fehler.  
  
 Wenn `count` der spezielle Wert [_TRUNCATE](../../c-runtime-library/truncate.md) ist, konvertiert `mbstowcs_s` einen so großen Teil der Zeichenfolge wie in den Zielpuffer passt, während weiterhin Platz für einen NULL-Terminator bleibt.  
  
 Wenn `mbstowcs_s` die Quellzeichenfolge erfolgreich konvertiert, wird die Größe der konvertierten Zeichenfolge in Breitzeichen und der NULL-Terminator in `*``pReturnValue` geschrieben, vorausgesetzt, `pReturnValue` ist ungleich `NULL`. Dieser Fehler tritt auch dann auf, wenn das `wcstr`-Argument `NULL` ist und es eine Methode zur Bestimmung der erforderlichen Puffergröße bietet. Bitte beachten Sie, dass `count` ignoriert wird, wenn `wcstr` gleich `NULL` ist und `sizeInWords` 0 sein muss.  
  
 Wenn `mbstowcs_s` ein ungültiges Multibytezeichen erkennt, schreibt es 0 in `*``pReturnValue`, legt den Zielpuffer auf eine leere Zeichenfolge fest, legt `errno` auf `EILSEQ` fest und gibt dann `EILSEQ` zurück.  
  
 Wenn die Sequenzen, auf die von `mbstr` und `wcstr` verwiesen wird, überlappen, ist das Verhalten von `mbstowcs_s` nicht definiert.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `wcstr` und `mbstr` nicht überlappen und dass `count` die Anzahl zu konvertierenderMultibytezeichen korrekt darstellt.  
  
 `mbstowcs_s` verwendet das aktuelle Gebietsschema für jedes Verhalten, das vom Gebietsschema abhängig ist; `_mbstowcs_s_l` ist identisch, nur dass sie stattdessen das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`mbstowcs_s`|\<stdlib.h>|  
|`_mbstowcs_s_l`|\<stdlib.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)

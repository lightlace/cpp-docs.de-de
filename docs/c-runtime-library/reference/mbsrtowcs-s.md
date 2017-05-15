---
title: mbsrtowcs_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbsrtowcs_s
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
- mbsrtowcs_s
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
caps.latest.revision: 24
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 920af1d0e06c7af71c3a98bf07f451f4d50f2659
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="mbsrtowcss"></a>mbsrtowcs_s
Konvertieren einer Zeichenfolge mit Multibytezeichen im aktuellen Gebietsschema in die entsprechende Zeichenfolge mit Breitzeichen. Eine Version von [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md) mit Sicherheitserweiterungen wie sie unter [Sicherheitserweiterungen im CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t * wcstr,  
   size_t sizeInWords,  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
);  
template <size_t size>  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `pReturnValue`  
 Die Anzahl von konvertierten Zeichen.  
  
 [out] `wcstr`  
 Pufferadresse zum Speichern der resultierenden konvertierten Zeichenfolge mit Breitzeichen.  
  
 [out] `sizeInWords`  
 Die Größe von `wcstr` in Wörtern (Breitzeichen).  
  
 [in, out] `mbstr`  
 Indirekter Zeiger auf den Speicherort der Multibyte-Zeichenfolge, die konvertiert werden soll.  
  
 [in] `count`  
 Die maximale Anzahl von Breitzeichen, die im `wcstr`-Puffer gespeichert werden können, wobei das abschließende NULL-Zeichen nicht eingeschlossen ist, oder [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in, out] `mbstate`  
 Ein Zeiger auf ein `mbstate_t`-Konvertierungszustandsobjekt. Wenn dieser Wert ein NULL-Zeiger ist, wird ein statisches internes Konvertierungszustandsobjekt verwendet. Da das interne `mbstate_t`-Objekt nicht threadsicher ist, wird empfohlen, immer Ihren eigenen `mbstate`-Parameter zu übergeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn die Konvertierung erfolgreich ist, oder ein Fehlercode bei einem Fehler.  
  
|Fehlerbedingung|Rückgabewert und `errno`|  
|---------------------|------------------------------|  
|`wcstr` ist ein NULL-Zeiger und `sizeInWords` > 0|`EINVAL`|  
|`mbstr` ist ein NULL-Zeiger|`EINVAL`|  
|Die Zeichenfolge, auf die indirekt von `mbstr` gezeigt wird, enthält eine Multibyte-Sequenz, die für das aktuelle Gebietsschema ungültig ist.|`EILSEQ`|  
|Der Zielpuffer ist zu klein für die konvertierte Zeichenfolge enthalten (es sei denn, `count` ist `_TRUNCATE`; weitere Informationen finden Sie unter "Hinweise")|`ERANGE`|  
  
 Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die Ausführung fortgesetzt werden kann, gibt die Funktion einen Fehlercode zurück und legt `errno` wie in der Tabelle angegeben fest.  
  
## <a name="remarks"></a>Hinweise  
 Die `mbsrtowcs_s`-Funktion konvertiert eine Zeichenfolge von Multibytezeichen, auf die indirekt von `mbstr` gezeigt wird, in im Puffer gespeicherte Breitzeichen, auf die von `wcstr` gezeigt wird, und verwendet dafür den in `mbstate` enthaltenen Konvertierungszustand. Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine der folgenden Bedingungen eintritt:  
  
-   Ein Multibyte-Nullzeichen wird erkannt.  
  
-   Ein ungültiges Multibytezeichen wird erkannt.  
  
-   Die Anzahl der Breitzeichen, die im `wcstr`-Puffer gespeichert sind, ist gleich `count`.  
  
 Die Zielzeichenfolge `wcstr` endet immer mit NULL, selbst bei einem Fehler, es sei denn `wcstr` ist ein NULL-Zeiger.  
  
 Wenn `count` der spezielle Wert [_TRUNCATE](../../c-runtime-library/truncate.md) ist, konvertiert `mbsrtowcs_s` einen so großen Teil der Zeichenfolge wie in den Zielpuffer passt, während weiterhin Platz für einen NULL-Terminator bleibt.  
  
 Wenn `mbsrtowcs_s` die Quellzeichenfolge erfolgreich konvertiert, wird die Größe der konvertierten Zeichenfolge in Breitzeichen und der NULL-Terminator in `*``pReturnValue` geschrieben, vorausgesetzt, `pReturnValue` ist kein NULL-Zeiger. Dieser Fehler tritt auf, selbst wenn das `wcstr`-Argument ein NULL-Zeiger ist und Sie die erforderliche Puffergröße bestimmen können. Beachten Sie, dass wenn `wcstr` ein NULL-Zeiger ist, wird `count` ignoriert.  
  
 Wenn `wcstr` kein NULL-Zeiger ist, wird das Zeigerobjekt, auf das von `mbstr` verwiesen wird, einem NULL-Zeiger zugewiesen, wenn die Konvertierung beendet wird, da ein abschließendes Nullzeichen erreicht wurde. Andernfalls wird es ggf. der Adresse unmittelbar nach dem letzten konvertierten Multibytezeichen zugewiesen. Auf diese Weise kann ein nachfolgender Funktionsaufruf die Konvertierung an der Stelle neu starten, an der der Aufruf beendet wurde.  
  
 Wenn `mbstate` ein NULL-Zeiger ist, wird das bibliotheksinterne statische `mbstate_t`-Konvertierungszustandobjekt verwendet. Da dieses interne statische Objekt nicht threadsicher ist, wird empfohlen, immer Ihren eigenen `mbstate`-Wert zu übergeben.  
  
 Wenn `mbsrtowcs_s` ein Multibytezeichen erkennt, das im aktuellen Gebietsschema ungültig ist, wird –1 in `*``pReturnValue` geschrieben, der Zielpuffer `wcstr` auf eine leere Zeichenfolge festgelegt, `errno` auf `EILSEQ` festgelegt und `EILSEQ` zurückgegeben.  
  
 Wenn die Sequenzen, auf die von `mbstr` und `wcstr` verwiesen wird, überlappen, ist das Verhalten von `mbsrtowcs_s` nicht definiert. `mbsrtowcs_s` wird von der LC_TYPE-Kategorie des aktuellen Gebietsschemas beeinflusst.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `wcstr` und `mbstr` nicht überlappen und dass `count` die Anzahl zu konvertierenderMultibytezeichen korrekt darstellt.  
  
 Die `mbsrtowcs_s`-Funktion unterscheidet sich von [mbstowcs_s](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md) durch die Neustartmöglichkeit. Der Konvertierungszustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert. Eine Anwendung sollte beispielsweise `mbsrlen` anstelle von `mbslen` verwenden, wenn ein nachfolgender Aufruf von `mbsrtowcs_s` anstelle von `mbstowcs_s.` verwendet wird.  
  
 In C++ wird die Verwendung dieser Funktion durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Ausnahmen  
 Die `mbsrtowcs_s`-Funktion ist multithreadsicher ist, solange keine Funktion im aktuellen Thread `setlocale` aufruft, solange diese Funktion ausgeführt wird und das `mbstate`-Argument kein NULL-Zeiger ist.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`mbsrtowcs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)

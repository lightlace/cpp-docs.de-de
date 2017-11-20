---
title: strcoll-Funktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords: strcoll
dev_langs: C++
helpviewer_keywords:
- code pages, using for string comparisons
- string comparison [C++], culture-specific
- strcoll functions
- strings [C++], comparing by code page
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 224c30dfbc79ab91e60f7f55f4835d3f627c454c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="strcoll-functions"></a>strcoll-Funktionen
Jede der `strcoll`- und `wcscoll`-Funktionen vergleicht zwei Zeichenfolgen gemäß der Kategorieneinstellung für `LC_COLLATE` der aktuell verwendeten Gebietsschemacodepage. Jede der `_mbscoll`-Funktionen vergleicht zwei Zeichenfolgen gemäß der aktuell verwendeten Multibytecodepage. Verwenden Sie die `coll`-Funktionen für Zeichenfolgenvergleiche, wenn es in der aktuellen Codepage einen Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Zeichenreihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist. Verwenden Sie die entsprechenden `cmp`-Funktionen, um nur Gleichheit der Zeichenfolgen zu prüfen.  
  
### <a name="strcoll-functions"></a>strcoll-Funktionen  
  
|SBCS|Unicode|MBCS|Beschreibung|  
|----------|-------------|----------|-----------------|  
|[strcoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Sortieren von zwei Zeichenfolgen|  
|[_stricoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_wcsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_mbsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Sortieren von zwei Zeichenfolgen (ohne Berücksichtigung von Groß-/Kleinschreibung)|  
|[_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Sortieren der ersten `count` Zeichen von zwei Zeichenfolgen|  
|[_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Sortieren der ersten `count` Zeichen zweier Zeichenfolgen (ohne Berücksichtigung von Groß-/Kleinschreibung)|  
  
## <a name="remarks"></a>Hinweise  
 Die Versionen dieser Funktionen im Einzelbyte-Zeichensatz (Single-Byte Character Set, SBCS) (`strcoll`, `stricoll`, `_strncoll` und `_strnicoll`) vergleichen `string1` und `string2` gemäß der Kategorieneinstellung `LC_COLLATE` des aktuellen Gebietsschemas. Diese Funktionen unterscheiden sich von den entsprechenden `strcmp`-Funktionen dahingehend, dass die `strcoll`-Funktionen Gebietsschemacodepageinformationen mit Sortierreihenfolgen verwenden. Für Zeichenfolgenvergleiche in Gebietsschemas, in denen die Reihenfolge des Zeichensatzes und die lexikografische Zeichenreihenfolge abweichen, sollten die `strcoll`-Funktionen statt der entsprechenden `strcmp`-Funktionen verwendet werden. Weitere Informationen zu `LC_COLLATE` finden Sie unter [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Bei manchen Codepages und entsprechenden Zeichensätzen kann die Reihenfolge der Zeichen im Zeichensatz möglicherweise von der lexikografischen Zeichenreihenfolge abweichen. Im "C "-Gebietsschema ist dies nicht der Fall: Die Reihenfolge der Zeichen im ASCII-Zeichensatz entspricht der lexikografischen Reihenfolge der Zeichen. In bestimmten europäischen Codepages beispielsweise steht im Zeichensatz das Zeichen "a" (Wert 0x61) vor dem Zeichen "ä" (Wert 0xE4), das Zeichen "ä" steht lexikografisch gesehen jedoch vor dem Zeichen "a". Um in solch einem Fall einen lexikografischen Vergleich durchzuführen, verwenden Sie `strcoll` statt `strcmp`. Sie können auch `strxfrm` für die ursprünglichen Zeichenfolgen verwenden, und dann `strcmp` für die resultierenden Zeichenfolgen.  
  
 `strcoll`, `stricoll`, `_strncoll` und `_strnicoll` verarbeiten automatisch Multibytezeichenfolgen entsprechend der derzeit verwendeten Gebietsschemacodepage, wie es bei den jeweiligen äquivalenten Breitzeichen (Unicode) der Fall ist. Die Versionen dieser Funktionen im Multibyte-Zeichensatz (Multibyte-Character Set, MBCS) sortieren Zeichenfolgen jedoch auf Zeichenbasis entsprechend der aktuell verwendeten Multibytecodepage.  
  
 Da die `coll`-Funktionen Zeichenfolgen für Vergleiche lexikografisch sortieren, während die `cmp`-Funktionen nur die Zeichenfolgengleichheit testen, sind die `coll`-Funktionen wesentlich langsamer als die entsprechenden `cmp`-Versionen. Daher sollten die `coll`-Funktionen nur verwendet werden, wenn es in der aktuellen Codepage einen Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Zeichenreihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Gebietsschema](../c-runtime-library/locale.md)   
 [Zeichenfolgenbearbeitung](../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, _mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
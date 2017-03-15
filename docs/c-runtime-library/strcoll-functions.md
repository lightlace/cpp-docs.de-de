---
title: "strcoll-Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strcoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Codepages, Verwenden für Zeichenfolgevergleiche"
  - "strcoll-Funktionen"
  - "Zeichenfolgenvergleich [C++], Kulturspezifisch"
  - "Zeichenfolgen [C++], Vergleichen nach Codepage"
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# strcoll-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede der `strcoll` und `wcscoll`\-Funktionen vergleicht zwei Zeichenfolgen anhand der `LC_COLLATE` Kategorieneinstellung der Gebietsschema\-Codepage derzeit.  Jede der Funktionen `_mbscoll` vergleicht zwei Zeichenfolgen anhand der Mehrbyte\-Codepage derzeit.  Verwenden Sie die Funktionen `coll` für Zeichenfolgenvergleiche, wenn es einen Unterschied zwischen der Zeichensatzreihenfolge gibt und der lexikografischen Reihenfolge in der aktuellen Codepage und diesem Unterschied relevant für den Vergleich ist.  Verwenden Sie die entsprechenden `cmp`\-Funktionen, um nur für Zeichenfolgengleichheit zu testen.  
  
### strcoll Funktionen  
  
|SBCS|Unicode|MBCS|**Beschreibung**|  
|----------|-------------|----------|----------------------|  
|[strcoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[\_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Sortieren Sie zwei Zeichenfolgen|  
|[\_stricoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[\_wcsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[\_mbsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Sortieren Sie zwei Zeichenfolgen \(Groß\-\/Kleinschreibung nicht berücksichtigt\)|  
|[\_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Sortieren Sie erste `count` Zeichen von zwei Zeichenfolgen|  
|[\_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Sortieren Sie erste `count` Zeichen von zwei Zeichenfolgen \(Groß\-\/Kleinschreibung nicht berücksichtigt\)|  
  
## Hinweise  
 Die Einzelbytezeichen \(sbcs\)\- Versionen dieser Funktionen \(`strcoll`, `stricoll`, `_strncoll` und `_strnicoll`\) vergleichen `string1` und `string2` anhand der `LC_COLLATE` Kategorieneinstellung des aktuellen Gebietsschemas.  Diese Funktionen unterscheiden sich von der entsprechenden `strcmp`\-Funktionen darin, dass die Funktionen `strcoll` Gebietsschemacodepageinformationen verwenden Sortierreihenfolgen, die bereitstellt.  Für Gebietsschemas, Zeichenfolgenvergleiche in den in denen die Zeichensatzreihenfolge und die lexikografische Reihenfolge unterscheiden, sollte das `strcoll`\-Funktionen anstatt die entsprechenden `strcmp`\-Funktionen verwendet werden.  Weitere Informationen zu `LC_COLLATE` finden Sie unter [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Für mehrere Codepages und entsprechende Zeichensätze unterscheidet möglicherweise die Reihenfolge der Zeichen im Zeichensatz sich von der lexikografischen Reihenfolge.  Im "C "\-Gebietsschema ist dies nicht der Fall: Die Reihenfolge der Zeichen im ASCII\-Zeichensatz entspricht der lexikografischen Reihenfolge der Zeichen.  In bestimmten europäischen Codepages beispielsweise steht im Zeichensatz das Zeichen "a" \(Wert 0x61\) vor dem Zeichen "ä" \(Wert 0xE4\), das Zeichen "ä" steht lexikografisch gesehen jedoch vor dem Zeichen "a".  Um einen lexikografischen Vergleich in einer solchen Instanz auszuführen, verwenden Sie `strcoll` anstelle von `strcmp`.  Alternativ können Sie `strxfrm` auf den ursprünglichen Zeichenfolgen verwenden, verwenden `strcmp` auf den Ergebniszeichenfolgen.  
  
 `strcoll`, `stricoll`, `_strncoll` und `_strnicoll` verarbeiten automatisch entsprechend der Mehrbyte\-Zeichenfolgen Gebietsschema\-Codepage derzeit, wie ihre Äquivalente des Breitzeichens \(Unicode\) möglich.  Die Mehrbytezeichen \(mbcs\)\- Versionen dieser Funktionen sortieren jedoch Zeichenfolgen auf einer Zeichenbasis entsprechend der Mehrbyte\-Codepage derzeit.  
  
 Da die `coll`\-Funktionen Zeichenfolgen für Vergleiche lexikografisch sortieren, während die `cmp`\-Funktionen nur die Zeichenfolgengleichheit testen, sind die `coll`\-Funktionen wesentlich langsamer als die entsprechenden `cmp`\-Versionen.  Daher, sollte das `coll`\-Funktionen verwendet werden, wenn es einen Unterschied zwischen der Zeichensatzreihenfolge gibt und der lexikografischen Reihenfolge in der aktuellen Codepage und diesem Unterschied relevant für den Zeichenfolgenvergleich ist.  
  
## Siehe auch  
 [Locale](../c-runtime-library/locale.md)   
 [Zeichenfolgenbearbeitung](../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll, \_mbsnbcoll\_l, \_mbsnbicoll, \_mbsnbicoll\_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, \_mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
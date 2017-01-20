---
title: "Locale"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Länderinformationen"
  - "Sprachinformationsroutinen"
  - "Gebietsschemaroutinen"
  - "Lokalisierung, Gebietsschema"
  - "setlocale-Funktion"
ms.assetid: 442f8112-9288-44d7-be3c-15d22652093a
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# Locale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*Gebietsschema* bezieht sich auf die Einstellungen für Land\/Region und Sprache, mit denen Sie Ihr Programm anpassen können.  Einige vom Gebietsschema abhängige Kategorien umfassen die Anzeigeformate für Datums\- und Währungswerte.  Weitere Informationen finden Sie unter [Gebietsschemakategorien](../c-runtime-library/locale-categories.md).  
  
 Verwenden Sie die [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)\-Funktion, um – bei der Verwendung von Funktionen ohne das `_l`\-Suffix – einige oder alle Gebietsschemainformationen des aktuellen Programms oder Threads zu ändern oder abzufragen.  Die Funktionen mit dem `_l`\-Suffix verwenden den Gebietsschemaparameter, der nur während der Ausführung dieser spezifischen Funktion für ihre Gebietsschemainformation übergeben wird.  Um ein Gebietsschema zu erstellen, das mit einer Funktion mit einem `_l`\-Suffix verwendet werden kann, verwenden Sie [\_create\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md).  Um dieses Gebietsschema freizugeben, verwenden Sie [\_free\_locale](../c-runtime-library/reference/free-locale.md).  Rufen Sie das aktuelle Gebietsschema mithilfe von [\_get\_current\_locale](../c-runtime-library/reference/get-current-locale.md) ab.  
  
 Steuern Sie mithilfe von [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md), ob jeder Thread über sein eigenes Gebietsschema verfügt, oder ob alle Threads in einem Programm das gleiche Gebietsschema verwenden.  Weitere Informationen finden Sie unter [Gebietsschemas und Codepages](../text/locales-and-code-pages.md).  
  
 Von den Funktionen in der folgenden Tabelle sind sicherere Versionen verfügbar, die durch das Suffix `_s` \("sicher"\) gekennzeichnet sind.  Weitere Informationen finden Sie unter [Sicherheitsfunktionen in der CRT](../c-runtime-library/security-features-in-the-crt.md).  
  
### Gebietsschemaabhängige Routinen  
  
|Routine|Verwendung|Abhängig von `setlocale`\-Kategorieneinstellungen|  
|-------------|----------------|-------------------------------------------------------|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Konvertieren von Zeichen in Gleitkommawert|`LC_NUMERIC`|  
|[atoi, \_atoi\_l, \_wtoi, \_wtoi\_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Konvertieren von Zeichen in ganzzahligen Wert|`LC_NUMERIC`|  
|[\_atoi64, \_atoi64\_l, \_wtoi64, \_wtoi64\_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Konvertieren von Zeichen in 64\-Bit\-Ganzzahlwert|`LC_NUMERIC`|  
|[atol, \_atol\_l, \_wtol, \_wtol\_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Konvertieren von Zeichen in langen Wert|`LC_NUMERIC`|  
|[\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Konvertieren von Zeichen in Wert mit doppelter Länge|`LC_NUMERIC`|  
|[is Routines](../c-runtime-library/is-isw-routines.md)|Testganzzahl für bestimmten Zustand.|`LC_CTYPE`|  
|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Test für führendes Byte|`LC_CTYPE`|  
|[localeconv](../c-runtime-library/reference/localeconv.md)|Lesen von entsprechenden Werten zum Formatieren von numerischen Mengen|`LC_MONETARY, LC_NUMERIC`|  
|[MB\_CUR\_MAX](../c-runtime-library/mb-cur-max.md)|Maximale Länge in Bytes eines beliebigen Multibytezeichens im aktuellen Gebietsschema \(in STDLIB.H per Makro definiert\)|`LC_CTYPE`|  
|[\_mbccpy, \_mbccpy\_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md),[\_mbccpy\_s, \_mbccpy\_s\_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Kopieren eines Multibytezeichens|`LC_CTYPE`|  
|[\_mbclen, mblen, \_mblen\_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Überprüfen und Zurückgeben einer Anzahl von Bytes in Multibytezeichen|`LC_CTYPE`|  
|[strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Bei Multibyte\-Zeichenfolgen: Überprüfen jedes Zeichens in der Zeichenfolge; Zurückgeben der Zeichenfolgenlänge|`LC_CTYPE`|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md),[mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Konvertieren von Multibytezeichensequenz in entsprechende Breitzeichensequenz|`LC_CTYPE`|  
|[mbtowc, \_mbtowc\_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Konvertieren von Multibytezeichen in entsprechendes Breitzeichen|`LC_CTYPE`|  
|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)\-Funktionen|Schreiben von formatierter Ausgabe|`LC_NUMERIC` \(bestimmt die Basiszeichenausgabe\)|  
|[scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)\-Funktionen|Lesen von formatierter Eingabe|`LC_NUMERIC` \(bestimmt die Basiszeichenerkennung\)|  
|[setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)|Auswählen von Gebietsschema für Programm|Nicht zutreffend|  
|[strcoll, wcscoll, \_mbscoll, \_strcoll\_l, \_wcscoll\_l, \_mbscoll\_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Vergleichen von Zeichen zweier Zeichenfolgen|`LC_COLLATE`|  
|[\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|Vergleichen zweier Zeichenfolgen ohne Berücksichtigung von Groß\-\/Kleinbuchstaben|`LC_CTYPE`|  
|[\_stricoll, \_wcsicoll, \_mbsicoll, \_stricoll\_l, \_wcsicoll\_l, \_mbsicoll\_l](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Vergleichen von Zeichen zweier Zeichenfolgen \(ohne Berücksichtigung von Groß\-\/Kleinbuchstaben\)|`LC_COLLATE`|  
|[\_strncoll, \_wcsncoll, \_mbsncoll, \_strncoll\_l, \_wcsncoll\_l, \_mbsncoll\_l](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Vergleichen der ersten `n` Zeichen von zwei Zeichenfolgen|`LC_COLLATE`|  
|[\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|Vergleichen von Zeichen zweier Zeichenfolgen ohne Berücksichtigung von Groß\-\/Kleinbuchstaben.|`LC_CTYPE`|  
|[\_strnicoll, \_wcsnicoll, \_mbsnicoll, \_strnicoll\_l, \_wcsnicoll\_l, \_mbsnicoll\_l](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Vergleichen der ersten `n` Zeichen zweier Zeichenfolgen \(ohne Berücksichtigung von Groß\-\/Kleinbuchstaben\)|`LC_COLLATE`|  
|[strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Formatieren von Datums\- und Uhrzeitwert nach angegebenem `format`\-Argument|`LC_TIME`|  
|[\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md),[\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Konvertieren von jedem Großbuchstaben in angegebener Zeichenfolge in Kleinbuchstaben an jeweiliger Stelle|`LC_CTYPE`|  
|[strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Konvertieren von Zeichenfolge in `double`\-Wert|`LC_NUMERIC` \(bestimmt die Basiszeichenerkennung\)|  
|[strtol, wcstol, \_strtol\_l, \_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Bekehrtzeichenfolge zu `long`\-Wert|`LC_NUMERIC` \(bestimmt die Basiszeichenerkennung\)|  
|[strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Konvertieren von Zeichenfolge in langen Wert ohne Vorzeichen|`LC_NUMERIC` \(bestimmt die Basiszeichenerkennung\)|  
|[\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md),[\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|Konvertieren von jedem Kleinbuchstaben in angegebener Zeichenfolge in Großbuchstaben an jeweiliger Stelle|`LC_CTYPE`|  
|[strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Transformieren von Zeichenfolge in sortierte Form gemäß Gebietsschema|`LC_COLLATE`|  
|[tolower, \_tolower, towlower, \_tolower\_l, \_towlower\_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md),[\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Konvertieren von angegebenem Zeichen zu entsprechendem Kleinbuchstaben|`LC_CTYPE`|  
|[toupper, \_toupper, towupper, \_toupper\_l, \_towupper\_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md),[\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Konvertieren von angegebenem Zeichen zu entsprechendem Großbuchstaben|`LC_CTYPE`|  
|[wcstombs, \_wcstombs\_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md),[wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Konvertieren von Breitzeichensequenz in entsprechende Multibytezeichensequenz|`LC_CTYPE`|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md),[wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Konvertieren von Breitzeichen in entsprechendes Multibytezeichen|`LC_CTYPE`|  
  
> [!NOTE]
>  Bei Multibyte\-Routinen muss die Multibyte\-Codepage dem mit [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) festgelegten Gebietsschema entsprechen.  Wenn [\_setmbcp](../c-runtime-library/reference/setmbcp.md) über ein Argument von `_MB_CP_LOCALE` verfügt, ist die Multibyte\-Codepage mit der `setlocale`\-Codepage identisch.  
  
## Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
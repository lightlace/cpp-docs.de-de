---
title: "Interpretation von Mehrbytezeichensequenzen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.character.multibyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MBCS [C++], Gebietsschema-Codepage"
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Interpretation von Mehrbytezeichensequenzen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die meisten Mehrbytezeichenroutinen in der Microsoft\-Laufzeitbibliothek erkennen Mehrbytezeichensequenzen in Bezug auf eine Mehrbyte\-Codepage.  Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  
  
### Gebietsschemaabhängige Mehrbyte\-Routinen  
  
|Routine|Verwendung|  
|-------------|----------------|  
|[\_mbclen, mblen, \_mblen\_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Überprüfen und Zurückgeben einer Anzahl von Bytes in Multibytezeichen|  
|[strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Für ergebenden: überprüfen Sie jedes Zeichen in der Zeichenfolge; geben Sie Zeichenfolgenlänge zurück.  Für Zeichenfolgen mit Breitzeichen: Rückholzeichenfolgenlänge.|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Konvertieren von Multibytezeichensequenz in entsprechende Breitzeichensequenz|  
|[mbtowc, \_mbtowc\_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Konvertieren von Multibytezeichen in entsprechendes Breitzeichen|  
|[wcstombs, \_wcstombs\_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Konvertieren von Breitzeichensequenz in entsprechende Multibytezeichensequenz|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Konvertieren von Breitzeichen in entsprechendes Multibytezeichen|  
  
## Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
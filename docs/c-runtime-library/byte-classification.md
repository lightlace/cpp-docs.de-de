---
title: "Byteklassifizierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.types.bytes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Byteklassifizierungsroutinen"
  - "Bytes, Testen"
  - "Codepage 932"
ms.assetid: 1cb52d71-fb0c-46ca-aad7-6472c1103370
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Byteklassifizierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede dieser Routinen testet ein bestimmtes Byte eines Mehrbytezeichens für Kundenzufriedenheit einer Bedingung.  Neben wo angegeben; andernfalls der Ausgabewert durch die Einstellung der `LC_CTYPE` Kategorieneinstellung des Gebietsschemas beeinflusst wird; Weitere Informationen finden Sie unter [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  
  
> [!NOTE]
>  Definitionsgemäß sind die ASCII\-Zeichen zwischen 0 und 127 eine Teilmenge jedes Mehrbyte\-Zeichensatzes.  Beispielsweise enthält der Japanerkatakana\-Zeichensatz ASCII sowie Nicht\-ASCII\-Zeichen.  
  
 Die vordefinierten Konstanten der folgenden Tabelle werden in CTYPE.H. definiert.  
  
### Mehrbytezeichen\-Byte\-Klassifizierungs\-Routinen  
  
|Routine|Byte\-Testbedingung|.NET Framework\-Entsprechung|  
|-------------|-------------------------|----------------------------------|  
|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Führendes Byte; Testergebnis hängt von der `LC_CTYPE` Kategorieneinstellung des aktuellen Gebietsschemas ab|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbalnum, \_ismbbalnum\_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum &#124;&#124; _ismbbkalnum`|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbalpha, \_ismbbalpha\_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|`isalpha &#124;&#124; _ismbbkalnum`|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbgraph, \_ismbbgraph\_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|Wie wie `_ismbbprint`, aber `_ismbbgraph` enthält nicht das Leerzeichen ein \(0x20\)|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbkalnum, \_ismbbkalnum\_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Nicht\-ASCII\-Textsymbol, das kein Interpunktionszeichen ist.  Beispielsweise in Codepage 932 nur, Katakana alphanumerisch Tests für `_ismbbkalnum`|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbkana, \_ismbbkana\_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana \(0xA1 \- 0xDF, Codepage\- nur 932\)|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbkprint, \_ismbbkprint\_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|Nicht\-ASCII\-Textsymbol oder Nicht\-ASCII\-Interpunktionssymbol.  Beispielsweise testet in Codepage 932 `_ismbbkprint` nur auf alphanumerische Katakana\-Zeichen oder Katakana\-Interpunktion \(Bereich: 0xA1–0xDF\).|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbkpunct, \_ismbbkpunct\_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|Nicht\-ASCII\-Interpunktion.  Beispielsweise testet `_ismbbkpunct` nur in Codepage 932 auf Katakana\-Interpunktion.|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbblead, \_ismbblead\_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Erstes Byte eines Multibytezeichens.  Beispielsweise sind die gültigen Bereiche nur in Codepage 932 0x81–0x9F, 0xE0–0xFC.|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbprint, \_ismbbprint\_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint &#124;&#124; _ismbbkprint. ismbbprint` schließt das Leerzeichen ein \(0x20\)|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbpunct, \_ismbbpunct\_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct &#124;&#124; _ismbbkpunct`|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbtrail, \_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Zweites Byte eines Multibytezeichens.  Beispielsweise sind die gültigen Bereiche nur in Codepage 932 0x40–0x7E, 0x80–0xEC.|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbslead, \_ismbslead\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Führendes Byte \(im Zeichenfolgenkontext\)|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[ismbstrail, \_ismbstrail\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Nachfolgendes Byte \(im Zeichenfolgenkontext\)|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_mbbtype, \_mbbtype\_l](../c-runtime-library/reference/mbbtype-mbbtype-l.md)|Rückholbytetyp auf Grundlage Vorheriges Byte|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_mbsbtype, \_mbsbtype\_l](../c-runtime-library/reference/mbsbtype-mbsbtype-l.md)|Rückgabetyp der Bytes in der Zeichenfolge|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[mbsinit](../c-runtime-library/reference/mbsinit.md)|Verfolgt den Zustand einer Multibytezeichen\-Konvertierung.|Nicht zutreffend, aber finden Sie unter [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
  
 Das Makro `MB_LEN_MAX`, die in LIMITS.H, erweitert der maximalen Länge in Bytes, die jedes Mehrbytezeichen haben kann.  `MB_CUR_MAX`, die in STDLIB.H, erweitert der maximalen Länge in Bytes eines beliebigen Mehrbytezeichens im aktuellen Gebietsschema.  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
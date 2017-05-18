---
title: _ismbb-Routinen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _ismbb
- ismbb
dev_langs:
- C++
helpviewer_keywords:
- ismbb routines
- _ismbb routines
ms.assetid: d63c232e-3fe4-4844-aafd-2133846ece4b
caps.latest.revision: 14
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: a9e24e349b829d9547037bba31c940f9af25f80c
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="ismbb-routines"></a>_ismbb-Routinen
Testet den angegebenen ganzzahligen Wert `c` unter Verwendung des aktuellen Gebietsschemas oder einer angegebenen LC_CTYPE-Konvertierungszustandskategorie auf eine bestimmte Bedingung.  
  
|||  
|-|-|  
|[_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|[_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|  
|[_ismbbalpha, _ismbbalpha_l](http://msdn.microsoft.com/en-us/8e54cb92-fc2b-41f5-8ab4-b22ac8aa9ad0)|[_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|  
|[_ismbbblank, _ismbbblank_l](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|[_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|  
|[_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|[_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|  
|[_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|[_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|  
|[_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|[_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|  
  
## <a name="remarks"></a>Hinweise  
 Jede Routine in der `_ismbb` -Gruppe testet den angegebenen ganzzahligen Wert `c` auf eine bestimmte Bedingung. Das Testergebnis hängt von der gültigen Multibyte-Codepage ab. Standardmäßig wird die Multibyte-Codepage auf die Standard-ANSI-Codepage festgelegt, die vom Betriebssystem beim Programmstart abgerufen wird. Sie können die verwendete Multibyte-Codepage mit [_getmbcp](../c-runtime-library/reference/getmbcp.md) abfragen oder mit [_setmbcp](../c-runtime-library/reference/setmbcp.md) ändern.  
  
 Der Ausgabewert ist von der Kategorieeinstellung `LC_CTYPE` des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen, die das **_l** -Suffix nicht verwenden, verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten. Die Versionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch stattdessen den übergebenen Gebietsschemaparameter.  
  
 Die Routinen in der `_ismbb` -Gruppe testen die angegebene ganze Zahl `c` wie folgt.  
  
|Routine|Byte-Testbedingung|  
|-------------|-------------------------|  
|[_ismbbalnum](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum` &#124;&#124; `_ismbbkalnum`.|  
|[_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md)|`isalpha` &#124;&#124; `_ismbbkalnum`.|  
|[_ismbbblank](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|`isblank`|  
|[_ismbbgraph](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|Wie `_ismbbprint`, aber `_ismbbgraph` enthält nicht das Leerzeichen (0x20).|  
|[_ismbbkalnum](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Nicht-ASCII-Textsymbol, das kein Interpunktionszeichen ist. Beispielsweise testet `_ismbbkalnum` nur in Codepage 932 auf alphanumerische Katakana-Zeichen.|  
|[_ismbbkana](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Katakana (0xA1–0xDF) Besonderheit bei Codepage 932.|  
|[_ismbbkprint](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|Nicht-ASCII-Textsymbol oder Nicht-ASCII-Interpunktionssymbol. `_ismbbkprint` testet beispielsweise in Codepage 932 nur auf alphanumerische Katakana-Zeichen oder Katakana-Interpunktion (Bereich: 0xA1–0xDF).|  
|[_ismbbkpunct](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|Nicht-ASCII-Interpunktion. Beispielsweise testet `_ismbbkpunct` nur in Codepage 932 auf Katakana-Interpunktion.|  
|[_ismbblead](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Erstes Byte eines Multibytezeichens. Gültige Bereiche sind in Codepage 932 beispielsweise nur 0x81–0x9F, 0xE0–0xFC.|  
|[_ismbbprint](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint` &#124;&#124; `_ismbbkprint`. **ismbbprint** schließt das Leerzeichen ein (0x20).|  
|[_ismbbpunct](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct` &#124;&#124; `_ismbbkpunct`.|  
|[_ismbbtrail](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Zweites Byte eines Multibytezeichens. Gültige Bereiche sind in Codepage 932 beispielsweise nur 0x40–0x7E, 0x80–0xEC.|  
  
 Die folgende Tabelle zeigt die ORed-Werte an, aus denen sich die Testbedingungen für die Routinen zusammensetzen. Die Manifestkonstanten `_BLANK`, `_DIGIT`, `_LOWER`, `_PUNCT`und `_UPPER` werden in Ctype.h definiert.  
  
|Routine|_BLANK|_DIGIT|LOWER|_PUNCT|UPPER|Non-<br /><br /> ASCII<br /><br /> Text|Non-<br /><br /> ASCII<br /><br /> punct|  
|-------------|-------------|-------------|-----------|-------------|-----------|------------------------------|-------------------------------|  
|`_ismbbalnum`|—|w|w|—|w|w|—|  
|`_ismbbalpha`|—|—|w|—|w|w|—|  
|`_ismbbblank`|w|—|—|—|—|—|—|  
|`_ismbbgraph`|—|w|w|w|w|w|w|  
|`_ismbbkalnum`|—|—|—|—|—|w|—|  
|`_ismbbkprint`|—|—|—|—|—|w|w|  
|`_ismbbkpunct`|—|—|—|—|—|—|w|  
|`_ismbbprint`|w|w|w|w|w|w|w|  
|`_ismbbpunct`|—|—|—|w|—|—|w|  
  
 Die `_ismbb` -Routinen werden sowohl als Funktionen als auch als Makros implementiert. Weitere Informationen zum Auswählen einer Implementierung finden Sie unter [Empfehlungen für die Wahl zwischen Funktionen und Macros](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Byteklassifizierung](../c-runtime-library/byte-classification.md)   
 [is- und isw-Routinen](../c-runtime-library/is-isw-routines.md)   
 [_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)   
 [_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)

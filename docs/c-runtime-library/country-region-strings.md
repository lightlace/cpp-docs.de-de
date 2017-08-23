---
title: "Zeichenfolgen für Länder und Regionen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
caps.latest.revision: 14
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
ms.translationtype: HT
ms.sourcegitcommit: 22da7776e46171467a37d46c3de3227f060eaf77
ms.openlocfilehash: 272ce38cee55661a3f4a1eb751c8808b355b59be
ms.contentlocale: de-de
ms.lasthandoff: 08/11/2017

---
# <a name="countryregion-strings"></a>Country/Region Strings
Zeichenfolgen für Länder und Regionen können mit einer Sprachenzeichenfolge kombiniert werden, um eine Gebietsschemaspezifikation für die Funktionen `setlocale`, `_wsetlocale`, `_create_locale`und `_wcreate_locale` zu erstellen. Listen der Länder-/Regionsnamen, die von verschiedenen Windows-Betriebssystemversionen unterstützt werden, finden Sie unter [National Language Support (NLS) API Reference](https://www.microsoft.com/resources/msdn/goglobal/default.mspx) (API-Referenz für die Unterstützung von Landessprachen). In den Listen kann die Zeichenfolge für Land/Region einer der Werte in der Spalte **Locale – Language County/Region** oder eine der Abkürzungen in der Spalte **Country or Region name abbreviation** sein. Weitere Informationen zur Sprachunterstützung in Windows-Betriebssystemen nach Version finden Sie unter [Appendix A: Product Behavior](http://msdn.microsoft.com/goglobal/bb896001.aspx) in „[MS-LCID]: Windows Language Code Identifier (LCID) Reference“ (Anhang A: Produktverhalten in „[MS-LCID]: Windows-Sprachcodebezeichner – Referenz“).  
  
 Die Implementierung der C-Laufzeitbibliothek unterstützt auch die folgenden zusätzlichen Land-/Regionszeichenfolgen und Abkürzungen:  
  
|Land-/Regionszeichenfolge|Abkürzung|Entsprechender Gebietsschemaname|  
|----------------------------|------------------|----------------------------|  
|america|USA|en-US|  
|britain|GBR|en-GB|  
|china|CHN|zh-CN|  
|czech|CZE|cs-CZ|  
|england|GBR|en-GB|  
|great britain|GBR|en-GB|  
|holland|NLD|nl-NL|  
|hong-kong|HKG|zh-HK|  
|new-zealand|NZL|en-NZ|  
|nz|NZL|en-NZ|  
|pr china|CHN|zh-CN|  
|pr-china|CHN|zh-CN|  
|puerto-rico|PRI|es-PR|  
|slovak|SVK|sk-SK|  
|south africa|ZAF|af-ZA|  
|south korea|KOR|ko-KR|  
|south-africa|ZAF|af-ZA|  
|south-korea|KOR|ko-KR|  
|trinidad & tobago|TTO|en-TT|  
|uk|GBR|en-GB|  
|united-kingdom|GBR|en-GB|  
|united-states|USA|en-US|  
|mehreren|USA|en-US|  
  
## <a name="see-also"></a>Siehe auch  
 [Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Sprachzeichenfolgen](../c-runtime-library/language-strings.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)

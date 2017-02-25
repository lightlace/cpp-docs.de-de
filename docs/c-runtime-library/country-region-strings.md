---
title: "L&#228;nder-/Regionszeichenfolgen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.strings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Sprache/Land-Zeichenfolgen"
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# L&#228;nder-/Regionszeichenfolgen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zeichenfolgen für Länder und Regionen können mit einer Sprachenzeichenfolge kombiniert werden, um eine Gebietsschemaspezifikation für die Funktionen `setlocale`, `_wsetlocale`, `_create_locale` und `_wcreate_locale` zu erstellen. Eine Liste der von den verschiedenen Windows\-Betriebssystemversionen unterstützten Länder\- und Regionsnamen finden Sie unter der [Referenz zur NLS\(National Language Support\)\-API](http://msdn.microsoft.com/goglobal/bb896001.aspx). In der Liste kann die Land\-\/Regionszeichenfolge irgendein Landeswert aus der Spalte **Gebietsschema – Sprache Land\/Region** oder irgendeine Abkürzung aus der Spalte **Abkürzung des Landes\- oder Regionsnamens** sein.  
  
 Die Implementierung der C\-Laufzeitbibliothek unterstützt auch die folgenden zusätzlichen Land\-\/Regionszeichenfolgen und Abkürzungen:  
  
|Land\-\/Regionszeichenfolge|Abkürzung|Entsprechender Gebietsschemaname|  
|---------------------------------|---------------|--------------------------------------|  
|america|USA|en\-US|  
|britain|GBR|en\-GB|  
|china|CHN|zh\-CN|  
|czech|CZE|cs\-CZ|  
|england|GBR|en\-GB|  
|great britain|GBR|en\-GB|  
|holland|NLD|nl\-NL|  
|hong\-kong|HKG|zh\-HK|  
|new\-zealand|NZL|en\-NZ|  
|nz|NZL|en\-NZ|  
|pr china|CHN|zh\-CN|  
|pr\-china|CHN|zh\-CN|  
|puerto\-rico|PRI|es\-PR|  
|slovak|SVK|sk\-SK|  
|south africa|ZAF|af\-ZA|  
|south korea|KOR|ko\-KR|  
|south\-africa|ZAF|af\-ZA|  
|south\-korea|KOR|ko\-KR|  
|trinidad & tobago|TTO|en\-TT|  
|uk|GBR|en\-GB|  
|united\-kingdom|GBR|en\-GB|  
|united\-states|USA|en\-US|  
|mehreren|USA|en\-US|  
  
## Siehe auch  
 [Gebietsschema\-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Sprachzeichenfolgen](../c-runtime-library/language-strings.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
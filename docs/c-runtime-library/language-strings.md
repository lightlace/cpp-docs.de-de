---
title: "Sprachzeichenfolgen"
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
  - "c.strings"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Sprachezeichenfolgen"
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# Sprachzeichenfolgen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Funktionen `setlocale` und `_create_locale` können die von der Windows NLS\-API unterstützten Sprachen auf Betriebssystemen verwenden, die nicht die Unicode\-Codepage verwenden.  Eine Liste der unterstützten Sprachen nach Betriebssystemversion finden Sie in der [Referenz zur Unterstützung der Landessprache \(National Language Support, NLS\)](http://msdn.microsoft.com/goglobal/bb896001.aspx).  Die Sprachenzeichenfolge kann ein beliebiger Wert aus den Spalten für die **Sprache** und die **Abkürzung der Sprachnamen** der Liste der unterstützten Sprachen sein.  Die Implementierung der C\-Laufzeitbibliothek unterstützt ebenfalls diese Sprachenzeichenfolgen:  
  
|Sprachenzeichenfolge|Entsprechender Gebietsschemaname|  
|--------------------------|--------------------------------------|  
|american|en\-US|  
|american english|en\-US|  
|american\-english|en\-US|  
|australian|en\-AU|  
|belgian|nl\-BE|  
|canadian|en\-CA|  
|chh|zh\-HK|  
|chi|zh\-SG|  
|chinese|zh|  
|chinese\-hongkong|zh\-HK|  
|chinese\-simplified|zh\-CN|  
|chinese\-singapore|zh\-SG|  
|chinese\-traditional|zh\-TW|  
|dutch\-belgian|nl\-BE|  
|english\-american|en\-US|  
|english\-aus|en\-AU|  
|english\-belize|en\-BZ|  
|english\-can|en\-CA|  
|english\-caribbean|en\-029|  
|english\-ire|en\-IE|  
|english\-jamaica|en\-JM|  
|english\-nz|en\-NZ|  
|english\-south africa|en\-ZA|  
|english\-trinidad y tobago|en\-TT|  
|english\-uk|en\-GB|  
|english\-us|en\-US|  
|english\-usa|en\-US|  
|french\-belgian|fr\-BE|  
|french\-canadian|fr\-CA|  
|french\-luxembourg|fr\-LU|  
|french\-swiss|fr\-CH|  
|german\-austrian|de\-AT|  
|german\-lichtenstein|de\-LI|  
|german\-luxembourg|de\-LU|  
|german\-swiss|de\-CH|  
|irish\-english|en\-IE|  
|italian\-swiss|it\-CH|  
|norwegian|nein|  
|norwegian\-bokmal|nb\-NO|  
|norwegian\-nynorsk|nn\-NO|  
|portuguese\-brazilian|pt\-BR|  
|spanish\-argentina|es\-AR|  
|spanish\-bolivia|es\-BO|  
|spanish\-chile|es\-CL|  
|spanish\-colombia|es\-CO|  
|spanish\-costa rica|es\-CR|  
|spanish\-dominican republic|es\-DO|  
|spanish\-ecuador|es\-EC|  
|spanish\-el salvador|es\-SV|  
|spanish\-guatemala|es\-GT|  
|spanish\-honduras|es\-HN|  
|spanish\-mexican|es\-MX|  
|spanish\-modern|es\-ES|  
|spanish\-nicaragua|es\-NI|  
|spanish\-panama|es\-PA|  
|spanish\-paraguay|es\-PY|  
|spanish\-peru|es\-PE|  
|spanish\-puerto rico|es\-PR|  
|spanish\-uruguay|es\-UY|  
|spanish\-venezuela|es\-VE|  
|swedish\-finland|sv\-FI|  
|swiss|de\-CH|  
|uk|en\-GB|  
|mehreren|en\-US|  
|usa|en\-US|  
  
## Siehe auch  
 [Gebietsschema\-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Länder\-\/Regionszeichenfolgen](../c-runtime-library/country-region-strings.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
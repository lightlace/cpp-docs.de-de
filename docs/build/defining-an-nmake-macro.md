---
title: "Definieren eines NMAKE-Makros"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Definieren von NMAKE-Makros"
  - "Makros, NMAKE"
  - "NMAKE-Makros, Definieren"
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Definieren eines NMAKE-Makros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
macroname=string  
```  
  
## Hinweise  
 Bei *macroname* handelt es sich um eine Kombination aus Buchstaben, Ziffern und Unterstrichen \(**\_**\) von bis zu 1024 Zeichen, die Groß\-\/Kleinschreibung beachtet.  *macroname* kann ein aufgerufenes Makro enthalten.  Besteht *macroname* vollständig aus einem aufgerufenen Makro, kann das aufgerufene Makro nicht NULL bzw. undefiniert sein.  
  
 Bei *string* kann es sich um eine beliebige Sequenz aus keinem, einem oder mehr Zeichen handeln.  Eine NULL\-Zeichenfolge enthält kein Zeichen oder lediglich Leerzeichen oder Tabstopps.  `string` kann einen Makroaufruf enthalten.  
  
## Worüber möchten Sie mehr erfahren?  
 [Sonderzeichen in Makros](../build/special-characters-in-macros.md)  
  
 [NULL\-Makros und undefinierte Makros](../build/null-and-undefined-macros.md)  
  
 [Definieren von Makros](../build/where-to-define-macros.md)  
  
 [Vorrang bei Makrodefinitionen](../build/precedence-in-macro-definitions.md)  
  
## Siehe auch  
 [Makros und NMAKE](../build/macros-and-nmake.md)
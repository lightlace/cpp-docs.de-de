---
title: "Befehlsmakros und Optionsmakros"
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
  - "Befehlsmakros in NMAKE"
  - "Makros, Befehlsmakros"
  - "Makros, Optionenmakros"
  - "Optionenmakros"
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Befehlsmakros und Optionsmakros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Befehlsmakros sind für Microsoft\-Produkte vordefiniert.  Optionenmakros repräsentieren Optionen zu diesen Produkten und sind standardmäßig undefiniert.  Sie werden in vordefinierten Rückschlussregeln verwendet und können in Beschreibungsblöcken oder benutzerdefinierten Rückschlussregeln verwendet werden.  Befehlsmakros können neu definiert werden, um einen Teil oder die gesamte Befehlszeile, einschließlich der Optionen, zu repräsentieren.  Optionenmakros generieren eine NULL\-Zeichenfolge, wenn sie undefiniert bleiben.  
  
|Microsoft\-Produkt|Befehlsmakro|Definiert als|Optionenmakro|  
|------------------------|------------------|-------------------|-------------------|  
|Macro Assembler|**AS**|ml|**AFLAGS**|  
|Basic\-Compiler|**BC**|bc|**BFLAGS**|  
|C\-Compiler|**CC**|cl|**CFLAGS**|  
|C\+\+\-Compiler|**CPP**|cl|**CPPFLAGS**|  
|C\+\+\-Compiler|**CXX**|cl|**CXXFLAGS**|  
|Ressourcencompiler|**RC**|rc|**RFLAGS**|  
  
## Siehe auch  
 [Besondere NMAKE\-Makros](../build/special-nmake-macros.md)
---
title: "Befehlsmakros und Optionsmakros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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
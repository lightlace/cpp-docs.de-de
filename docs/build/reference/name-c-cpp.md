---
title: "NAME (C/C++)"
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
  - "name"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NAME-Anweisung in DEF-Dateien"
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# NAME (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt einen Namen für die Hauptausgabedatei fest.  
  
```  
NAME [application][BASE=address]  
```  
  
## Hinweise  
 Alternativ kann der Name der Ausgabedatei auch mit der [\/OUT](../../build/reference/out-output-file-name.md)\-Linkeroption angegeben werden, genauso wie die Basisdadresse auch durch die [\/BASE](../../build/reference/base-base-address.md)\-Linkeroption festgelegt werden kann.  Werden beide angegeben, wird **NAME** durch **\/OUT** überschrieben.  
  
 Wenn Sie eine DLL erstellen, wirkt sich **NAME** lediglich auf den Namen der DLL aus.  
  
## Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)
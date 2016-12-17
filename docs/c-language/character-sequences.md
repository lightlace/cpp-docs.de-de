---
title: "Zeichenfolgen"
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
  - "C"
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Zeichenfolgen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** Die Zuordnung der Quelldatei\-Zeichenfolgen  
  
 Präprozessoranweisungen verwenden den gleichen Zeichensatz wie Quelldateianweisungen, mit der Ausnahme, dass Escapesequenzen nicht unterstützt werden.  
  
 Um einen Pfad für eine Includedatei anzugeben, verwenden Sie nur einen umgekehrten Schrägstrich:  
  
```  
#include "path1\path2\myfile"  
```  
  
 Im Quellcode sind zwei umgekehrte Schrägstriche erforderlich:  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## Siehe auch  
 [Präprozessordirektiven](../c-language/preprocessing-directives.md)
---
title: "COMM"
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
  - "COMM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMM directive"
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# COMM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Kommunalvariable mit den Attributen, die in `definition`angegeben werden.  
  
## Syntax  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## Hinweise  
 Jedes `definition` verfügt über das folgende Format:  
  
 \[\[*langtype***NAHE**\[\[\]\] &#124; **FAR**\]\]**:** *Bezeichnung*`type`\[\[:\-*Anzahl*\]\]  
  
 Die *Bezeichnung* ist der Name der Variablen.  `type` kann jeder Typspezifizierer \([BYTE](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)usw.\) oder eine ganze Zahl sein, die die Anzahl von Bytes angibt.  Die *Anzahl* gibt die Anzahl von Datenobjekten an \(der Standardwert\) von ist.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)
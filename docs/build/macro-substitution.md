---
title: "Makroersetzung"
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
  - "Makros, NMAKE"
  - "NMAKE (Programm), Makroersetzung"
  - "Substitutionsmakros in NMAKE"
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Makroersetzung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn *macroname* aufgerufen wird, wird jedes Auftreten von *string1* in der Definitionszeichenfolge durch *string2* ersetzt.  
  
## Syntax  
  
```  
$(macroname:string1=string2)  
```  
  
## Hinweise  
 Die Makroersetzung beachtet die Groß\-\/Kleinschreibung und ist literal. Es können keine Makros durch *string1* und *string2* aufgerufen werden.  Die Ersetzung ändert die ursprüngliche Definition nicht.  Text kann in einem beliebigen vordefinierten Makro außer im [$$@](../build/filename-macros.md)\-Makro ersetzt werden.  
  
 Vor dem Doppelpunkt befinden sich keine Leerzeichen oder Tabstopps. Leerzeichen oder Tabstopps nach dem Doppelpunkt werden als Literale interpretiert.  Wenn *string2* den Wert NULL aufweist, wird das Auftreten von *string1* aus der Definitionszeichenfolge des Makros gelöscht.  
  
## Siehe auch  
 [Verwenden eines NMAKE\-Makros](../build/using-an-nmake-macro.md)
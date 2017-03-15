---
title: "Verwenden eines NMAKE-Makros | Microsoft Docs"
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
  - "Makros, NMAKE"
  - "NMAKE-Makros, Verwenden"
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Verwenden eines NMAKE-Makros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei der Verwendung eines Makros wird der Name nach einem Dollarzeichen \($\) in Klammern eingeschlossen, wie im Folgenden dargestellt:  
  
## Syntax  
  
```  
$(macroname)  
```  
  
## Hinweise  
 Es sind keine Leerzeichen zulässig.  Die Klammern sind optional, wenn *macroname* nur aus einem einzelnen Zeichen besteht.  Die Definitionszeichenfolge ersetzt **$\(***macroname*\). Ein undefiniertes Makro wird durch eine NULL\-Zeichenfolge ersetzt.  
  
## Worüber möchten Sie mehr erfahren?  
 [Makroersetzung](../build/macro-substitution.md)  
  
## Siehe auch  
 [Makros und NMAKE](../build/macros-and-nmake.md)
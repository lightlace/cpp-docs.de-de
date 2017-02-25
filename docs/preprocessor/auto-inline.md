---
title: "auto_inline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "auto_inline_CPP"
  - "vc-pragma.auto_inline"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_inline-Pragma"
  - "Pragmas, auto_inline"
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# auto_inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließt alle Funktionen aus, die innerhalb des Bereichs definiert sind, in dem **off** durch die Betrachtung als Kandidaten für die automatische Inlineerweiterung angegeben wird.  
  
## Syntax  
  
```  
  
#pragma auto_inline( [{on | off}] )  
```  
  
## Hinweise  
 Um das **auto\_inline**\-Pragma zu verwenden, platzieren Sie es vor und unmittelbar nach \(jedoch nicht in\) einer Funktionsdefinition.  Dieses Pragma tritt mit der ersten Funktionsdefinition in Kraft, nachdem das Pragma angezeigt wird.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
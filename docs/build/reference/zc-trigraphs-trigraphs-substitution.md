---
title: "/Zc:trigraphs (Trigraphen-Ersetzung) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (Compileroptionen) [C++]"
  - "Übereinstimmung (Compileroptionen)"
  - "Zc (Compileroptionen) [C++]"
  - "-Zc (Compileroptionen) [C++]"
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Zc:trigraphs (Trigraphen-Ersetzung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn **\/Zc:trigraphs** angegeben wird, ersetzt der Compiler mit einem entsprechenden Interpunktionszeichen eine Trigraphzeichensequenz.  Geben Sie zum Deaktivieren der Trigraphersetzung **\/Zc:trigraphs\-** an.  **\/Zc:trigraphs** ist standardmäßig deaktiviert.  
  
## Syntax  
  
```  
/Zc:trigraphs[-]  
```  
  
## Hinweise  
 Ein Trigraph besteht aus zwei aufeinander folgenden Fragezeichen \("??"\) gefolgt von einem eindeutigen dritten Zeichen.  Der Compiler ersetzt z. B. den "??\="\-Trigraphen mit dem \#\-Zeichen.  Verwenden Sie Trigraphen in C\-Quelldateien, die einen Zeichensatz verwenden, der keine zweckmäßigen grafischen Darstellungen für einige Interpunktionszeichen enthält.  
  
 Eine Liste von C\/C\+\+\-Trigraphen, und ein Beispiel, das zeigt, wie Trigraphen verwendet werden, erhalten Sie unter [Trigraphen](../../c-language/trigraphs.md).  
  
## Siehe auch  
 [\/Zc \(Übereinstimmung\)](../../build/reference/zc-conformance.md)   
 [Trigraphen](../../c-language/trigraphs.md)
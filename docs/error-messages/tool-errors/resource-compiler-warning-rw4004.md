---
title: "Ressourcencompiler: Warnung RW4004"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "RW4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW4004"
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ressourcencompiler: Warnung RW4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ASCII\-Zeichen entspricht nicht virtuellem Tastencode  
  
 Ein Zeichenfolgenliteral wurde als virtueller Tastencode für eine Zugriffstaste vom Typ **VIRTKEY** verwendet.  
  
 Der Vorgang kann nach dieser Warnung fortgesetzt werden, die generierten Zugriffstasten entsprechen aber möglicherweise nicht der angegebenen Zeichenfolge. Bei **VIRTKEY**s werden andere Tastencodes als bei **ASCII**\-Zugriffstasten verwendet.  
  
 Auch wenn Zeichenfolgenliterale syntaktisch gültig sind, können Sie nur durch Verwenden der **VK\_\* \#define**\-Werte in WINDOWS.h sicherstellen, dass Sie die gewünschte Zugriffstaste erhalten.
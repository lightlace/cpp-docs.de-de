---
title: "Ressourcencompiler: Warnung RW4004 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RW4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW4004"
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Warnung RW4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ASCII\-Zeichen entspricht nicht virtuellem Tastencode  
  
 Ein Zeichenfolgenliteral wurde als virtueller Tastencode für eine Zugriffstaste vom Typ **VIRTKEY** verwendet.  
  
 Der Vorgang kann nach dieser Warnung fortgesetzt werden, die generierten Zugriffstasten entsprechen aber möglicherweise nicht der angegebenen Zeichenfolge. Bei **VIRTKEY**s werden andere Tastencodes als bei **ASCII**\-Zugriffstasten verwendet.  
  
 Auch wenn Zeichenfolgenliterale syntaktisch gültig sind, können Sie nur durch Verwenden der **VK\_\* \#define**\-Werte in WINDOWS.h sicherstellen, dass Sie die gewünschte Zugriffstaste erhalten.
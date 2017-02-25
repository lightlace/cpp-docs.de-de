---
title: "Compilerwarnung (Stufe 1) C4651 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4651"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4651"
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4651
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Definition' für vorkompilierte Headerdatei, aber nicht für aktuelle Kompilierung angegeben  
  
 Die Definition wurde zwar beim Erstellen der vorkompilierten Headerdatei, nicht aber bei der aktuellen Kompilierung angegeben.  
  
 Innerhalb des vorkompilierten Headers hat die Definition Gültigkeit, im übrigen Code jedoch nicht.  
  
 Wenn ein vorkompilierter Header mit \/DSYMBOL erstellt wurde und die \/Yu\-Kompilierung kein \/DSYMBOL enthält, wird vom Compiler diese Warnmeldung ausgegeben.  Durch Hinzufügen von \/DSYMBOL in die \/Yu\-Befehlszeile kann das Problem behoben werden.
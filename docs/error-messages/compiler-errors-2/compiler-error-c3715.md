---
title: "Compilerfehler C3715 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3715"
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Zeiger': muss ein Zeiger auf 'Klasse' sein  
  
 Sie haben in [\_\_hook](../../cpp/hook.md) oder [\_\_unhook](../../cpp/unhook.md) einen Zeiger angegeben, der auf keine gültige Klasse zeigte.  Um diesen Fehler zu beheben, sollten Sie sicherstellen, dass in den Aufrufen `__hook` und `__unhook` Zeiger auf gültige Klassen angegeben werden.
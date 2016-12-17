---
title: "Compilerfehler C3715"
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
  - "C3715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3715"
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Zeiger': muss ein Zeiger auf 'Klasse' sein  
  
 Sie haben in [\_\_hook](../../cpp/hook.md) oder [\_\_unhook](../../cpp/unhook.md) einen Zeiger angegeben, der auf keine gültige Klasse zeigte.  Um diesen Fehler zu beheben, sollten Sie sicherstellen, dass in den Aufrufen `__hook` und `__unhook` Zeiger auf gültige Klassen angegeben werden.
---
title: "Compilerfehler C2030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2030"
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ein Destruktor mit "protected private"\-Zugriffsmöglichkeiten kann kein Member einer Klasse sein, die als "sealed" deklariert wurde  
  
 Eine Windows\-Runtime\-Klasse, die als `sealed` deklariert wird, kann nicht über einen geschützten privaten Destruktor verfügen.  Nur öffentliche virtuelle und private nicht virtuelle Destruktoren sind für versiegelte Typen zulässig.  Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](../Topic/Ref%20classes%20and%20structs%20\(C++-CX\).md).  
  
 Um diesen Fehler zu beheben, ändern Sie den Zugriff auf den Destruktor.
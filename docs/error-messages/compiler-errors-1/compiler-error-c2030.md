---
title: "Compilerfehler C2030"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2030"
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ein Destruktor mit "protected private"\-Zugriffsmöglichkeiten kann kein Member einer Klasse sein, die als "sealed" deklariert wurde  
  
 Eine Windows\-Runtime\-Klasse, die als `sealed` deklariert wird, kann nicht über einen geschützten privaten Destruktor verfügen.  Nur öffentliche virtuelle und private nicht virtuelle Destruktoren sind für versiegelte Typen zulässig.  Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](../Topic/Ref%20classes%20and%20structs%20\(C++-CX\).md).  
  
 Um diesen Fehler zu beheben, ändern Sie den Zugriff auf den Destruktor.
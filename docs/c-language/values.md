---
title: "Werte"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 24003f89-220f-4f93-be7a-b650c26157d7
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Werte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.1.2.5** Die Darstellungen und die Sätze von Werten der verschiedenen Typen von Gleitkommazahlen  
  
 Der Typ **float** enthält 32 Bit: 1 für das Zeichen, 8 für den Exponenten und 23 für die Mantisse.  Sein Bereich ist \+\/– 3.4E38 mit mindestens 7 Dezimalstellen.  
  
 Der Typ **double** enthält 64 Bit: 1 für das Zeichen, 11 für den Exponenten und 52 für die Mantisse.  Sein Bereich ist \+\/– 1.7E308 mit mindestens 15 Dezimalstellen.  
  
 Der Typ **long double** enthält 80 Bits: 1 für das Zeichen, 15 für den Exponenten und 64 für die Mantisse.  Sein Bereich ist \+\/– 1.2E4932 mit mindestens 19 Dezimalstellen.  Beachten Sie, dass mit dem Microsoft C\-Compiler die Darstellung des Typs **long double** mit Typ **double** identisch ist.  
  
## Siehe auch  
 [Gleitkommaoperationen](../c-language/floating-point-math.md)
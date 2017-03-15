---
title: "Einfache Zuweisung (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zuweisungsoperatoren [C++], Einfach"
  - "Datentypkonvertierung [C++], Einfache Zuweisung"
  - "Gleichheitszeichen"
  - "Operatoren [C], Einfache Zuweisung"
  - "Einfacher Zuweisungsoperator"
  - "Typkonvertierung [C++], Einfache Zuweisung"
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Einfache Zuweisung (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der einfache Zuweisungsoperator weist seinen rechten Operanden dem linken Operanden zu.  Der Wert des rechten Operanden wird in den Typ des Zuweisungsausdrucks konvertiert und ersetzt den Wert, der im Objekt gespeichert wird, das durch den linken Operanden festgelegt ist.  Es gelten die Konvertierungsregeln für die Zuweisung \(siehe [Zuweisungskonvertierungen](../c-language/assignment-conversions.md)\).  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 In diesem Beispiel wird der Wert von `y` in den Typ **double** konvertiert und `x` zugewiesen.  
  
## Siehe auch  
 [C\-Zuweisungsoperatoren](../c-language/c-assignment-operators.md)
---
title: "Compilerwarnung (Stufe 1) C4807 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4807"
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4807
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Operation": Unsichere Kombination von Typ "Typ" und signiertem Bitfeld des Typs "Typ"  
  
 Diese Warnung wird erzeugt, wenn ein vorzeichenbehaftetes Bitfeld der Länge 1 mit einer `bool`\-Variablen verglichen wird. Da ein vorzeichenbehaftetes Bitfeld der Länge 1 nur die Werte \-1 oder 0 enthalten kann, ist der Vergleich mit einem `bool`\-Wert nicht unproblematisch. Keine Warnungen werden dagegen erzeugt, wenn `bool`\-Werte mit vorzeichenlosen Bitfeldern der Länge 1 verglichen werden, da diese mit `bool` identisch sind und nur 0 oder 1 enthalten können.  
  
## Beispiel  
 Im folgenden Beispiel wird C4807 generiert:  
  
```  
// C4807.cpp // compile with: /W1 typedef struct bitfield { signed mybit : 1; } mybitfield; int main() { mybitfield bf; bool b = true; // try.. // int b = true; bf.mybit = -1; if (b == bf.mybit) {   // C4807 b = false; } }  
```
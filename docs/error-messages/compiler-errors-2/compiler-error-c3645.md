---
title: "Compilerfehler C3645 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3645"
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3645
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': \_\_clrcall kann nicht für Funktionen verwendet werden, die zu systemeigenen Code kompiliert wurden  
  
 Durch das Vorhandensein einiger Schlüsselwörter in einer Funktion wird die Funktion zu systemeigen Code kompiliert.  
  
## Beispiel  
 Im folgenden Beispiel wird C3645 generiert.  
  
```  
// C3645.cpp  
// compile with: /clr /c  
#pragma unmanaged   
int __clrcall dog() {}   // C3645  
```
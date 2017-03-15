---
title: "Compilerwarnung (Stufe 1) C4229 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4229"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4229"
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4229
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Anachronismus verwendet: Modifizierer der Daten werden ignoriert  
  
 Die Verwendung eines Microsoft\-Modifizierers, z. B. `__cdecl`, für eine Datendeklaration ist nicht mehr üblich.  
  
## Beispiel  
  
```  
// C4229.cpp  
// compile with: /W1 /LD  
int __cdecl counter;   // C4229 cdecl ignored  
```
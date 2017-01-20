---
title: "Compilerwarnung (Stufe 1) C4237"
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
  - "C4237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4237"
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schlüsselwort 'Schlüsselwort' wird noch nicht unterstützt, ist jedoch für die zukünftige Verwendung reserviert  
  
 Ein Schlüsselwort in der C\+\+\-Spezifikation ist nicht im Visual C\+\+\-Compiler implementiert, das Schlüsselwort ist jedoch nicht als benutzerdefiniertes Symbol verfügbar.  
  
 Im folgenden Beispiel wird C4237 generiert:  
  
```  
// C4237.cpp  
// compile with: /W1 /c  
int export;   // C4237  
```
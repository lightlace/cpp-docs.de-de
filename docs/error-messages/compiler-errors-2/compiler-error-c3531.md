---
title: "Compilerfehler C3531"
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
  - "C3531"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3531"
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3531
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Symbol": ein Symbol, dessen Typ "Auto" enthält, muss einen Initialisierer haben  
  
 Die angegebene Variable verfügt nicht über einen Initialisiererausdruck.  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie einen Initialisiererausdruck an, wenn Sie die Variable deklarieren, z. B. eine einfache Zuweisung mit Gleichheitszeichensyntax.  
  
## Beispiel  
 Das folgende Beispiel erzeugt C3531, da die Variablen `x1`, `y1, y2, y3` und `z2` nicht initialisiert werden.  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## Siehe auch  
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)
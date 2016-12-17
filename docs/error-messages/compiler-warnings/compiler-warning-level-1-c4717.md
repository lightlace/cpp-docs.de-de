---
title: "Compilerwarnung (Stufe 1) C4717"
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
  - "C4717"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4717"
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4717
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Rekursiv für alle Steuerelementpfade. Die Funktion verursacht einen Stapelüberlauf zur Laufzeit.  
  
 In jedem durch eine Funktion verlaufenden Pfad ist ein Aufruf dieser Funktion enthalten.  Da die Ausführung der Funktion nicht beendet werden kann, ohne dass sie sich selbst zuvor rekursiv aufruft, wird die Funktion niemals beendet.  
  
 Im folgenden Beispiel wird C4717 generiert:  
  
```  
// C4717.cpp  
// compile with: /W1 /c  
// C4717 expected  
int func(int x) {  
   if (x > 1)  
      return func(x - 1); // recursive call  
   else {  
      int y = func(0) + 1; // recursive call  
      return y;  
   }  
}  
  
int main(){  
   func(1);  
}  
```
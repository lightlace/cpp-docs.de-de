---
title: "Compilerwarnung (Stufe 1) C4945"
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
  - "C4945"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4945"
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4945
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Symbol": Das Symbol kann nicht aus "Assembly2" importiert werden: "Symbol" wurde bereits aus einer anderen Assembly "Assembly1" importiert  
  
 Ein Symbol wurde aus einer referenzierten Assembly importiert, es wurde jedoch bereits aus einer anderen referenzierten Assembly importiert.  Entweder sollte auf keine der Assemblys verwiesen oder der Symbolname in einer der Assemblys geändert werden.  
  
 In den folgenden Beispielen wird C4945 generiert:  
  
```  
// C4945a.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 und anschließend  
  
```  
// C4945b.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 und anschließend  
  
```  
// C4945c.cpp  
// compile with: /clr /LD /W1  
#using "C4945a.dll"  
#using "C4945b.dll"   // C4945  
```
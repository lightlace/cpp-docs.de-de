---
title: "Compilerfehler C3286"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3286"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3286"
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3286
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Spezifizierer": Eine Iterationsvariable darf keine Speicherklassenspezifizierer aufweisen.  
  
 Weitere Informationen hierzu finden Sie unter [\(NOTINBUILD\)Speicherklassenspezifizierer](assetId:///10b3d22d-cb40-450b-994b-08cf9a211b6c).  
  
 Weitere Informationen finden Sie unter [for each, in](../../dotnet/for-each-in.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3286 generiert:  
  
```  
// C3286.cpp // compile with: /clr int main() { array<int> ^p = { 1, 2, 3 }; for each (static int i in p) {}   // C3286 for each (int j in p) {}   // OK }  
```
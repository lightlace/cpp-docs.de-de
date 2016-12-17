---
title: "Linkertoolfehler LNK1313"
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
  - "LNK1313"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1313"
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1313
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

IJW\/Native\-Modul gefunden; kann mit reinen Modulen nicht verknüpft werden  
  
 Die aktuelle Version von Visual C\+\+ unterstützt das Verknüpfen von systemeigenen oder gemischten verwalteten\/systemeigenen .obj\-Dateien mit .objDateien, die mit **\/clr:pure** kompiliert wurden.  
  
## Beispiel  
  
```  
// LNK1313.cpp  
// compile with: /c /clr:pure  
// a pure module  
int main() {}  
```  
  
## Beispiel  
  
```  
// LNK1313_b.cpp  
// compile with: /c /clr  
// an IJW module  
void test(){}  
```  
  
## Beispiel  
 Im folgende Beispiel wird LNK1313 generiert.  
  
```  
// LNK1313_c.cpp  
// compile with: /link LNK1313.obj LNK1313_b.obj  
// LNK1313 warning expected  
```
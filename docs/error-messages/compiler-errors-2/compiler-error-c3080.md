---
title: "Compilerfehler C3080"
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
  - "C3080"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3080"
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3080
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Finalizer\_Funktion': Ein Finalizer kann keinen Speicherklassenspezifizierer aufweisen.  
  
 Weitere Informationen finden Sie unter [Destruktoren und Finalizer in Visual C\+\+](../../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3080 generiert:  
  
```  
// C3080.cpp // compile with: /clr /c ref struct rs { protected: static !rs(){}   // C3080 !rs(){}   // OK };  
```
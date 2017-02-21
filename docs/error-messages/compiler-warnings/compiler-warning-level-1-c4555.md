---
title: "Compilerwarnung (Stufe 1) C4555 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4555"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4555"
ms.assetid: 50b286c1-f7bf-4292-b1fa-baaac9538611
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4555
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Ausdruck hat keine Auswirkungen; Ausdruck mit Nebeneffekten erwartet  
  
 Diese Warnung informiert Sie darüber, dass ein Ausdruck keine Auswirkungen hat.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Beispiel:  
  
```  
// C4555.cpp  
// compile with: /W1  
#pragma warning(default:4555)  
  
void func1()  
{  
   1;   // C4555  
}  
  
void func2()  
{  
   int x;  
   x;   // C4555  
}  
  
int main()  
{  
}  
```
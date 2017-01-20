---
title: "Compilerwarnung (Stufe 2) C4756"
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
  - "C4756"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4756"
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 2) C4756
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überlauf bei arithmetischer Auswertung einer Konstanten  
  
 Bei der arithmetischen Auswertung einer Konstanten während der Kompilierung erzeugte der Compiler eine Ausnahme.  
  
 Im folgenden Beispiel wird C4756 generiert:  
  
```  
// C4756.cpp  
// compile with: /W2 /Od  
int main()  
{  
   float f = 1e100+1e100;   // C4756  
}  
```
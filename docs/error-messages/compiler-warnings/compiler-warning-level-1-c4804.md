---
title: "Compilerwarnung (Stufe 1) C4804"
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
  - "C4804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4804"
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operation': unsichere Verwendung des Typs 'bool' in einer Operation  
  
 Diese Warnung ist für Situationen gedacht, in denen eine Variable oder ein Wert vom Typ `bool` nicht wie erwartet verwendet wurde.  C4804 wird z. B. erzeugt, wenn Sie Operatoren, wie den negativen unären Operator \(**\-**\) oder den Komplementierungsoperator \(`~`\), verwenden.  Der Ausdruck wird vom Compiler ausgewertet.  
  
## Beispiel  
 Im folgenden Beispiel wird C4804 generiert:  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```
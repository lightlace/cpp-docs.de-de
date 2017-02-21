---
title: "Compilerwarnung (Stufe 1) C4572 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4572"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4572"
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4572
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das \[ParamArray\]\-Attribut von \/clr ist veraltet, verwenden Sie stattdessen "..."  
  
 Ein veraltetes Format für die Angabe einer Variablenargumentlisten wurde verwendet.  Verwenden Sie beim Kompilieren für CLR anstelle von <xref:System.ParamArrayAttribute> eine Syntax mit Auslassungszeichen.  Weitere Informationen finden Sie unter [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4572 generiert.  
  
```  
// C4572.cpp  
// compile with: /clr /W1  
void Func([System::ParamArray] array<int> ^);   // C4572  
void Func2(... array<int> ^){}   // OK  
  
int main() {  
   Func2(1, 2, 3);  
}  
```
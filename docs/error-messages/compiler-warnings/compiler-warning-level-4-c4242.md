---
title: "Compilerwarnung (Stufe 4) C4242 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4242"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4242"
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 4) C4242
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Umwandlung von 'Typ1' in 'Typ2', Datenverlust ist möglich  
  
 Die Typen sind unterschiedlich.  Die Typkonvertierung kann Datenverluste verursachen.  Der Compiler führt die Typkonvertierung durch.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Weitere Informationen über C4242, finden Sie unter [Häufige Compilerfehler](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 Im folgenden Beispiel wird C4242 generiert:  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```
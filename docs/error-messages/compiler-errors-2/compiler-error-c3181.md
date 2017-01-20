---
title: "Compilerfehler C3181"
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
  - "C3181"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3181"
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3181
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Ungültiger Operand für Operator  
  
 Ein ungültiger Parameter wurde an den Operator [\_\_typeof](../../misc/typeof.md) oder [typeid](../../windows/typeid-cpp-component-extensions.md) übergeben.  Der Parameter muss ein verwalteter Typ sein.  
  
 Beachten Sie, dass der Compiler Aliasnamen für systemeigene Typen verwendet, die den Typen in der Common Language Runtime zugeordnet sind.  
  
 Im folgenden Beispiel wird C3181 generiert:  
  
```  
// C3181a.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181  
   Type ^pType2 = int::typeid;   // OK  
}  
```  
  
 Im folgenden Beispiel wird C3181 generiert:  
  
```  
// C3181b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
int main() {  
   Type *pType1 = __typeof(int __gc*);   // C3181  
   Type *pType2 = __typeof(int*);   // OK  
}  
```
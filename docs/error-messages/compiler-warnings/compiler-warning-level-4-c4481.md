---
title: "Compilerwarnung (Stufe 4) C4481 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4481"
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerwarnung (Stufe 4) C4481
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: Spezifizierer 'Schlüsselwort' überschreiben  
  
 Es wurde ein Schlüsselwort verwendet, das nicht dem C\+\+\-Standard entspricht, beispielsweise einer der Überschreibungsspezifizierer, die auch unter \/clr funktionieren.  Weitere Informationen finden Sie unter  
  
-   [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md)  
  
## Beispiel  
 Im folgenden Beispiel wird C4481 generiert.  
  
```  
// C4481.cpp  
// compile with: /W4 /c  
class B {  
   virtual void f(unsigned);  
};  
  
class C : B {  
   void f(unsigned) override;   // C4481  
   void f2(unsigned);  
};  
```
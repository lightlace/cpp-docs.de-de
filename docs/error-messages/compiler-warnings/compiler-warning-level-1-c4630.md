---
title: "Compilerwarnung (Stufe 1) C4630"
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
  - "C4630"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4630"
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4630
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol' : Speicherklassenspezifizierer 'extern' darf nicht für Elementdefinition verwendet werden  
  
 Ein Datenmember oder eine Memberfunktion wurde **extern** definiert.  Member können im Gegensatz zu vollständigen Objekten nicht extern sein.  Der Compiler ignoriert das `extern`\-Schlüsselwort.  Im folgenden Beispiel wird C4630 generiert:  
  
```  
// C4630.cpp  
// compile with: /W1 /LD  
class A {  
   void func();  
};  
  
extern void A::func() {   // C4630, remove 'extern' to resolve  
}  
```
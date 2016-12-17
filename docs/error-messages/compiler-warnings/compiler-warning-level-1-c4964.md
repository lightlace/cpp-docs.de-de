---
title: "Compilerwarnung (Stufe 1) C4964"
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
  - "C4964"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4964"
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4964
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es wurden keine Optimierungsoptionen angegeben. Es werden keine Profilinformationen erfasst.  
  
 Es wurde [\/GL](../../build/reference/gl-whole-program-optimization.md) und [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) angegeben, ohne dass jedoch Optimierungen angefordert wurden. Aus diesem Grund werden keine PGC\-Dateien erzeugt, und infolgedessen sind keine profilgesteuerten Optimierungen möglich.  
  
 Wenn beim Ausführen der Anwendung PGC\-Dateien generiert werden sollen, geben Sie eine der [\/O](../../build/reference/o-options-optimize-code.md)\-Compileroptionen an.  
  
 Im folgenden Beispiel wird C4964 generiert:  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```
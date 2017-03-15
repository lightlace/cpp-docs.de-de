---
title: "Compilerwarnung (Stufe 4) C4937 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4937"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4937"
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4937
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Text1' und 'Text2' sind als Argumente für 'Direktive' nicht differenzierbar.  
  
 Aufgrund der Art und Weise, wie der Compiler Argumente zu Direktiven verarbeitet, können Namen, die für den Compiler eine Bedeutung haben, z. B. Schlüsselwörter mit mehreren Textdarstellungen \(Varianten mit einfachem und doppeltem Unterstrich\), nicht unterschieden werden.  
  
 Beispiele solcher Zeichenfolgen sind „\_\_cdecl“ und „\_\_forceinline“.  Beachten Sie, dass unter „\/Za“ nur die Varianten mit doppeltem Unterstrich aktiviert sind.  
  
 Im folgenden Beispiel wird C4937 generiert:  
  
```  
// C4937.cpp // compile with: /openmp /W4 #include "omp.h" int main() { #pragma omp critical ( __leave )   // C4937 ; // OK #pragma omp critical ( leave ) ; }  
```
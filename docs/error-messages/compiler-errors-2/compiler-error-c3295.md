---
title: "Compilerfehler C3295"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3295"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3295"
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3295
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\#pragma Pragma" kann nur im globalen Gültigkeitsbereich oder im Namespace\-Gültigkeitsbereich verwendet werden.  
  
 Einige Pragmas können nicht in einer Funktion verwendet werden.  Weitere Informationen finden Sie unter [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3295 generiert:  
  
```  
// C3295.cpp int main() { #pragma managed   // C3295 }  
```
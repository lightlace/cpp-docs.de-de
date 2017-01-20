---
title: "Compilerwarnung (Stufe 1) C4080"
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
  - "C4080"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4080"
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4080
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bezeichner für Segmentnamen erwartet; "Symbol" gefunden  
  
 Der Name des Segments in [\#pragma alloc\_text](../../preprocessor/alloc-text.md) muss eine Zeichenfolge oder ein Bezeichner sein. Der Compiler ignoriert das Pragma, wenn kein gültiger Bezeichner gefunden wurde.  
  
 Im folgenden Beispiel wird C4080 generiert:  
  
```  
// C4080.cpp // compile with: /W1 extern "C" void func(void); #pragma alloc_text()   // C4080 // try this line to resolve the warning // #pragma alloc_text("mysection", func) int main() { } void func(void) { }  
```
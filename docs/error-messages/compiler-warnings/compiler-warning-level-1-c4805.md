---
title: "Compilerwarnung (Stufe 1) C4805 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4805"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4805"
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4805
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Operation": unsichere Kombination von Typ "Typ" mit Typ "Typ" in einer Operation  
  
 Diese Warnung wird für Vergleichsvorgänge zwischen [bool](../../cpp/bool-cpp.md) und [int](../../c-language/integer-types.md) generiert. Im folgenden Beispiel wird C4805 generiert:  
  
```  
// C4805.cpp // compile with: /W1 int main() { int i = 1; bool b = true; if (i == b) {   // C4805, comparing bool and int variables } }  
```
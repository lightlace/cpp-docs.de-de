---
title: "Compilerfehler C3896 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3896"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3896"
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3896
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member' : Fehlerhafter Initialisierer: Dieser literal\-Datenmember kann nur mit 'nullptr' initialisiert werden.  
  
 Ein [literal](../../windows/literal-cpp-component-extensions.md)\-Datenmember wurde falsch initialisiert.  Weitere Informationen finden Sie unter [nullptr](../../windows/nullptr-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3896 generiert:  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```
---
title: "Compiler Error C3387 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3387"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3387"
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compiler Error C3387
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„member“: \_\_\_\_declspec\(dllexport\)\/\_\_declspec\(dllimport\) kann nicht auf einen Member eines verwalteten oder WinRT\-Typs angewendet werden.  
  
 Die `__declspec`\-Modifizierer `dllimport` und [dllexport](../../cpp/dllexport-dllimport.md) sind für Member eines verwalteten oder WinRT\-Typs nicht zulässig .  
  
 Im folgenden Beispiel wird C3387 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3387a.cpp  
// compile with: /clr /c  
ref class X2 {  
   void __declspec(dllexport) mf() {   // C3387  
   // try the following line instead  
   // void mf() {  
   }  
};  
```
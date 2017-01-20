---
title: "Compilerfehler C2506"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2506"
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2506
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member': '\_\_declspec\(modifier\)' kann nicht auf dieses Symbol angewendet werden  
  
 Sie können statische Member einer verwalteten Klasse nicht prozess\- oder anwendungsdomänenspezifisch deklarieren.  
  
 Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2506 generiert.  
  
```  
// C2506.cpp  
// compile with: /clr /c  
ref struct R {  
   __declspec(process) static int n;   // C2506  
   int o;   // OK  
};  
```
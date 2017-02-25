---
title: "Compilerfehler C2506 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2506"
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
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
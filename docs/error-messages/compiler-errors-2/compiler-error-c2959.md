---
title: "Compilerfehler C2959 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2959"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2959"
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2959
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine generische Klasse oder Funktion ist möglicherweise kein Member einer Vorlage  
  
 Weitere Informationen finden Sie unter [Windows Runtime and Managed Templates](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md) und [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2959 generiert.  
  
```  
// C2959.cpp  
// compile with: /clr /c  
template <class T> ref struct S {  
   generic <class U> ref struct GR1;   // C2959  
};  
```
---
title: "Compilerfehler C3869"
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
  - "C3869"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3869"
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3869
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In der gcnew\-Einschränkung fehlt die leere Parameterliste '\(\)'  
  
 Die spezielle `gcnew`\-Einschränkung wurde ohne die leere Parameterliste angegeben.  Weitere Informationen finden Sie unter [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3869 generiert.  
  
```  
// C3869.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : gcnew   // C3869  
// try the following line instead  
// where T : gcnew()  
ref class List {};  
```
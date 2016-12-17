---
title: "Compilerfehler C3371"
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
  - "C3371"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3371"
ms.assetid: f7ecf1aa-ed0a-4f73-81e5-62cf98f88ea1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3371
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"idl\_module": Hier ist nur die "name"\-Eigenschaft zulässig  
  
 Die direkte Verwendung von [idl\_module](../../windows/idl-module.md) in einer Funktionsdeklaration kann keine anderen Parameter als „name“ aufweisen.  
  
 Im folgenden Beispiel wird C3371 generiert:  
  
```  
// C3371.cpp [idl_module(name="Name", dllname="Some.dll")]; [idl_module(name="Name", helpstring="Some help")]   // C3371 int f1(); // try // [idl_module(name="Name")] // int f1(); int main() { }  
```
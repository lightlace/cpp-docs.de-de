---
title: "Compilerfehler C3638"
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
  - "C3638"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3638"
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3638
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Die Standardoperatoren für die Boxing\- und Unboxing\-Konvertierung können nicht neu definiert werden  
  
 Der Compiler definiert einen Konvertierungsoperator, damit jede verwaltete Klasse implizites Boxing unterstützt.  Dieser Operator kann nicht neu definiert werden.  
  
 Weitere Informationen finden Sie unter [Implizites Boxing](../../windows/boxing-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3638 generiert:  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```
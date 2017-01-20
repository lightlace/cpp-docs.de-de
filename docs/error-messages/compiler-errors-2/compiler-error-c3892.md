---
title: "Compilerfehler C3892"
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
  - "C3892"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3892"
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3892
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': Zuweisung zu einer const\-Variablen nicht möglich  
  
 Eine const\-Variable kann nicht geändert werden, nachdem sie deklariert und initialisiert wurde.  
  
 Im folgenden Beispiel wird C3892 generiert:  
  
```  
// C3892.cpp  
// compile with: /clr  
ref struct Y1 {  
   static const int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3892  
}  
```
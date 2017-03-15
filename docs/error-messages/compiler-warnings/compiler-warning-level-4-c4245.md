---
title: "Compilerwarnung (Stufe 4) C4245 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4245"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4245"
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4245
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konvertierung': Konvertierung von 'Typ1' in 'Typ2', signed\/unsigned\-Konflikt  
  
 Sie haben versucht, eine **Konstante** mit Vorzeichen, die einen negativen Wert hat, in `unsigned` zu konvertieren.  
  
 Im folgenden Beispiel wird C4245 generiert:  
  
```  
// C4245.cpp  
// compile with: /W4 /c  
const int i = -1;  
unsigned int j = i; // C4245  
  
const int k = 1;  
unsigned int l = k; // okay  
  
int m = -1;  
unsigned int n = m; // okay  
  
void Test(size_t i) {}  
  
int main() {  
   Test( -19 );   // C4245  
}  
```
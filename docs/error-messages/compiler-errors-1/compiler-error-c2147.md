---
title: "Compilerfehler C2147 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2147"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2147"
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2147
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: 'Bezeichner' ist ein neues Schlüsselwort  
  
 Ein Bezeichner wurde verwendet, der jetzt ein reserviertes Schlüsselwort in der Sprache ist.  
  
 Im folgenden Beispiel wird C2147 generiert:  
  
```  
// C2147.cpp  
// compile with: /clr  
int main() {  
   int gcnew = 0;   // C2147  
   int i = 0;   // OK  
}  
```
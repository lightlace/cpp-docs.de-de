---
title: "Compilerfehler C2745 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2745"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2745"
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2745
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Token': Dieses Token kann nicht in einen Bezeichner umgewandelt werden.  
  
 Bezeichner dürfen nur zulässige Zeichen enthalten.  
  
 Im folgenden Beispiel wird C2745 generiert:  
  
```  
// C2745.cpp  
// compile with: /clr  
int main() {  
   int __identifier([));   // C2745  
}  
```
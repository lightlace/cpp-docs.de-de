---
title: "Compilerfehler C2745"
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
  - "C2745"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2745"
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
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
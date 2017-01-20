---
title: "Compilerfehler C2118"
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
  - "C2118"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2118"
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2118
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Negativer Index  
  
 Der Wert, der die Größe des Arrays definiert, ist größer als die maximal zulässige Arraygröße oder kleiner als 0 \(null\).  
  
 Im folgenden Beispiel wird C2118 generiert:  
  
```  
// C2118.cpp  
int main() {  
   int array1[-1];   // C2118  
   int array2[3];   // OK  
}  
```
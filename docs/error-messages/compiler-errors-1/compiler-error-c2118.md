---
title: "Compilerfehler C2118 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2118"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2118"
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
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
---
title: "Compilerwarnung (Stufe 2) C4156 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4156"
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 2) C4156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Löschen eines Arrayausdrucks ohne Verwendung der Arrayform von "delete". Arrayform wird automatisch verwendet.  
  
 Ein Array kann nicht mit der Nicht\-Arrayform von **delete** gelöscht werden.  **delete** wurde vom Compiler in die Arrayform übersetzt.  
  
 Diese Warnung tritt nur bei Verwendung der Microsoft\-Erweiterungen \(**\/Ze**\) auf.  
  
## Beispiel  
  
```  
// C4156.cpp  
// compile with: /W2  
int main()  
{  
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];  
   delete array; // C4156, changed by compiler to "delete [] array;"  
}  
```
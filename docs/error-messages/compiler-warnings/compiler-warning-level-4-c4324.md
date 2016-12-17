---
title: "Compilerwarnung (Stufe 4) C4324"
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
  - "C4324"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4324"
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4324
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'struct\_name': Struktur wurde aufgrund von \_\_declspec\(align\(\)\) aufgefüllt  
  
 Am Ende der Struktur wurden Füllzeichen hinzugefügt, da Sie einen [\_\_declspec\(align\)](../../cpp/align-cpp.md)\-Wert angegeben haben.  
  
 Der folgende Code generiert z. B. C4324:  
  
```  
// C4324.cpp  
// compile with: /W4  
struct __declspec(align(32)) A  
{  
   char a;  
};   // C4324  
  
int main()  
{  
}  
```
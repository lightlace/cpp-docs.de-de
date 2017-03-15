---
title: "Compilerfehler C2505 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2505"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2505"
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2505
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol': \_\_declspec\(Modifizierer\) kann nur auf Deklarationen oder Definitionen globaler Objekte oder statischer Datenmember angewendet werden  
  
 Ein `__declspec`\-Modifizierer, der nur für die globale Verwendung bestimmt war, wurde in einer Funktion verwendet.  
  
 Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).  
  
 Im folgenden Beispiel wird C2505 generiert:  
  
```  
// C2505.cpp  
// compile with: /clr  
  
// OK  
__declspec(process) int ii;  
__declspec(appdomain) int jj;  
  
int main() {  
   __declspec(process) int i;   // C2505  
   __declspec(appdomain) int j;   // C2505  
}  
```
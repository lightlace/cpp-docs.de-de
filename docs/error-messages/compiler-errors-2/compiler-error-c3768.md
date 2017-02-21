---
title: "Compilerfehler C3768 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3768"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3768"
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3768
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Adresse einer virtuellen vararg\-Funktion kann in reinem verwalteten Code nicht verwendet werden  
  
 Wenn Sie mit `/clr:pure` kompilieren, können Sie die Adresse einer virtuellen `vararg`\-Funktion nicht verwenden.  
  
 Im folgenden Beispiel wird C3768 generiert:  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```
---
title: "Compilerfehler C3727 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3727"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3727"
ms.assetid: 17b9fe7b-ee9e-483f-9c27-1f709255a9e0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3727
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Ereignis' : Ein verwaltetes Ereignis muss eine Memberfunktion oder ein Datenmember sein, das ein Zeiger zu einem Delegat ist  
  
 .NET\-Ereignisse müssen Zeiger auf einen Delegattyp sein.  
  
 Im folgenden Beispiel wird C3727 generiert:  
  
```  
// C3727.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class PseudoDelegate  
{  
};  
  
// use the following declaration to resolve the error.  
// __delegate void PseudoDelegate(int);  
  
__gc class MyAttr  
{  
   __event PseudoDelegate* MyE;  
};   // C3727  
  
int main()  
{  
}  
```
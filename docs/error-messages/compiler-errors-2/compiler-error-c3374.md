---
title: "Compilerfehler C3374 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3374"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3374"
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3374
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Übernehmen der Adresse der 'Funktion' nicht möglich, außer bei Erstellung der Delegatinstanz  
  
 Die Adresse einer Funktion wurde in einem anderen Kontext als bei der Erstellung einer Delegatinstanz übernommen.  
  
 Im folgenden Beispiel wird C3374 generiert:  
  
```  
// C3374.cpp  
// compile with: /clr  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      System::Console::WriteLine("in func1 {0}", i);  
   }  
};  
  
int main() {  
   &A::func1;   // C3374  
  
   // OK  
   A ^ a = gcnew A;  
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);  
}  
```  
  
## Siehe auch  
 [Gewusst wie: Definieren und Verwenden von Delegaten](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)
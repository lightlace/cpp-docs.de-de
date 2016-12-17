---
title: "Compilerfehler C2252"
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
  - "C2252"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2252"
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2252
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vorlage kann in aktuellem Bereich nicht explizit instanziiert werden  
  
 Der Compiler hat ein Problem mit einer expliziten Instanziierung einer Vorlage festgestellt.  Sie können beispielsweise keine Vorlage explizit in einer Funktion instanziieren.  
  
 Im folgenden Beispiel wird C2252 generiert:  
  
```  
// C2252.cpp  
class A {  
public:  
   template <class T>  
   int getit(int i , T * it ) {  
      return i;  
   }  
   template int A::getit<double>(int i, double * it);   // C2252  
   // try the following line instead  
   // template <> int A::getit<double>(int i, double * it);  
  
};  
  
int main() {  
   // cannot explicitly instantiate in function  
   template int A::getit<long>(int i, long * it);   // C2252  
}  
```
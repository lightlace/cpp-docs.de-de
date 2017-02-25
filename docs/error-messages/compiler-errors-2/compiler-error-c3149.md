---
title: "Compilerfehler C3149 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3149"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3149"
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C3149
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Dieser Typ kann ohne 'char' der obersten Ebene hier nicht verwendet werden  
  
 Eine Deklaration wurde nicht ordnungsgemäß angegeben.  
  
 Möglicherweise wurde ein CLR\-Typ im globalen Gültigkeitsbereich definiert und versucht, eine Variable des Typs als Teil der Definition zu erstellen.  Da globale Variablen von CLR\-Typen nicht zulässig sind, generiert der Compiler C3149.  
  
 Um diesen Fehler zu beheben, deklarieren Sie Variablen von CLR\-Typen innerhalb einer Funktion oder Typdefinition.  
  
 Im folgenden Beispiel wird C3149 generiert:  
  
```  
// C3149.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   // declare an array of value types   
   array< Int32 ^> IntArray;   // C3149  
   array< Int32>^ IntArray2;   // OK  
}  
```  
  
 Im folgenden Beispiel wird C3149 generiert:  
  
```  
// C3149b.cpp  
// compile with: /clr /c  
delegate int MyDelegate(const int, int);  
void Test1(MyDelegate m) {}   // C3149  
void Test2(MyDelegate ^ m) {}   // OK  
```  
  
 **Managed Extensions for C\+\+**  
  
 Ein verwaltetes Objekt wurde nicht ordnungsgemäß verwendet.  
  
 Im folgenden Beispiel wird C3149 generiert:  
  
```  
// C3149c.cpp  
// compile with: /clr:oldSyntax  
__gc class A {};  
  
int main() {  
   A a = new A;   // C3149  
   A *a = new A;   // OK  
}  
```
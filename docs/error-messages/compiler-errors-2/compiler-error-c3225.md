---
title: "Compilerfehler C3225"
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
  - "C3225"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3225"
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3225
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das generische Typargument für 'Argument' kann nicht 'Typ' sein, es muss ein Werttyp oder ein Handletyp sein  
  
 Das generische Typargument war nicht vom richtigen Typ.  
  
 Weitere Informationen finden Sie unter [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Beispiel  
 Sie können keinen generischen Typ mit einem systemeigenen Typ instanziieren.  Im folgenden Beispiel wird C3225 generiert.  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird eine Komponente mithilfe von C\# erstellt.  Die Einschränkung gibt an, dass der generische Typ nur mit einem Werttyp instanziiert werden kann.  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## Beispiel  
 In diesem Beispiel wird die mit C\# erstellte Komponente verwendet. Die Einschränkung, dass MyList nur mit einem Werttyp außer <xref:System.Nullable> verwendet werden kann, wird verletzt.  Im folgenden Beispiel wird C3225 generiert.  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```
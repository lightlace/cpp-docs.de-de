---
title: "Compilerfehler C2885"
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
  - "C2885"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2885"
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2885
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse::Bezeichner': Keine gültige using\-Deklaration im Gültigkeitsbereich der Nichtklasse.  
  
 Eine [using](../../cpp/using-declaration.md)\-Deklaration wurde nicht ordnungsgemäß verwendet.  
  
## Beispiel  
 Dieser Fehler kann infolge einer Verbesserung der Compilerkonformität für Visual C\+\+ 2005 generiert werden: Es ist nicht mehr zulässig, eine `using`\-Deklaration zu verwenden, die sich auf einen geschachtelten Typ bezieht. Sie müssen jeden Verweis auf den verschachtelten Typ explizit qualifizieren, den Typ in einem Namespace ablegen oder eine Typdefinition erstellen.  
  
 Im folgenden Beispiel wird C2885 generiert.  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## Beispiel  
 Wenn Sie das `using`\-Schlüsselwort mit einem Klassenmember verwenden, ist es in C\+\+ erforderlich, dass dieser Member innerhalb einer anderen \(abgeleiteten\) Klasse definiert wird.  
  
 Im folgenden Beispiel wird C2885 generiert.  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```
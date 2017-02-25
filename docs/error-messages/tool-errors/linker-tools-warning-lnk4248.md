---
title: "Linkertoolwarnung LNK4248 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4248"
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Linkertoolwarnung LNK4248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht aufgelöstes typeref\-Token \(Token\) für 'Typ'. Bild kann möglicherweise nicht ausgeführt werden.  
  
 Für einen Typ ist in den MSIL\-Metadaten keine Definition vorhanden.  
  
 LNK4248 kann auftreten, wenn für einen Typ lediglich eine Vorwärtsdefinition in einem MSIL\-Modul \(kompiliert mit **\/clr**\) vorhanden ist, auf den Typ im MSIL\-Modul verwiesen wird, und das MSIL\-Modul mit einem systemeigenen Modul verknüpft ist, das eine Definition für den Typ enthält.  
  
 In diesem Fall wird vom Linker die systemeigene Typdefinition in den MSIL\-Metadaten zur Verfügung gestellt, was möglicherweise zum gewünschten Verhalten führt.  
  
 Wenn es sich bei einer Vorwärtsdefinition für einen Typ jedoch um einen CLR\-Typ handelt, ist die vom Linker bereitgestellte systemeigene Typdefinition unter Umständen nicht die richtige.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie im MSIL\-Modul die Typdefinition bereit.  
  
## Beispiel  
 Im folgenden Beispiel wird LNK4248 generiert.  Definieren Sie Struktur A, um das Problem zu beheben.  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## Beispiel  
 Das folgende Beispiel enthält eine Vorwärtsdefinition für einen Typ.  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird LNK4248 generiert.  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```
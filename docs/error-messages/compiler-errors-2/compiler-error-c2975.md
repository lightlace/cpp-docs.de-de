---
title: "Compilerfehler C2975"
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
  - "C2975"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2975"
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2975
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : Ungültiges Vorlagenargument für 'Typ', konstanter Ausdruck zur Kompilierungszeit erwartet  
  
 Das Vorlagenargument stimmt nicht mit der Vorlagendeklaration überein. Innerhalb der spitzen Klammern sollte ein konstanter Ausdruck stehen.  Variablen sind nicht als tatsächlich an die Vorlage übergebene Argumente zulässig.  Überprüfen Sie die Vorlagendefinition, um die richtigen Typen zu finden.  
  
 Im folgenden Beispiel wird C2975 generiert:  
  
```  
// C2975.cpp  
template<int I>  
class X {};  
  
int main() {  
   int i = 4, j = 2;  
   X<i + j> x1;   // C2975  
   X<6> x2;   // OK  
}  
```  
  
 C2975 tritt auch auf, wenn Sie \_\_LINE\_\_ als Konstante zur Kompilierungszeit zusammen mit [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) verwenden.  Eine Lösung wäre, mit [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) statt mit **\/ZI** zu kompilieren.  
  
```  
// C2975b.cpp  
// compile with: /ZI  
// processor: x86  
template<long line>   
void test(void) {}  
  
int main() {  
   test<__LINE__>();   // C2975  
}  
```
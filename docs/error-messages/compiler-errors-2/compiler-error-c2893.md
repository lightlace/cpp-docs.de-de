---
title: "Compilerfehler C2893 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2893"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2893"
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compilerfehler C2893
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Funktionsvorlage 'Vorlagenname' konnte nicht spezialisiert werden  
  
 Der Compiler war nicht in der Lage, eine Funktionsvorlage zu spezialisieren.  Für diesen Fehler kommen mehrere Ursachen in Betracht.  
  
 Im Allgemeinen kann ein C2893\-Fehler behoben werden, indem die Signatur der Funktion überprüft sowie sichergestellt wird, dass alle Typen instanziiert werden können.  
  
## Beispiel  
 C2893 tritt auf, da der zu `f` zugehörige Vorlagenparameter `T` abgeleitet wird, um `std::map<int,int>` zu erhalten, `std::map<int,int>` jedoch nicht über einen Member `data_type` verfügt. \(`T::data_type` kann nicht mit `T = std::map<int,int>` instanziiert werden.\)  Im folgenden Beispiel wird C2893 generiert.  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```
---
title: "property (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "property_cpp"
  - "Property"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], Eigenschaft"
  - "property __declspec-Schlüsselwort"
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# property (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Dieses Attribut kann auf nicht statische "virtuelle Datenmember" in einer Klassen\- oder Strukturdefinition angewendet werden.  Der Compiler behandelt diese "virtuellen Datenmember" als Datenmember, indem er ihre Verweise in Funktionsaufrufe ändert.  
  
## Syntax  
  
```  
  
      __declspec( property( get=get_func_name ) ) declarator  
__declspec( property( put=put_func_name ) ) declarator  
__declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## Hinweise  
 Wenn der Compiler auf der rechten Seite eines Memberauswahloperators \("**.**" oder "**\-\>**"\) einen Datenmember erkennt, der mit diesem Attribut deklariert ist, konvertiert er den Vorgang in eine **get**\- oder **put**\-Funktion, je nachdem, ob der Ausdruck ein L\-Wert oder ein R\-Wert ist.  In den schwierigeren Kontexten \(beispielsweise "`+=`"\) wird eine Neufassung ausgeführt, indem **get** und **put** ausgeführt werden.  
  
 Dieses Attribut kann in der Deklaration eines leeren Arrays in einer Klassen\- oder Strukturdefinition ebenfalls verwendet werden.  Beispiel:  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 Die oben genannte Anweisung gibt an, dass `x[]` mit einem oder mehreren Arrayindizes verwendet werden kann.  In diesem Fall wird `i=p->x[a][b]` in `i=p->GetX(a, b)` umgewandelt und `p->PutX(a, b, i);` in `p->x[a][b] = i`.  
  
 **END Microsoft\-spezifisch**  
  
## Beispiel  
  
```  
// declspec_property.cpp  
struct S {  
   int i;  
   void putprop(int j) {   
      i = j;  
   }  
  
   int getprop() {  
      return i;  
   }  
  
   __declspec(property(get = getprop, put = putprop)) int the_prop;  
};  
  
int main() {  
   S s;  
   s.the_prop = 5;  
   return s.the_prop;  
}  
```  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)
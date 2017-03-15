---
title: "Consuming Generics (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generics [C++], consuming from .NET languages"
ms.assetid: e6330ef5-e907-432e-b527-7a22f5899639
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Consuming Generics (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Generika, das in einer .NET\-Sprache erstellt wird, wird in anderen .NET\-Sprachen verwendet werden.  Anders als Vorlagen bleibt ein generisches in einer kompilierten Assembly weiterhin generisch.  Daher instanziiert möglicherweise von den generischen Typ in einer anderen Assembly und sogar in einer anderen Sprache als die Assembly, in der der generische Typ definiert wurde.  
  
## Hinweise  
 Weitere Informationen finden Sie unter:  
  
-   [Einführung in Generika](../Topic/Introduction%20to%20Generics%20\(C%23%20Programming%20Guide\).md)  
  
-   [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)  
  
## Beispiel  
  
### **Beschreibung**  
 In diesem Beispiel wird eine generische Klasse, die in C\# definiert wird.  
  
### Code  
  
```  
// consuming_generics_from_other_NET_languages.cs  
// compile with: /target:library  
// a C# program  
public class CircularList<ItemType> {  
   class ListNode    {  
      public ItemType m_item;  
      public ListNode next;  
      public ListNode(ItemType item) {  
         m_item = item;  
      }  
   }  
  
   ListNode first, last;  
  
   public CircularList() {}  
  
   public void Add(ItemType item) {  
      ListNode newnode = new ListNode(item);  
      if (first == null) {  
         first = last = newnode;  
         first.next = newnode;  
         last.next = first;  
      }  
      else {  
         newnode.next = first;  
         first = newnode;  
         last.next = first;  
      }   
   }  
  
   public void Remove(ItemType item) {  
      ListNode iter = first;  
      if (first.m_item.Equals( item )) {  
         first =   
         last.next = first.next;  
      }  
      for ( ; iter != last ; iter = iter.next )  
         if (iter.next.m_item.Equals( item )) {  
              if (iter.next == last)  
                  last = iter;  
              iter.next = iter.next.next;  
              return;  
          }  
   }  
  
   public void PrintAll() {  
      ListNode iter = first;  
      do {  
         System.Console.WriteLine( iter.m_item );  
         iter = iter.next;  
      } while (iter != last);  
   }  
}  
```  
  
## Beispiel  
  
### **Beschreibung**  
 In diesem Beispiel wird die Assembly, die in C\# erstellt wird.  
  
### Code  
  
```  
// consuming_generics_from_other_NET_languages_2.cpp  
// compile with: /clr  
#using <consuming_generics_from_other_NET_languages.dll>  
using namespace System;  
class NativeClass {};  
ref class MgdClass {};  
  
int main() {  
   CircularList<int>^ circ1 = gcnew CircularList<int>();  
   CircularList<MgdClass^>^ circ2 = gcnew CircularList<MgdClass^>();  
  
   for (int i = 0 ; i < 100 ; i += 10)  
      circ1->Add(i);  
   circ1->Remove(50);  
   circ1->PrintAll();  
}  
```  
  
### Ausgabe  
  
```  
90  
80  
70  
60  
40  
30  
20  
10  
```  
  
## Siehe auch  
 [Generics](../windows/generics-cpp-component-extensions.md)
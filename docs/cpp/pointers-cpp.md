---
title: Zeiger (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- declarators, pointers
- declarations, pointers
- pointers [C++]
- pointers, declarations
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e81d56cee716a11f918149279f0b0fefadfe4bb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pointers-c"></a>Zeiger (C++)
Zeiger werden mithilfe der folgenden Sequenz deklariert.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator ;  
```  
  
 wobei ein beliebiger gültiger Zeigerdeklarator für `declarator` verwendet werden kann.  Die Syntax für einen einfachen Zeigerdeklarator lautet wie folgt:  
  
```  
* [cv-qualifiers] identifier [= expression]  
```  
  
 1. Die Deklarationsspezifizierer:  
  
-   Ein optionaler Speicherklassenbezeichner. Weitere Informationen finden Sie unter [Spezifizierer](../cpp/specifiers.md).  
  
-   Ein optionales `const`- oder `volatile`-Schlüsselwort, das auf den Typ des Objekts angewendet wird, auf das gezeigt werden soll.  
  
-   Der Typspezifizierer: der Name eines Typs, der den Typ des Objekts dargestellt, auf das gezeigt wird.  
  
 2. Der Deklarator:  
  
-   Ein optionaler Microsoft-spezifischer Modifizierer. Weitere Informationen finden Sie unter [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).  
  
-   Der Operator `*`.  
  
-   Ein optionales `const`- oder `volatile`-Schlüsselwort, das auf den Zeiger selbst angewendet wird.  
  
-   Der Bezeichner.  
  
-   Ein optionaler Initialisierer.  
  
 Der Deklarator für einen Zeiger auf eine Funktion sieht wie folgt aus:  
  
```  
(* [cv-qualifiers] identifier )( argument-list ) [cv-qualifers]  
[exception specification] [= expression];  
```  
  
-   Für ein Array von Zeigern, sieht die Syntax wie folgt aus:  
  
```  
* identifier [ [ constant-expression ] ]  
```  
  
-   Mehrere Deklaratoren und ihre Initialisierer erscheinen möglicherweise zusammen in einer einzigen Deklaration in einer durch Trennzeichen getrennten Liste, die dem Deklarationsspezifizierer folgt.  
  
 Ein einfaches Beispiel für eine Zeigerdeklaration ist:  
  
```  
char *pch;  
```  
  
 Die vorhergehende Deklaration gibt an, dass `pch` auf ein Objekt vom Typ `char` zeigt.  
  
 Ein komplexeres Beispiel ist  
  
```  
static unsigned int * const ptr;  
```  
  
 Die vorhergehende Deklaration gibt an, dass `ptr` ist ein konstanter Zeiger auf ein Objekt des Typs `unsigned` `int` mit statischer Speicherdauer.  
  
 Das folgende Beispiel zeigt, wie mehrere Zeiger deklariert und initialisiert werden:  
  
```  
static int *p = &i, *q = &j;  
```  
  
 Im vorhergehenden Beispiel, zeigen die Zeiger p und q auf Objekte vom Typ `int` und werden entsprechend mit den Adressen von i und j initialisiert.  Der Speicherklassenspezifizierer `static` gilt für beide Zeiger.  
  
## <a name="example"></a>Beispiel  
  
```  
// pointer.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   int i = 1, j = 2; // local variables on the stack  
   int *p;  
  
   // a pointer may be assigned to "point to" the value of  
   // another variable using the & (address of) operator  
   p = & j;   
  
   // since j was on the stack, this address will be somewhere  
   // on the stack.  Pointers are printed in hex format using  
   // %p and conventionally marked with 0x.    
   printf_s("0x%p\n",  p);  
  
   // The * (indirection operator) can be read as "the value  
   // pointed to by".  
   // Since p is pointing to j, this should print "2"  
   printf_s("0x%p %d\n",  p, *p);  
  
   // changing j will change the result of the indirection  
   // operator on p.  
   j = 7;  
   printf_s("0x%p %d\n",  p, *p );  
  
   // The value of j can also be changed through the pointer  
   // by making an assignment to the dereferenced pointer  
   *p = 10;  
   printf_s("j is %d\n", j); // j is now 10  
  
   // allocate memory on the heap for an integer,  
   // initialize to 5  
   p = new int(5);  
  
   // print the pointer and the object pointed to  
   // the address will be somewhere on the heap  
   printf_s("0x%p %d\n",  p, *p);  
  
   // free the memory pointed to by p  
   delete p;  
  
   // At this point, dereferencing p with *p would trigger  
   // a runtime access violation.  
  
   // Pointer arithmetic may be done with an array declared  
   // on the stack or allocated on the heap with new.  
   // The increment operator takes into account the size   
   // of the objects pointed to.  
   p = new int[5];  
   for (i = 0; i < 5; i++, p++) {  
      *p = i * 10;  
      printf_s("0x%p %d\n", p, *p);  
   }  
  
   // A common expression seen is dereferencing in combination  
   // with increment or decrement operators, as shown here.  
   // The indirection operator * takes precedence over the   
   // increment operator ++.   
   // These are particularly useful in manipulating char arrays.  
   char s1[4] = "cat";  
   char s2[4] = "dog";  
   char* p1 = s1;  
   char* p2 = s2;  
  
   // the following is a string copy operation  
   while (*p1++ = *p2++);  
  
   // s2 was copied into s1, so now they are both equal to "dog"  
   printf_s("%s %s", s1, s2);  
}  
```  
  
```Output  
0x0012FEC8  
0x0012FEC8 2  
0x0012FEC8 7  
j is 10  
0x00320850 5  
0x00320850 0  
0x00320854 10  
0x00320858 20  
0x0032085C 30  
0x00320860 40  
dog dog  
```  
  
## <a name="example"></a>Beispiel  
 Ein weiteres Beispiel illustriert die Verwendung von Zeigern in Datenstrukturen; in diesem Fall eine verknüpfte Liste.  
  
```  
// pointer_linkedlist.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct NewNode {  
   NewNode() : node(0){}  
   int i;  
   NewNode * node;  
};  
  
void WalkList(NewNode * ptr) {  
   if (ptr != 0) {  
      int i = 1;  
      while (ptr->node != 0 ) {  
         cout << "node " << i++ << " = " << ptr->i << endl;  
         ptr = ptr->node;  
      }  
      cout << "node " << i++ << " = " << ptr->i << endl;  
   }  
}  
  
void AddNode(NewNode ** ptr) {  
   NewNode * walker = 0;  
   NewNode * MyNewNode = new NewNode;  
   cout << "enter a number: " << endl;  
   cin >> MyNewNode->i;  
  
   if (*ptr == 0)  
      *ptr = MyNewNode;  
   else  {  
      walker = *ptr;  
      while (walker->node != 0)  
         walker = walker->node;  
  
      walker->node = MyNewNode;  
   }  
}  
  
int main() {  
   char ans = ' ';  
   NewNode * ptr = 0;  
   do {  
      cout << "a (add node)  d (display list)  q (quit)" << endl;  
      cin >> ans;  
      switch (ans) {  
      case 'a':  
         AddNode(&ptr);  
         break;  
      case 'd':  
         WalkList(ptr);  
         break;  
      }  
   } while (ans != 'q');  
}  
```  
  
```Output  
  
      a  
45  
d  
a  
789  
d  
qa (add node)  d (display list)  q (quit)  
enter a number:   
a (add node)  d (display list)  q (quit)  
node 1 = 45  
a (add node)  d (display list)  q (quit)  
enter a number:   
a (add node)  d (display list)  q (quit)  
node 1 = 45  
node 2 = 789  
a (add node)  d (display list)  q (quit)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dereferenzierungsoperator: *](../cpp/indirection-operator-star.md)   
 [address-of-Operator](../cpp/address-of-operator-amp.md)
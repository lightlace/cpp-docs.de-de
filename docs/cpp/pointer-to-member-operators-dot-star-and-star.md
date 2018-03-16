---
title: Pointer-to-Member-Operatoren:. * "und" -&gt;* | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- .*
- ->*
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], pointer
- pointer-to-member operators [C++]
- .* operator
- expressions [C++], operators
- ->* operator
ms.assetid: 2632be3f-1c81-4523-b56c-982a92a68688
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6db7b7190a1374564071775ce2ea6c0777bdf567
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="pointer-to-member-operators--and--gt"></a>Pointer-to-Member-Operatoren:. * "und" -&gt;*
## <a name="syntax"></a>Syntax  
  
```  
expression .* expression  
expression ->* expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Pointer-to-Member-Operatoren,. * und ->\*, Rückgabe des Werts eines bestimmten Klassenmembers für das Objekt, das auf der linken Seite des Ausdrucks angegeben.  Die rechte Seite muss einen Klassenmember angeben.  Im folgenden Beispiel wird die Verwendung dieser Operatoren dargestellt:  
  
```  
// expre_Expressions_with_Pointer_Member_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
class Testpm {  
public:  
   void m_func1() { cout << "m_func1\n"; }  
   int m_num;  
};  
  
// Define derived types pmfn and pmd.  
// These types are pointers to members m_func1() and  
// m_num, respectively.  
void (Testpm::*pmfn)() = &Testpm::m_func1;  
int Testpm::*pmd = &Testpm::m_num;  
  
int main() {  
   Testpm ATestpm;  
   Testpm *pTestpm = new Testpm;  
  
// Access the member function  
   (ATestpm.*pmfn)();  
   (pTestpm->*pmfn)();   // Parentheses required since * binds  
                        // less tightly than the function call.  
  
// Access the member data  
   ATestpm.*pmd = 1;  
   pTestpm->*pmd = 2;  
  
   cout  << ATestpm.*pmd << endl  
         << pTestpm->*pmd << endl;  
   delete pTestpm;  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
m_func1  
m_func1  
1  
2  
```  
  
 Im vorherigen Beispiel wird ein Zeiger auf einen Member, `pmfn` verwendet, um die Memberfunktion `m_func1` aufzurufen. Mit einem weiteren Zeiger auf einen Member, `pmd`, erfolgt der Zugriff auf den `m_num`-Member.  
  
 Der binäre Operator. * kombiniert den ersten Operanden, der ein Objekt des Klassentyps sein muss, mit dem zweiten Operanden, der vom Typ „Pointer-to-Member“ sein muss.  
  
 Der binäre Operator -> * kombiniert den ersten Operanden, der einen Zeiger auf ein Objekt des Klassentyps sein, mit dem zweiten Operanden, die ein "Pointer-to-Member"-Typ sein muss.  
  
 In einem Ausdruck, der den .*-Operator enthält, muss der erste Operand vom Klassentyp des Zeigers auf den Member sein (oder er muss auf ihn zugreifen können), der im zweiten Operanden angegeben wurde, oder er muss ein zugreifbarer Typ sein, der eindeutig von dieser Klasse abgeleitet wurde und für diese Klasse zugreifbar ist.  
  
 In einem Ausdruck mit der-> *-Operator, der erste Operand muss vom Typ "Zeiger auf den Klassentyp" des Typs angegeben werden im zweiten Operanden, oder es muss werden von einem Typ eindeutig von dieser Klasse abgeleitet.  
  
## <a name="example"></a>Beispiel  
 Berücksichtigen Sie die folgenden Klassen und das Programmfragment:  
  
```  
// expre_Expressions_with_Pointer_Member_Operators2.cpp  
// C2440 expected  
class BaseClass {  
public:  
   BaseClass(); // Base class constructor.  
   void Func1();  
};  
  
// Declare a pointer to member function Func1.  
void (BaseClass::*pmfnFunc1)() = &BaseClass::Func1;  
  
class Derived : public BaseClass {  
public:  
   Derived();  // Derived class constructor.  
   void Func2();  
};  
  
// Declare a pointer to member function Func2.  
void (Derived::*pmfnFunc2)() = &Derived::Func2;  
  
int main() {  
   BaseClass ABase;  
   Derived ADerived;  
  
   (ABase.*pmfnFunc1)();   // OK: defined for BaseClass.  
   (ABase.*pmfnFunc2)();   // Error: cannot use base class to  
                           // access pointers to members of  
                           // derived classes.   
  
   (ADerived.*pmfnFunc1)();   // OK: Derived is unambiguously  
                              // derived from BaseClass.   
   (ADerived.*pmfnFunc2)();   // OK: defined for Derived.  
}  
```  
  
 Das Ergebnis der. * oder ->\* Pointer-to-Member-Operatoren ist ein Objekt oder eine Funktion des Typs in der Deklaration eines Zeigers auf den Member angegeben. Im vorherigen Beispiel ist das Ergebnis des Ausdrucks `ADerived.*pmfnFunc1()` ein Zeiger auf eine Funktion, die "void" zurückgibt. Dieses Ergebnis ist ein L-Wert, wenn der zweite Operand ein L-Wert ist.  
  
> [!NOTE]
>  Wenn das Ergebnis eines der Zeiger-auf-Member-Operatoren eine Funktion ist, kann das Ergebnis nur als Operand für den Funktionsaufrufoperator verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)


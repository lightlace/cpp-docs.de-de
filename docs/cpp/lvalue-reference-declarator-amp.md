---
title: "Lvalue-Verweisdeklarator: &amp;"
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
  - "&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (Operator), Verweisoperator"
  - "Verweisoperator"
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Lvalue-Verweisdeklarator: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Enthält die Adresse eines Objekts, verhält sich jedoch syntaktisch wie ein Objekt.  
  
## Syntax  
  
```  
  
type-id & cast-expression  
```  
  
## Hinweise  
 Sie können sich einen lvalue\-Verweis als einen anderen Namen für ein Objekt vorstellen.  Eine lvalue\-Verweisdeklaration enthält eine optionale Liste von Bezeichnern, gefolgt von einem Verweisdeklarator.  Ein Verweis muss initialisiert werden und kann nicht geändert werden.  
  
 Jedes Objekt, dessen Adresse in einen angegebenen Zeigertyp konvertiert werden kann, kann auch in den ähnlichen Referenztyp konvertiert werden.  Beispielsweise kann jedes Objekt, dessen Adresse in den Typ `char *` konvertiert werden kann, auch in den Typ `char &` konvertiert werden.  
  
 Verwechseln Sie Verweisdeklarationen nicht mit der Verwendung des [address\-of\-Operators](../cpp/address-of-operator-amp.md).  Wenn `&`*identifier* ein Typ vorangestellt wird, wie z. B. `int` oder `char`, wird *identifier* als Verweis auf den Typ deklariert.  Wenn `&`*identifier* kein Typ vorangestellt ist, wird er als address\-of\-Operator verwendet.  
  
## Beispiel  
 Das folgende Beispiel zeigt den Verweisdeklarator, indem ein `Person`\-Objekt und ein Verweis auf dieses Objekt deklariert wird.  Da `rFriend` ein Verweis auf `myFriend` ist, ändert die Aktualisierung einer der Variablen das gleiche Objekt.  
  
```  
// reference_declarator.cpp  
// compile with: /EHsc  
// Demonstrates the reference declarator.  
#include <iostream>  
using namespace std;  
  
struct Person  
{  
    char* Name;  
    short Age;  
};  
  
int main()  
{  
   // Declare a Person object.  
   Person myFriend;  
  
   // Declare a reference to the Person object.  
   Person& rFriend = myFriend;  
  
   // Set the fields of the Person object.  
   // Updating either variable changes the same object.  
   myFriend.Name = "Bill";  
   rFriend.Age = 40;  
  
   // Print the fields of the Person object to the console.  
   cout << rFriend.Name << " is " << myFriend.Age << endl;  
}  
```  
  
  **Bill ist 40.**   
## Siehe auch  
 [Verweise](../cpp/references-cpp.md)   
 [Verweistyp\-Funktionsargumente](../cpp/reference-type-function-arguments.md)   
 [Verweistyp\-Funktionsrückgaben](../cpp/reference-type-function-returns.md)   
 [Verweise auf Zeiger](../cpp/references-to-pointers.md)
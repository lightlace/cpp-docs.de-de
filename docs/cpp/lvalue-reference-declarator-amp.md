---
title: 'Lvalue-Verweisdeklarator: &amp; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6aa0c0a18d77f685369681c0d0400ada6f879e9d
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="lvalue-reference-declarator-amp"></a>Lvalue-Verweisdeklarator:&amp;
Enthält die Adresse eines Objekts, verhält sich jedoch syntaktisch wie ein Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
type-id & cast-expression  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können sich einen lvalue-Verweis als einen anderen Namen für ein Objekt vorstellen. Eine lvalue-Verweisdeklaration enthält eine optionale Liste von Bezeichnern, gefolgt von einem Verweisdeklarator. Ein Verweis muss initialisiert werden und kann nicht geändert werden.  
  
 Jedes Objekt, dessen Adresse in einen angegebenen Zeigertyp konvertiert werden kann, kann auch in den ähnlichen Referenztyp konvertiert werden. Beispielsweise kann jedes Objekt, dessen Adresse in den Typ `char *` konvertiert werden kann, auch in den Typ `char &` konvertiert werden.  
  
 Verwechseln Sie Verweisdeklarationen durch Verwendung einer nicht die [Address-of-Operator](../cpp/address-of-operator-amp.md). Wenn die `&` *Bezeichner* ist ein Typ vorangestellt, wie z. B. `int` oder `char`, *Bezeichner* als Verweis auf den Typ deklariert wird. Wenn `&` *Bezeichner* geht nicht von einem Typ ist, wird der Address-of-Operators.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt den Verweisdeklarator, indem ein `Person`-Objekt und ein Verweis auf dieses Objekt deklariert wird. Da `rFriend` ein Verweis auf `myFriend` ist, ändert die Aktualisierung einer der Variablen das gleiche Objekt.  
  
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
  
```Output  
Bill is 40  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise](../cpp/references-cpp.md)   
 [Verweistyp Funktionsargumente](../cpp/reference-type-function-arguments.md)   
 [Verweistyp-Funktionsrückgaben](../cpp/reference-type-function-returns.md)   
 [Verweise auf Zeiger](../cpp/references-to-pointers.md)

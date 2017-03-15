---
title: Compiler Fehler C3861 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3861
dev_langs:
- C++
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 10
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 177890dcd3ff2abf07f5d9e282efd4a9fd7121a7
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3861"></a>Compilerfehler C3861
'identifier': Bezeichner nicht gefunden  
  
Der Compiler konnte einen Verweis sogar mit der Suche „argument-dependent“ zu einem Bezeichner nicht auflösen.  
  
Prüfen Sie zum Beheben dieses Fehlers die Identifziererdeklaration hinsichtlich Groß-/Kleinschreibung und Rechtschreibung. Überprüfen Sie, ob [Bereich Auflösung Operatoren](../../cpp/scope-resolution-operator.md) und Namespace [using-Direktiven](../../cpp/namespaces-cpp.md#using_directives) ordnungsgemäß verwendet werden. Wenn der Bezeichner in einer Headerdatei deklariert wird, muss der Header einbezogen werden, bevor er referenziert wird. Überprüfen Sie außerdem, dass der Bezeichner nicht durch ausgeschlossen ist [bedingten Kompilierungsdirektiven](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird C3861 generiert:  
  
```cpp  
// C3861.cpp  
void f2(){}  
int main() {  
   f();   // C3861  
   f2();   // OK  
}  
```  
  
## <a name="example"></a>Beispiel  
Ausnahmeklassen in der C++-Standardbibliothek sind jetzt im `std`-Namespace.  
  
```cpp  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```

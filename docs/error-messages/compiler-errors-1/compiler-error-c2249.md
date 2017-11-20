---
title: Compilerfehler C2249 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2249
dev_langs:
- C++
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5878c28ed0b4fc2663c17021aa9e277ccaa8ad4e
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2249"></a>Compilerfehler C2249
'Member': kein Zugriff auf den Pfad Zugriff auf Element deklariert wird, in der virtuellen Basis 'Class'  
  
 Die `member` wird von einem Nonpublic geerbt `virtual` Basisklasse der Klasse oder Struktur.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2249 generiert.  
  
```  
// C2249.cpp  
class A {  
private:  
   void privFunc( void ) {};  
public:  
   void pubFunc( void ) {};  
};  
  
class B : virtual public A {} b;  
  
int main() {  
   b.privFunc();    // C2249, private member of A  
   b.pubFunc();    // OK  
}  
```  
  
## <a name="example"></a>Beispiel  
 C2249 kann auch auftreten, wenn Sie versuchen, einen Stream aus der C++-Standardbibliothek in einen anderen Stream zuzuweisen.  Im folgenden Beispiel wird C2249 generiert.  
  
```  
// C2249_2.cpp  
#include <iostream>  
using namespace std;  
int main() {  
   cout = cerr;   // C2249  
   #define cout cerr;   // OK  
}  
```
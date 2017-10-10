---
title: Compilerfehler Fehler C2079 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2079
dev_langs:
- C++
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 236e40ed865230416ddde9511420c1cf333d2687
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2079"></a>Compilerfehler Fehler C2079
'Bezeichner' wird nicht definierte Klasse/Struktur/Union "Name" verwendet.  
  
 Der angegebene Bezeichner ist eine nicht definierte Klasse, Struktur oder Union.  
  
 Dieser Fehler kann durch die Initialisierung einer anonymen Union verursacht werden.  
  
 Im folgenden Beispiel wird C2079 generiert:  
  
```  
// C2079.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   std::ifstream g;   // C2079  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2079b.cpp  
// compile with: /EHsc  
#include <fstream>  
int main( ) {  
   std::ifstream g;  
}  
```  
  
 C2079 kann auch auftreten, wenn Sie versuchen, ein Objekt auf dem Stapel eines Typs deklarieren, deren Vorwärtsdeklaration nur im Gültigkeitsbereich ist.  
  
```  
// C2079c.cpp  
class A;  
  
class B {  
   A a;   // C2079  
};  
  
class A {};  
```  
  
 Mögliche Lösung:  
  
```  
// C2079d.cpp  
// compile with: /c  
class A;  
class C {};  
  
class B {  
   A * a;  
   C c;  
};  
  
class A {};  
```

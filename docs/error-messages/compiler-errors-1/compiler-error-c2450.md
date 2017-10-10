---
title: Compilerfehler C2450 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2450
dev_langs:
- C++
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 484eeb2c8c586a3f552cb77b5afd1671c199a551
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2450"></a>Compilerfehler C2450
Switch-Ausdruck vom Typ "Type" ist nicht zulässig  
  
 Die `switch` Ausdruck ergibt einen ungültigen Typ. Es muss ein ganzzahliger Typ oder einen Klassentyp ausgewertet mit eindeutige Konvertierung in einen Integer-Datentyp. Wenn sie einen benutzerdefinierten Typ ergibt, müssen Sie einen Konvertierungsoperator angeben.  
  
 Im folgende Beispiel wird C2450 generiert:  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```

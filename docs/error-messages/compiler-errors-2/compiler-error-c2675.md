---
title: Compilerfehler Fehler C2675 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2675
dev_langs:
- C++
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c9c5815e7c57eb2469599a26c2cbc5202018f27e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2675"></a>Compilerfehler Fehler C2675
unärer 'Operator Operator': 'Typ' definiert für den vordefinierten Operator nicht diesen Operator oder eine Konvertierung in einen zulässigen Typ  
  
 C2675 kann auch auftreten, wenn einen unäroperator, und der Typ ist nicht der Operator oder eine Konvertierung in einen geeigneten Typ für den vordefinierten Operator definieren. Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2675 generiert.  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```

---
title: Compiler-Fehler C2774 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2774
dev_langs: C++
helpviewer_keywords: C2774
ms.assetid: 10f428c6-7f49-489a-92ba-6ef978b7caaf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: efa25c9e1c5fa755dc2b31290ab8c921366455c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2774"></a>Compiler-Fehler C2774 generiert
'Bezeichner': keine Methode "put" bezieht sich auf diese Eigenschaft  
  
 Ein Datenmember deklariert mit [Eigenschaft](../../cpp/property-cpp.md) hat keine `put` -Funktion, aber ein Ausdruck versucht, dessen Wert festzulegen.  
  
 Im folgende Beispiel wird C2774 generiert:  
  
```  
// C2774.cpp  
struct A {  
   __declspec(property(get=GetProp)) int prop;  
   int GetProp(void);  
  
   __declspec(property(get=GetProp2, put=PutProp2)) int prop2;  
   int GetProp2(void);  
   void PutProp2(int);  
};  
  
int main() {  
   A* pa = new A;  
   int val = 0;  
   pa->prop = val;   // C2774  
   pa->prop++;   // C2774  
}  
```
---
title: Compilerfehler C2976 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2976
dev_langs:
- C++
helpviewer_keywords:
- C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 49250abe3cef048b15f7af87f643002640fe6bf5
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2976"></a>Compilerfehler C2976
'Bezeichner': nicht genügend Typargumente  
  
 Eine generische oder Vorlagendeklaration fehlt mindestens eine tatsächliche Argumente. Überprüfen Sie die generische oder Vorlagendeklaration, um die richtige Anzahl von Parametern zu ermitteln.  
  
 Dieser Fehler kann durch fehlende Vorlagenargumente in C++-Standardbibliothek Komponenten verursacht werden.  
  
 Im folgenden Beispiel wird C2976 generiert:  
  
```  
// C2976.cpp  
template <class T>   
struct TC {  
   T t;  
};  
int main() {  
   TC<>* t;   // C2976  
   TC<int>* t2;   // OK  
}  
```  
  
 C2976 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2976b.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC {  
   T t;  
};  
  
int main() {  
   GC<>^ g;   // C2976  
   GC<int>^ g2;   // OK  
}  
```

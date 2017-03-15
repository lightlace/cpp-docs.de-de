---
title: Compilerfehler C2976 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: d691eba50403819e1a468b850995f4ae55a3731f
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2976"></a>Compilerfehler C2976
'Bezeichner': nicht genügend Typargumente  
  
 Eine generische oder eine Vorlage fehlt mindestens eine tatsächliche Argumente. Überprüfen Sie die generische oder Vorlagendeklaration, um die richtige Anzahl von Parametern zu ermitteln.  
  
 Dieser Fehler kann durch fehlende Vorlagenargumente in C++-Standardbibliothek Komponenten verursacht werden.  
  
 Im folgende Beispiel wird C2976 generiert:  
  
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

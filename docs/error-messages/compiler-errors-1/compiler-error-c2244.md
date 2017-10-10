---
title: Compilerfehler C2244 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2244
dev_langs:
- C++
helpviewer_keywords:
- C2244
ms.assetid: d9911c12-ceb5-4f93-ac47-b44a485215c2
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fc2afb310e7fdee866d437631f4a20554fc7a872
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2244"></a>Compilerfehler C2244
'Bezeichner': kann nicht entsprechend der Definition der Funktion um eine bestehende Deklaration  
  
 Eine ungewöhnliche Verwenden des unären Operators + wurde vor einem Funktionsaufruf verwendet, die kein Klammer vorhanden war.  
  
 Dieser Fehler tritt nur in C++-Projekten.  
  
 Im folgenden Beispiel wird C2244 generiert:  
  
```  
// C2244.cpp  
int func(char) {  
   return 0;  
}   
  
int func(int) {  
   return 0;  
}  
  
int main() {  
   +func;   // C2244  
}  
```  
  
 C2244 kann auch auftreten, wenn eine falsche Funktionssignatur für eine Memberfunktion einer Klassenvorlage verwendet wird.  
  
```  
// C2244b.cpp  
// compile with: /c  
template<class T>   
class XYZ {  
   void func(T t);  
};  
  
template<class T>  
void XYZ<T>::func(int i) {}   // C2244 wrong function signature  
// try the following line instead  
// void XYZ<T>::func(T t) {}  
```  
  
 C2244 kann auch auftreten, wenn eine falsche Funktionssignatur für eine Memberfunktionsvorlage verwendet wird.  
  
```  
// C2244c.cpp  
// compile with: /c  
class ABC {  
   template<class T>   
   void func(int i, T t);  
};  
  
template<class T>  
void ABC::func(int i) {}   // C2244 wrong signature  
// try the following line instead  
// void ABC::func(int i, T t) {}  
```  
  
 Eine Funktionsvorlage kann nicht teilweise spezialisiert werden.  
  
```  
// C2244d.cpp  
template<class T, class U>  
class QRS {  
   void func(T t, U u);  
};  
  
template<class T>  
void QRS<T,int>::func(T t, int u) {}   // C2244  
```

---
title: Compilerfehler C2797 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2797
dev_langs:
- C++
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 09c5a26a1a7bb594419d2db211f86074d01da84e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2797"></a>Compilerfehler C2797
(Veraltet) Listen-Initialisierung innerhalb Memberinitialisiererliste oder nicht statische Daten-Memberinitialisierer ist nicht implementiert.  
  
 Diese Warnung wird in Visual Studio 2015 veraltet. In Visual Studio 2013 und früheren Versionen implementiert nicht Listen-Initialisierung innerhalb einer Memberinitialisiererliste oder eine nicht statische datenmemberinitialisierer Visual C++-Compiler. Vor dem Visual Studio 2013 Update 3 wurde dies im Hintergrund in einen Funktionsaufruf konvertiert, der zur Generierung von ungültigem Code führen könnte. Visual Studio 2013 Update 3 meldet dies als Fehler.  
  
 In diesem Beispiel wird C2797 generiert:  
  
```  
#include <vector>  
struct S {  
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'  
  
    std::vector<int> v1;  
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'  
};  
  
```  
  
 In diesem Beispiel wird auch die C2797:  
  
```  
struct S1 {  
    int i;  
};  
  
struct S2 {  
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664  
    S1 s1;  
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664  
};  
  
```  
  
 Um dieses Problem zu beheben, können Sie die explizite Konstruktion von inneren Listen verwendn. Beispiel:  
  
```  
#include <vector>  
typedef std::vector<int> Vector;  
struct S {  
    S() : v1(Vector{1}) {}  
  
    Vector v1;  
    Vector v2 = Vector{1, 2};  
};  
  
```  
  
 Wenn Sie keine Listen-Initialisierung erfordern:  
  
```  
struct S {  
    S() : s1("") {}  
  
    std::string s1;  
    std::string s2 = std::string("");  
};  
  
```  
  
 (Der Compiler in Visual Studio 2013 Fall vor dem Visual Studio 2013 Update 3 hat dies nur implizit ausgeführt.)
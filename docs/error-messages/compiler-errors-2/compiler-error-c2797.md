---
title: Compilerfehler C2797 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 5eea0aae37627015f8723835e4e3e1cb0c6d2e94
ms.lasthandoff: 04/24/2017

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

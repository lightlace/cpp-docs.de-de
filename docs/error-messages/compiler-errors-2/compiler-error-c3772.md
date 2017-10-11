---
title: Compilerfehler C3772 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3772
dev_langs:
- C++
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c2f6d59a03757ca609a821fd0ca7d520ffdbf8ba
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3772"></a>Compilerfehler C3772
"Name": Ungültige Friend-Vorlagendeklaration.  
  
Es ist unzulässig, einen "Friend" einer Spezialisierung einer Klassenvorlage zu deklarieren. Sie können keine explizite oder partielle Spezialisierung einer Klassenvorlage deklarieren und in derselben Anweisung einen "Friend" dieser Spezialisierung deklarieren. Die *Name* -Platzhalter identifiziert die ungültige Deklaration.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Sie sollten keinen "Friend" der Spezialisierung einer Klassenvorlage deklarieren.  
  
-   Deklarieren Sie einen "Friend" der Klassenvorlage oder einen "Friend" einer bestimmten partiellen oder expliziten Spezialisierung, sofern dies für Ihre Anwendung geeignet ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel tritt ein Fehler auf, da ein "Friend" einer partiellen Spezialisierung einer Klassenvorlage deklariert wird.  
  
```cpp  
// c3772.cpp  
// compile with: /c  
  
// A class template.  
    template<class T> class A {};  
  
// A partial specialization of the class template.  
    template<class T> class A<T*> {};  
  
// An explicit specialization.  
    template<> class A<char>;  
  
class X {  
// Invalid declaration of a friend of a partial specialization.  
    template<class T> friend class A<T*>; // C3772  
  
// Instead, if it is appropriate for your application, declare a   
// friend of the class template. Consequently, all specializations   
// of the class template are friends:  
//    template<class T> friend class A;  
// Or declare a friend of a particular partial specialization:  
//    friend class A<int*>;  
// Or declare a friend of a particular explicit specialization:  
//    friend class A<char>;  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
[Vorlagen](../../cpp/templates-cpp.md)   
[Spezialisierung einer Klassenvorlage](../../cpp/template-specialization-cpp.md)   


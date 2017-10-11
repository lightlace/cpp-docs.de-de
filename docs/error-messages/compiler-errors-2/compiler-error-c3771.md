---
title: Compilerfehler C3771 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3771
dev_langs:
- C++
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: dc3e9639fa83524e797c22edd771c847046f0e3c
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3771"></a>Compilerfehler C3771
"Bezeichner": Die Friend-Deklaration kann im nächsten Namespacebereich nicht gefunden werden.  
  
Die Klassenvorlagendeklaration für den angegebenen *Bezeichner* der Vorlage wurde im aktuellen Namespace nicht gefunden.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass die Klassenvorlagendeklaration für den Vorlagenbezeichner im aktuellen Namespace definiert ist oder dass der Vorlagenbezeichner ein voll qualifizierter Name ist.  
  
## <a name="example"></a>Beispiel  
Im folgenden Codebeispiel werden eine Klassenvorlage und Funktion im Namespace `NA`deklariert, allerdings wird versucht, eine Friend-Funktionsvorlage im Namespace `NB`zu deklarieren.  
  
```cpp  
// C3771.cpp   
// compile with: /c  
  
namespace NA {  
template<class T> class A {  
    void aFunction(T t) {};  
    };  
}  
// using namespace NA;  
namespace NB {  
    class X {  
        template<class T> friend void A<T>::aFunction(T); // C3771  
// try the following line instead  
//      template<class T> friend void NA::A<T>::aFunction(T);  
// or try "using namespace NA;" instead.  
    };  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
[Vorlagen](../../cpp/templates-cpp.md)  

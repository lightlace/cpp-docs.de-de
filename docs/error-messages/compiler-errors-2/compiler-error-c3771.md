---
title: Compilerfehler C3771 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3771
dev_langs: C++
helpviewer_keywords: C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d1f552eee7ac20c086240a4ce79fd3616127268b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
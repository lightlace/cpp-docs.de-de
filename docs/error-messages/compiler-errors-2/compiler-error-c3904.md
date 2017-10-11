---
title: Compilerfehler C3904 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3904
dev_langs:
- C++
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 31a6f728fdbfb9540245cf85879adef8c1827d2e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3904"></a>Compilerfehler C3904
"Property_accessor": muss Zahl Parameter angeben  
  
 Überprüfen Sie die Anzahl von Parametern in Ihre `get` und `set` Methoden für die Eigenschaftendimensionen.  
  
-   Die Anzahl von Parametern für die `get` Methode muss gleich der Anzahl der Dimensionen der Eigenschaft oder NULL für nicht indizierte Eigenschaften.  
  
-   Die Anzahl der Parameter, der die `set` Methode muss entweder mehr als die Anzahl der Dimensionen der Eigenschaft.  
  
 Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3904 generiert.  
  
```  
// C3904.cpp  
// compile with: /clr /c  
ref class X {  
   property int P {  
      // set  
      void set();   // C3904  
      // try the following line instead  
      // void set(int);  
  
      // get  
      int get(int, int);   // C3904  
      // try the following line instead  
      // int get();  
   };  
};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3904 generiert.  
  
```  
// C3904b.cpp  
// compile with: /clr /c  
ref struct X {  
   property int Q[double, double, float, float, void*, int] {  
      // set  
      void set(double, void*);   // C3904  
      // try the following line instead  
      // void set(double, double, float, float, void*, int, int);  
  
      // get  
      int get();   // C3904  
      // try the following line instead  
      // int get(double, double, float, float, void*, int);  
   }  
};  
```

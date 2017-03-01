---
title: Compilerfehler C3352 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3352
dev_langs:
- C++
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
caps.latest.revision: 11
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: fb65402b78f777d4a2dcfce2a4366444a259e5d9
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3352"></a>Compilerfehler C3352
'Funktion': die angegebene Funktion entspricht nicht dem Typ des Delegaten 'Typ'  
  
 Die Parameterlisten für `function` und der Delegaten stimmen nicht überein.  
  
 Weitere Informationen finden Sie unter [Delegaten (C++-Komponentenerweiterungen)](../../windows/delegate-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3352 generiert:  
  
```  
// C3352.cpp  
// compile with: /clr  
delegate int D( int, int );  
ref class C {  
public:  
   int mf( int ) {  
      return 1;  
   }  
  
   // Uncomment the following line to resolve.  
   // int mf(int, int) { return 1; }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352  
}  
```  


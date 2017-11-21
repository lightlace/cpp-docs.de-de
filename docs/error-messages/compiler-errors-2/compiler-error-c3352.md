---
title: Compilerfehler C3352 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3352
dev_langs: C++
helpviewer_keywords: C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65643abc883cfd0674dbb908c8ab26f274f65cd4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3352"></a>Compilerfehler C3352
'Funktion': die angegebene Funktion entspricht nicht den Typ des Delegaten "Type"  
  
 Die Parameterlisten für `function` und der Delegaten stimmen nicht überein.  
  
 Weitere Informationen finden Sie unter [Delegate (Komponentenerweiterungen für C++)](../../windows/delegate-cpp-component-extensions.md).  
  
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

---
title: Compilerwarnung (Stufe 4) C4487 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4487
dev_langs: C++
helpviewer_keywords: C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 01ae890c5566132462a5bd259341e62b97610ece
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4487"></a>Compilerwarnung (Stufe 4) C4487
'Abgeleitete_Klassenfunktion': geerbte nicht virtuelle Methode "Basisklassenfunktion" ist jedoch nicht explizit gekennzeichnet "new"  
  
 Eine Funktion in einer abgeleiteten Klasse weist die gleiche Signatur wie eine nicht virtuelle Basisklasse-Funktion. C4487 erinnert Sie daran, dass die Funktion der abgeleiteten Klasse die Funktion der Basisklasse nicht überschreibt. Markieren Sie die Funktion der abgeleiteten Klasse als explizit `new` auf diese Warnung zu beheben.  
  
 Weitere Informationen finden Sie unter [new (neuer Slot in Vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4487 generiert.  
  
```  
// C4487.cpp  
// compile with: /W4 /clr  
using namespace System;  
public ref struct B {  
   void f() { Console::WriteLine("in B::f"); }  
   void g() { Console::WriteLine("in B::g"); }  
};  
  
public ref struct D : B {  
   void f() { Console::WriteLine("in D::f"); }   // C4487  
   void g() new { Console::WriteLine("in D::g"); }   // OK  
};  
  
int main() {  
   B ^ a = gcnew D;  
   // will call base class functions  
   a->f();  
   a->g();  
}  
```
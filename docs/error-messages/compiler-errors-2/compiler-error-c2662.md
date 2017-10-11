---
title: Compiler-Fehler C2662 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2662
dev_langs:
- C++
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e914431ff7303b6689dc7ee1da57e2a11b309a37
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2662"></a>Compiler-Fehler C2662 generiert
'Funktion': 'this' Zeiger von "Typ1" in "Typ2" kann nicht konvertiert werden.  
  
 Der Compiler konnte nicht konvertiert werden. die `this` Zeiger von `type1` auf `type2`.  
  
 Dieser Fehler kann verursacht werden, durch den Aufruf einer nicht -`const` Member-Funktion auf einem `const` Objekt.  Folgende Lösungen möglich:  
  
-   Entfernen Sie die `const` aus der Deklaration des Objekts.  
  
-   Hinzufügen `const` auf die Member-Funktion.  
  
 Im folgende Beispiel wird C2662 generiert:  
  
```  
// C2662.cpp  
class C {  
public:  
   void func1();  
   void func2() const{}  
} const c;  
  
int main() {  
   c.func1();   // C2662  
   c.func2();   // OK  
}  
```  
  
 Beim Kompilieren mit **"/ CLR"**, eine Funktion für nicht aufgerufen werden können eine `const` oder `volatile` verwalteten Typ qualifiziert. Eine const-Memberfunktion einer verwalteten Klasse nicht deklariert werden, damit Methoden für const verwaltete Objekte aufgerufen werden kann.  
  
```  
// C2662_b.cpp  
// compile with: /c /clr  
ref struct M {  
   property M^ Type {  
      M^ get() { return this; }  
   }  
  
   void operator=(const M %m) {  
      M ^ prop = m.Type;   // C2662  
   }  
};  
  
ref struct N {  
   property N^ Type {  
      N^ get() { return this; }  
   }  
  
   void operator=(N % n) {  
      N ^ prop = n.Type;   // OK  
   }  
};  
```  
  
 Im folgende Beispiel wird C2662 generiert:  
  
```  
// C2662_c.cpp  
// compile with: /c  
// C2662 expected  
typedef int ISXVD;  
typedef unsigned char BYTE;  
  
class LXBASE {  
protected:  
    BYTE *m_rgb;  
};  
  
class LXISXVD:LXBASE {  
public:  
   // Delete the following line to resolve.  
   ISXVD *PMin() { return (ISXVD *)m_rgb; }  
  
   ISXVD *PMin2() const { return (ISXVD *)m_rgb; };   // OK  
};  
  
void F(const LXISXVD *plxisxvd, int iDim) {  
   ISXVD isxvd;  
   // Delete the following line to resolve.  
   isxvd = plxisxvd->PMin()[iDim];  
  
   isxvd = plxisxvd->PMin2()[iDim];    
}  
```

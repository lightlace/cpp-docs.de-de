---
title: Compiler-Fehler C2662 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: aa2c22d7fbe8b017617fcad41327feef7f8fd19a
ms.lasthandoff: 04/04/2017

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

---
title: "Compilerfehler C2662 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2662"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2662"
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2662
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Konvertierung des 'this'\-Zeigers von 'Typ1' in 'Typ2' nicht möglich  
  
 Der Compiler konnte den `this`\-Zeiger nicht von `type1` in `type2` konvertieren.  
  
 Dieser Fehler kann auftreten, wenn eine nicht mit `const` deklarierte Memberfunktion eines `const`\-Objekts aufgerufen wird.  Mögliche Lösungen:  
  
-   Entfernen Sie `const` aus der Objektdeklaration.  
  
-   Fügen `const` der Memberfunktion hinzu.  
  
 Im folgenden Beispiel wird C2662 generiert:  
  
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
  
 Wenn Sie mit **\/clr** kompilieren, können Sie keine Funktion auf einem mit `const` oder `volatile` gekennzeichneten verwalteten Typ aufrufen.  Sie können keine const\-Memberfunktion einer verwalteten Klasse deklarieren. Daher können keine Methoden auf verwalteten const\-Objekten aufgerufen werden.  
  
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
  
 Im folgenden Beispiel wird C2662 generiert:  
  
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
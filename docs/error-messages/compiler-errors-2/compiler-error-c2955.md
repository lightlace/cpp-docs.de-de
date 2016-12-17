---
title: "Compilerfehler C2955"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2955"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2955"
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2955
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Bezeichner“: Die Verwendung der Klassenvorlage oder des generischen Alias erfordert eine Vorlagen\- bzw. eine generische Argumentliste.  
  
 Eine Klassenvorlage oder generische Klasse kann ohne Vorlagen\- bzw. generische Argumentliste nicht als Bezeichner verwendet werden.  
  
 Weitere Informationen finden Sie unter [Klassenvorlagen](../../cpp/class-templates.md).  
  
 Im folgenden Beispiel wird C2955 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2955.cpp  
// compile with: /c  
template<class T>   
class X {};  
  
X x1;   // C2955  
X<int> x2;   // OK - this is how to fix it.  
```  
  
 C2955 kann auch bei dem Versuch auftreten, eine abweichende Definition für eine Funktion zu erstellen, die in einer Klassenvorlage deklariert wurde:  
  
```  
// C2955_b.cpp  
// compile with: /c  
template <class T>  
class CT {  
public:  
   void CTFunc();  
   void CTFunc2();  
};  
  
void CT::CTFunc() {}   // C2955  
  
// OK - this is how to fix it  
template <class T>  
void CT<T>::CTFunc2() {}  
  
```  
  
 C2955 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2955_c.cpp  
// compile with: /clr  
generic <class T>   
ref struct GC {   
   T t;  
};  
  
int main() {  
   GC^ g;   // C2955  
   GC <int>^ g;  
}  
```
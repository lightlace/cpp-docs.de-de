---
title: "Compilerfehler C2896 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2896"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2896"
ms.assetid: b600407b-cb05-42e3-9069-2aa6960f0eaa
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2896
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion1': Funktionsvorlage 'Funktion2' kann nicht als Argument verwendet werden  
  
 Eine Funktionsvorlage kann nicht als Argument für eine andere Funktionsvorlage verwendet werden.  
  
 Im folgenden Beispiel wird C2896 generiert:  
  
```  
// C2896.cpp  
template<class T1, class T2> void f1(void(*)(T1, T2));  
template<class T1, class T2> void f2(T1, T2);  
  
int main() {  
   f1(f2);   // C2896  
}  
```  
  
 C2896 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2896b.cpp  
// compile with: /clr  
generic<class T1> void gf1(T1){}  
generic<class T1> void gf2(T1){}  
  
int main() {  
   gf1(gf2);   // C2896  
   gf1(1);   // OK  
}  
```
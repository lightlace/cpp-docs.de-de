---
title: "Compilerfehler C2683"
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
  - "C2683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2683"
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Umwandlung': 'Typ' ist kein polymorpher Typ  
  
 Sie können [dynamic\_cast](../../cpp/dynamic-cast-operator.md) nicht verwenden, um von einer nicht polymorphen Klasse \(d. h. einer Klasse ohne virtuelle Funktionen\) umzuwandeln.  
  
 Sie können [static\_cast](../../cpp/static-cast-operator.md) verwenden, um Konvertierungen von nicht polymorphen Typen durchzuführen.  Bei Verwendung von `static_cast` wird jedoch keine Laufzeitüberprüfung durchgeführt.  
  
 Im folgenden Beispiel wird C2683 generiert:  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```
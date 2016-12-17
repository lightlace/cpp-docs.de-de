---
title: "Compilerfehler C2844"
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
  - "C2844"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2844"
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2844
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member' : Kann kein Element der Schnittstelle 'Schnittstelle' sein  
  
 Eine [interface class](../../windows/interface-class-cpp-component-extensions.md) kann keinen Datenmember enthalten, sofern er nicht gleichzeitig eine Eigenschaft ist.  
  
 Andere Elemente als Eigenschaften oder Memberfunktionen sind in einer Schnittstelle nicht zulässig.  Auch die Verwendung von Konstruktoren, Destruktoren und Operatoren ist untersagt.  
  
 Im folgenden Beispiel wird C2844 generiert:  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  
  
 Im folgenden Beispiel wird C2844 generiert:  
  
```  
// C2844b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
__gc __interface IFace {  
   int i;   // C2844  
   // try the following line instead  
   // __property int Size { get; set; };  
};  
```
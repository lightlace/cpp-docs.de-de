---
title: "Portabilit&#228;t an ABI-Grenzen (Modern C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Portabilit&#228;t an ABI-Grenzen (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Portable Typen der Verwendung ausreichend und Konventionen an den binären Schnittstellengrenzen.  Ein "besser portierbar Typ" ist Wechselstrom\-integrierterDatentyp oder eine Struktur, die nur C\-integrierteDatentypen enthält.  Klassentypen können nur verwendet werden, wenn Aufrufer und Aufgerufenem über Layouts, Aufrufkonvention, usw. sich dann sind. Dies ist nur möglich, wenn beide denselben Compiler und Compilereinstellungen kompiliert werden.  
  
## Wie Sie eine Klasse für C\-Portabilität vereinfacht  
 Wenn Aufrufer möglicherweise einen anderen Compiler\/Sprache kompiliert werden, dann "vereinfachen Sie" zu einer API extern "C" mit einer bestimmten Aufrufkonvention:  
  
```cpp  
// class widget {  
//   widget();  
//   ~widget();  
//   double method( int, gadget& );  
// };  
extern “C” {    // functions using explicit “this”  
  struct widget;   // + opaque type (fwd decl only)  
  widget* STDCALL widget_create();    // ctor → create new  “this”  
  void STDCALL widget_destroy( widget* );    // dtor → consume “this”  
  double STDCALL widget_method( widget*, int, gadget* );    // method → use “this”  
}  
  
```  
  
## Siehe auch  
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
---
title: "Compilerfehler C3900 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3900"
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member': Ist im aktuellen Gültigkeitsbereich nicht zulässig  
  
 Eigenschaftenblöcke können nur Funktionsdeklarationen und Inlinefunktionsdefinitionen enthalten.  In Eigenschaftenblöcken sind nur Funktionen als Member erlaubt.  Typdefinitionen, Operatoren oder Friend\-Funktionen sind nicht zulässig.  Weitere Informationen finden Sie unter [Eigenschaft](../../windows/property-cpp-component-extensions.md).  
  
 Ereignisdefinitionen können nur Zugriffsmethoden und Funktionen enthalten.  
  
 Im folgenden Beispiel wird C3900 generiert:  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 Im folgenden Beispiel wird C3900 generiert:  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```
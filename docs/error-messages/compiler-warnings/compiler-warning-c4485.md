---
title: "Compilerwarnung C4485"
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
  - "C4485"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4485"
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4485
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override\_function': Stimmt mit der 'base\_class\_function '\-Basismethode der Verweisklasse überein, ist jedoch nicht als 'new' oder 'override' markiert; 'new' \(und 'virtual'\) wird angenommen  
  
 Ein Accessor überschreibt mit oder ohne `virtual`\-Schlüsselwort eine Basisklassen\-Accessorfunktion, der `override`\-Spezifizierer oder der `new`\-Spezifizierer war jedoch nicht Teil der überschreibenden Funktionssignatur.  Fügen Sie den `new`\-Spezifizierer oder den `override`\-Spezifizierer hinzu, um diese Warnung zu vermeiden.  
  
 Weitere Informationen finden Sie unter [override](../../windows/override-cpp-component-extensions.md) und [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
 C4485 wird immer als Fehler ausgegeben.  Verwenden Sie das [warning](../../preprocessor/warning.md)\-Pragma, um C4485 zu unterdrücken.  
  
## Beispiel  
 Im folgenden Beispiel wird C4485 generiert:  
  
```  
// C4485.cpp  
// compile with: /clr  
delegate void Del();  
  
ref struct A {  
   virtual event Del ^E;  
};  
  
ref struct B : A {  
   virtual event Del ^E;   // C4485  
};  
  
ref struct C : B {  
   virtual event Del ^E {  
      void raise() override {}  
      void add(Del ^) override {}  
      void remove(Del^) override {}  
   }  
};  
```
---
title: "Compilerfehler C3231"
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
  - "C3231"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3231"
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3231
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Argument': Das Vorlagentypargument kann keinen generischen Typparameter verwenden  
  
 Vorlagen werden zur Kompilierzeit instanziiert, Generika jedoch zur Laufzeit.  Es ist daher nicht möglich, generischen Code zu generieren, der die Vorlage aufrufen kann, da die Vorlage nicht zur Laufzeit instanziiert werden kann. Der generische Typ ist jedoch erst zur Laufzeit bekannt.  
  
 Im folgenden Beispiel wird C3231 generiert:  
  
```  
// C3231.cpp  
// compile with: /clr /LD  
template <class T> class A;  
  
generic <class T>  
ref class C {  
   void f() {  
      A<T> a;   // C3231  
   }  
};  
```
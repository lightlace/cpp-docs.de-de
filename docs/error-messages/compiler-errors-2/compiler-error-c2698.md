---
title: "Compilerfehler C2698"
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
  - "C2698"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2698"
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2698
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die using\-Deklaration für 'Deklaration 1' kann nicht zusammen mit der vorhandenen using\-Deklaration für 'Deklaration 2' verwendet werden  
  
 Sobald eine [using\-Deklaration](../../cpp/using-declaration.md) für einen Datenmember vorhanden ist, ist innerhalb des Gültigkeitsbereichs keine `using`\-Deklaration mit demselben Namen mehr zulässig, da nur Funktionen überladen werden können.  
  
 Im folgenden Beispiel wird C2698 generiert:  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```
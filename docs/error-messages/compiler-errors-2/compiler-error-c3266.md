---
title: "Compilerfehler C3266"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3266"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3266"
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3266
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"class": Ein Klassenkonstruktor muss eine "void"\-Parameterliste haben  
  
 Klassenkonstruktoren in einer Klasse mit \/CLR\-Programmierung akzeptieren keine Parameter.  
  
 Im folgenden Beispiel wird C3266 generiert:  
  
```  
// C3266.cpp // compile with: /clr ref class X { static X(int i) { // C3266 // try the following line instead // static X() { } }; int main() { }  
```  
  
 Im folgenden Beispiel wird C3266 generiert:  
  
```  
// C3266b.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __gc class X { static X(int i) { // C3266 // try the following line instead // static X() { } }; int main() { }  
```
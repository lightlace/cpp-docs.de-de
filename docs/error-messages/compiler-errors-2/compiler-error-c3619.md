---
title: "Compilerfehler C3619"
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
  - "C3619"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3619"
ms.assetid: 76ae80d0-9fbe-4297-a1ef-b1503377fdcf
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3619
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Vorlage kann nicht innerhalb eines verwalteten oder WinRT\-Typs deklariert werden.  
  
 Klassenvorlagen sind in einer verwalteten oder WinRT\-Klasse oder \-Schnittstelle nicht zulässig.  
  
 C3619 ist nur über **\/clr:oldSyntax** erreichbar.  
  
 Im folgenden Beispiel wird C3619 generiert:  
  
```  
// C3619.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class X {  
   template<typename T> class Y {   // C3619  
   };  
};  
```
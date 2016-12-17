---
title: "Compilerfehler C3838"
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
  - "C3838"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3838"
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3838
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kann nicht explizit von 'Typ' geerbt werden  
  
 Der angegebene `type` kann nicht als Basisklasse einer beliebigen Klasse fungieren.  
  
 Im folgenden Beispiel wird C3838 generiert:  
  
```  
// C3838a.cpp  
// compile with: /clr /c  
public ref class B : public System::Enum {};   // C3838  
```  
  
 Im folgenden Beispiel wird C3838 generiert:  
  
```  
// C3838b.cpp  
// compile with: /clr:oldSyntax /c  
public __gc class B : public System::ValueType {};   // C3838  
```
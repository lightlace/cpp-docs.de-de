---
title: "Compilerfehler C3838 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3838"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3838"
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
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
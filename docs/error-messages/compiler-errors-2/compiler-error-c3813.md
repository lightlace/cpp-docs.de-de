---
title: "Compilerfehler C3813 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3813"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3813"
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

eine Eigenschaftendeklaration kann nur in der Definition eines verwalteten oder WinRT\-Typs auftreten.  
  
 Ein [Eigenschaft](../../misc/property.md) kann nur innerhalb eines verwalteten oder Windows\-Runtime\-Typs deklariert werden.  Systemeigene Typen unterstützen das `property`\-Schlüsselwort nicht.  
  
 Im folgenden Beispiel wird C3813 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```
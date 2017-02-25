---
title: "Compilerwarnung (Stufe 3) C4580 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4580"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4580"
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 3) C4580
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\[attribute\] ist veraltet; geben Sie stattdessen System::Attribute oder Platform::Metadata als Basisklasse an.  
  
 [attribute](../../windows/attribute.md) ist nicht mehr die bevorzugte Syntax zum Erstellen von benutzerdefinierten Attributen.  Weitere Informationen finden Sie unter [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  Leiten Sie für CLR\-Code Attribute aus <xref:Attribute> ab.  Leiten Sie für Windows\-Runtime\-Code Attribute aus `Platform::Metadata` ab.  
  
## Beispiel  
 Im folgenden Beispiel wird C3454 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```  
// C4580.cpp  
// compile with: /W3 /c /clr  
[attribute]   // C4580  
public ref class Attr {  
public:  
   int m_t;  
};  
  
public ref class Attr2 : System::Attribute {  
public:  
   int m_t;  
};  
```
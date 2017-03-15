---
title: "Compilerfehler C3095 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3095"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3095"
ms.assetid: cde725be-0936-40f6-9e57-e1d7d0710f83
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3095
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Attribut": Das Attribut kann nicht wiederholt werden.  
  
 Einige Attribute werden so deklariert, dass mehrere Vorkommen des Attributs auf ein Ziel angewendet werden können.  
  
 Weitere Informationen finden Sie unter [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3095 generiert.  
  
```  
// C3095.cpp // compile with: /clr /c using namespace System; [AttributeUsage(AttributeTargets::All, AllowMultiple=false)] public ref class Attr : public Attribute { public: Attr(int t) : m_t(t) {} const int m_t; }; [AttributeUsage(AttributeTargets::All, AllowMultiple=true)] public ref class Attr2 : public Attribute { public: Attr2(int t) : m_t(t) {} const int m_t; }; [Attr(10)]   // C3095 [Attr(11)] ref class A {}; [Attr2(10)]   // OK [Attr2(11)] ref class B {};  
```
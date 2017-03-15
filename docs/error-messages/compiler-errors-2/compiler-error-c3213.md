---
title: "Compilerfehler C3213 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3213"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3213"
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3213
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse 'base\_type' hat eine stärkere Zugriffsbeschränkung als 'derived\_type'  
  
 Ein Typ, der von einer Assembly aus sichtbar ist, muss öffentlich sichtbare Basisklassen verwenden.  
  
 Im folgenden Beispiel wird C3213 generiert:  
  
```  
// C3213.cpp // compile with: /clr private ref struct privateG { public: int i; }; public ref struct publicG { public: int i; }; public ref struct V : public privateG {   // C3213 public: int j; }; public ref struct W: public publicG {   // OK public: int j; };  
```
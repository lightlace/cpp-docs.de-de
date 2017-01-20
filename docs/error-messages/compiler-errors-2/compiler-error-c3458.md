---
title: "Compilerfehler C3458"
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
  - "C3458"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3458"
ms.assetid: 940202fd-8dcc-4042-9c96-3f9e9127d2f1
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3458
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribut1': Das Attribut 'attribut2' wurde bereits für 'konstrukt' angegeben  
  
 Zwei Attribute, die sich gegenseitig ausschließen, wurden für dasselbe Konstrukt angegeben.  
  
## Beispiel  
 Im folgenden Beispiel wird C3458 generiert:  
  
```  
// C3458.cpp // compile with: /clr /c [System::Reflection::DefaultMember("Chars")] public ref class MyString { public: [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3458 property char default[int] { char get(int index); void set(int index, char c); } };  
```
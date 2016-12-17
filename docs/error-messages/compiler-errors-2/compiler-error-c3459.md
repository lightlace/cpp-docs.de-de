---
title: "Compilerfehler C3459"
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
  - "C3459"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3459"
ms.assetid: 3d290a20-d313-4c07-9bd8-c5c159cb169f
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3459
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"attribute": Das Attribut ist nur für den Klassenindexer \(indizierte Standardeigenschaft\) zulässig  
  
 Ein Attribut, das auf eine Klassenindexer\-Eigenschaft angewendet werden soll, wurde falsch verwendet.  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von indizierten Eigenschaften](../../misc/how-to-use-indexed-properties.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3459 generiert.  
  
```  
// C3459.cpp // compile with: /clr /c public ref class MyString { public: [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3459 property int Prop; }; // OK public ref class MyString2 { array<int>^ MyArr; public: MyString2() { MyArr = gcnew array<int>(5); } [System::Runtime::CompilerServices::IndexerName("Chars")]   // OK property int default[int] { int get(int index) { return MyArr[index]; } void set(int index, int value) { MyArr[index] = value; } } };  
```
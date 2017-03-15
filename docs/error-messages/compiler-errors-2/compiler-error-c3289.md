---
title: "Compilerfehler C3289 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3289"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3289"
ms.assetid: 3c1c623b-7fcf-43ab-a89a-8722532a8d29
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3289
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"property": Eine trivial\-Eigenschaft kann nicht indiziert werden  
  
 Eine Eigenschaft wurde falsch deklariert. Für eine indizierte Eigenschaft müssen Accessoren definiert werden. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3289 generiert.  
  
```  
// C3289.cpp // compile with: /clr public ref struct C { // user-defined simple indexer property int indexer1[int];   // C3289 // user-defined indexer property int indexer2[int] { int get(int i) { return 0; } void set(int i, int j) {} } }; int main() { C ^ MyC = gcnew C(); MyC->indexer2[0] = 1; }  
```
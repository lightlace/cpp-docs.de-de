---
title: "Compilerfehler C3170"
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
  - "C3170"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3170"
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3170
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es können nicht verschiedene Modulidentifizierer in einem Projekt vorhanden sein  
  
 In zwei Dateien einer Kompilierung wurden [module](../../windows/module-cpp.md)\-Attribute mit unterschiedlichen Namen gefunden.  Pro Kompilierung kann nur ein eindeutiges `module`\-Attribut angegeben werden.  
  
 Identische `module`\-Attribute können in mehr als einer Quellcodedatei angegeben werden.  
  
 Werden beispielsweise folgende **module**\-Attribute gefunden,  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 und anschließend  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 erzeugt der Compiler den Fehler C3170 \(beachten Sie die unterschiedlichen Namen\).
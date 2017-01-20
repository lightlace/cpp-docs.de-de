---
title: "Compilerfehler C3171"
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
  - "C3171"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3171"
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3171
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Module': Es können keine verschiedenen 'module'\-Attribute in einem Projekt angegeben werden  
  
 In zwei Dateien einer Kompilierung wurden [module](../../windows/module-cpp.md)\-Attribute mit unterschiedlichen Parameterlisten gefunden.  Pro Kompilierung kann nur ein eindeutiges `module`\-Attribut angegeben werden.  
  
 Identische `module`\-Attribute können in mehr als einer Quellcodedatei angegeben werden.  
  
 Werden z. B. die folgenden `module`\-Attribute gefunden:  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 und anschließend  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 erzeugt der Compiler den Fehler C3171 \(beachten Sie die unterschiedlichen Versionswerte\).
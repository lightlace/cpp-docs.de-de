---
title: "Compilerwarnung (Stufe 1 und Stufe 4) C4700"
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
  - "C4700"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4700"
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1 und Stufe 4) C4700
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht initialisierte lokale Variable 'Name' verwendet  
  
 Sie haben die lokale Variable *name* verwendet, ohne ihr zuvor einen Wert zuzuweisen. Dies kann unvorhersehbare Ergebnisse zur Folge haben.  
  
 Im folgenden Beispiel wird C4700 generiert:  
  
```  
// C4700.cpp  
// compile with: /W1  
int main() {  
   int i;  
   return i;   // C4700  
}  
```  
  
 Unter [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) ist dies eine Warnung der Stufe 4.  Im folgenden Beispiel wird C4700 generiert:  
  
```  
// C4700b.cpp  
// compile with: /W4 /clr:safe /c  
using namespace System;  
int main() {  
   Int32^ bi;  
   return *bi;   // C4700  
}  
```
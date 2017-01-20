---
title: "Compilerwarnung (Stufe 1) C4005"
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
  - "C4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4005"
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Makro\-Neudefinition  
  
 Der Makrobezeichner wurde zweimal definiert.  Der Compiler verwendet die zweite Makrodefinition.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Ein Makro in der Befehlszeile und im Code wurde mit einer `#define`\-Direktive definiert.  
  
2.  Aus Includedateien importierte Makros.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Entfernen Sie eine der Definitionen.  
  
2.  Verwenden Sie eine [\#undef](../../preprocessor/hash-undef-directive-c-cpp.md)\-Direktive vor der zweiten Definition.  
  
 Im folgenden Beispiel wird C4005 generiert:  
  
```  
// C4005.cpp  
// compile with: /W1 /EHsc  
#include <iostream>  
using namespace std;  
  
#define TEST "test1"  
#define TEST "test2"   // C4005 delete or rename to resolve the warning  
  
int main() {  
   cout << TEST << endl;  
}  
```
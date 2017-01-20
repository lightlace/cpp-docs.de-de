---
title: "Schwerwiegender Fehler C1094"
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
  - "C1094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1094"
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\-Zmval1': Die Befehlszeilenoption stimmt nicht mit dem Wert überein, der zum Erstellen des vorkompilierten Headers verwendet wurde \('\-Zmval2'\)  
  
 Der Wert, der an [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) übergeben wird, muss dem Wert entsprechen, der an [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) wird \(**\/Zm**\-Werte müssen in allen Kompilationen identisch sein, die dieselben vorkompilierten Headerdateien verwenden oder erstellen\).  
  
 Im folgenden Beispiel wird C1094 generiert:  
  
```  
// C1094.h  
int func1();  
```  
  
 und anschließend  
  
```  
// C1094.cpp  
// compile with: /Yc"C1094.h" /Zm200  
int u;  
int main() {  
   int sd = 32;  
}  
#include "C1094.h"  
```  
  
 und anschließend  
  
```  
// C1094b.cpp  
// compile with: /Yu"C1094.h" /Zm300 /c  
#include "C1094.h"   // C1094 compile with /Zm200  
void Test() {}  
```